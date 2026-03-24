---
name: omni-embed
description: Embed Omni Analytics dashboards in external applications using signed iframe URLs, custom themes, and postMessage events. Use this skill whenever someone wants to embed a dashboard, create a white-label analytics experience, build embedded analytics, customize the look and feel of an embedded dashboard, set up row-level security for embedded users, handle embed events, or any variant of "embed this dashboard", "white-label analytics", "add Omni to my app", "customize the embed theme", or "listen for drill events".
---

# Omni Embed

Embed Omni dashboards in external applications using signed iframe URLs. The `@omni-co/embed` SDK handles URL signing and theme customization. Omni's postMessage events enable two-way communication between the parent app and embedded iframe.

> **Tip**: Use `omni-content-explorer` to find dashboards to embed, and `omni-admin` to manage embed user permissions.

## Prerequisites

```bash
npm install @omni-co/embed
```

```bash
export OMNI_BASE_URL="https://yourorg.embed-omniapp.co"   # Embed domain
export OMNI_EMBED_SECRET="your-embed-secret"               # Admin → Embed
export OMNI_API_KEY="your-api-key"                         # For user/content API calls
```

The embed secret is found in **Admin → Embed** in your Omni instance. The `OMNI_BASE_URL` for embedding uses the `.embed-omniapp.co` domain, not the standard `.omniapp.co` domain.

## Signing Embed URLs

```typescript
import { embedSsoDashboard, EmbedSessionMode } from "@omni-co/embed";

const embedUrl = await embedSsoDashboard({
  contentId: "dashboard-uuid",
  secret: process.env.OMNI_EMBED_SECRET,
  host: "yourorg.embed-omniapp.co",       // Hostname only, no https://
  externalId: "user@example.com",
  name: "Jane Doe",
  userAttributes: { brand: ["Acme"] },     // For row-level security
  mode: EmbedSessionMode.SingleContent,
  prefersDark: "false",
});
```

### Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| `contentId` | Yes | Dashboard UUID (from URL or Admin → Dashboards) |
| `secret` | Yes | Embed secret from Admin → Embed |
| `host` | Yes | Embed hostname only — no protocol, no port |
| `externalId` | Yes | Unique user identifier (typically email) |
| `name` | Yes | Display name for the user |
| `userAttributes` | No | `Record<string, string[]>` for row-level security |
| `mode` | No | `SingleContent` (default) or `Application` (enables create) |
| `prefersDark` | No | `"true"` or `"false"` |
| `customTheme` | No | Theme object |
| `entity` | No | Entity name for workspaces |

> **Gotcha**: The `host` parameter must be a bare hostname. Including a protocol (`https://`) or port (`:3000`) causes Omni to return 400.

## Custom Themes

```typescript
const embedUrl = await embedSsoDashboard({
  // ...signing params
  customTheme: {
    "dashboard-background": "#FEF2F2",
    "dashboard-tile-background": "#FFF5F5",
    "dashboard-key-color": "#E60000",
    "dashboard-key-text-color": "#ffffff",
  },
});
```

### Key Theme Properties

**Page:** `dashboard-background`, `dashboard-page-padding`

**Tiles:** `dashboard-tile-background`, `dashboard-tile-shadow`, `dashboard-tile-text-body-color`, `dashboard-tile-title-text-color`, `dashboard-tile-border-color`, `dashboard-tile-border-radius`

**Controls:** `dashboard-control-background`, `dashboard-control-border-color`, `dashboard-control-text-color`, `dashboard-control-label-color`

**Buttons:** `dashboard-key-color`, `dashboard-key-text-color`, `dashboard-button-radius`

### Theming Tips

- `dashboard-background` → light brand tint (color-50)
- `dashboard-tile-background` → slightly lighter than page background
- `dashboard-tile-title-text-color` → brand primary
- `dashboard-key-color` → brand primary
- Use solid hex colors for reliability

## Embed Events

### Listening for Events

```javascript
window.addEventListener("message", (event) => {
  if (event.data?.source !== "omni") return;

  switch (event.data.name) {
    case "dashboard:loaded":
      // Dashboard ready
      break;
    case "error":
      // Handle error
      break;
    case "dashboard:tile-drill":
      // Handle drill action — use event.data.payload.drill.rowToDrill
      break;
  }
});
```

### Event Reference

| Event | Description |
|-------|-------------|
| `dashboard:loaded` | Fired when embedded dashboard finishes loading |
| `dashboard:filters` | Fired when filter state changes |
| `error` | Fired when a detectable error occurs |
| `dashboard:tile-drill` | Fired when a user drills on any dashboard tile |
| `page:changed` | Fired when the URL changes inside the iframe |

### Sending Filters to the Iframe

```javascript
iframe.contentWindow.postMessage({
  source: "omni",
  name: "dashboard:filter-change-by-url-parameter",
  payload: {
    filterUrlParameter: 'f--<filter_id>={"values":["value1","value2"]}'
  }
}, iframeOrigin);
```

## Entity Workspaces

```typescript
import {
  embedSsoDashboard,
  EmbedSessionMode,
  EmbedEntityFolderContentRoles,
  EmbedUiSettings,
  EmbedConnectionRoles,
} from "@omni-co/embed";

const embedUrl = await embedSsoDashboard({
  // ...standard signing params
  entity: "acme",
  entityFolderContentRole: EmbedEntityFolderContentRoles.EDITOR,
  mode: EmbedSessionMode.Application,
  uiSettings: {
    [EmbedUiSettings.SHOW_NAVIGATION]: false,
  },
  connectionRoles: {
    "connection-uuid": EmbedConnectionRoles.RESTRICTED_QUERIER,
  },
});
```

## Embed Users and Permissions

```bash
# Look up an embed user by externalId
curl -L "$OMNI_API_BASE/api/scim/v2/embed/users?filter=embedExternalId%20eq%20%22user@example.com%22" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# List documents by user permission
curl -L "$OMNI_API_BASE/api/v1/documents?userId={omniUserId}" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# List folders for friendly names
curl -L "$OMNI_API_BASE/api/v1/folders" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

### Domain Mapping

```
Embed: yourorg.embed-omniapp.co  →  used for iframe URLs
API:   yourorg.omniapp.co        →  used for REST API calls
```

## Docs Reference

- [Embed Overview](https://docs.omni.co/embed.md) · [Custom Themes](https://docs.omni.co/embed/customization/themes.md) · [Embed Events](https://docs.omni.co/embed/events.md) · [Embed Users API](https://docs.omni.co/api/users/list-embed-users.md)

## Related Skills

- **omni-content-explorer** — find dashboards to embed
- **omni-content-builder** — create dashboards before embedding them
- **omni-admin** — manage embed user permissions and connections
- **omni-model-explorer** — understand available fields for embed event data
