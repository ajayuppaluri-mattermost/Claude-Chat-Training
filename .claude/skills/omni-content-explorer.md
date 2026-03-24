---
name: omni-content-explorer
description: Find, browse, and organize content in Omni Analytics — dashboards, workbooks, folders, and labels — using the REST API. Use this skill whenever someone wants to find an existing dashboard, search for content, list workbooks, browse folders, see what dashboards exist, find popular reports, download a dashboard as PDF or PNG, favorite content, manage labels on documents, or any variant of "find the dashboard about", "what reports do we have", "show me our dashboards", "where is the sales report", or "download this dashboard".
---

# Omni Content Explorer

Find, browse, and organize dashboards, workbooks, folders, and labels in Omni Analytics via the REST API.

## Prerequisites

```bash
export OMNI_BASE_URL="https://yourorg.omniapp.co"
export OMNI_API_KEY="your-api-key"
```

## API Discovery

Fetch the OpenAPI spec at `/openapi.json` to verify endpoints and parameters before making calls.

```bash
curl -L "$OMNI_BASE_URL/openapi.json" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

## Browsing Content

```bash
# List all content
curl -L "$OMNI_BASE_URL/api/v1/content" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Include counts and labels
curl -L "$OMNI_BASE_URL/api/v1/content?include=_count,labels" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

- Filter by labels, scope
- Sort by favorites or updatedAt
- Use cursor-based pagination with `pageInfo`

## Working with Documents

```bash
# List documents
curl -L "$OMNI_BASE_URL/api/v1/documents" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Filter by creator
curl -L "$OMNI_BASE_URL/api/v1/documents?creatorId={userId}" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

> **Critical:** Use the `identifier` field for API calls, not `id`

```bash
# Retrieve dashboard query definitions
curl -L "$OMNI_BASE_URL/api/v1/documents/{identifier}/queries" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

## Folders, Labels & Favorites

```bash
# List folders
curl -L "$OMNI_BASE_URL/api/v1/folders" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Create folder
curl -L -X POST "$OMNI_BASE_URL/api/v1/folders" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "name": "My Folder", "scope": "organization" }'

# Add label to document
curl -L -X PUT "$OMNI_BASE_URL/api/v1/documents/{identifier}/labels/{labelName}" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Remove label
curl -L -X DELETE "$OMNI_BASE_URL/api/v1/documents/{identifier}/labels/{labelName}" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Favorite a document
curl -L -X PUT "$OMNI_BASE_URL/api/v1/documents/{identifier}/favorite" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Unfavorite
curl -L -X DELETE "$OMNI_BASE_URL/api/v1/documents/{identifier}/favorite" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

## Dashboard Downloads

```bash
# Start async download
curl -L -X POST "$OMNI_BASE_URL/api/v1/dashboards/{dashboardId}/download" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "format": "pdf" }'

# Poll status
curl -L "$OMNI_BASE_URL/api/v1/download/{jobId}/status" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

## URL Patterns

Construct links:
- `{OMNI_BASE_URL}/dashboards/{identifier}`
- `{OMNI_BASE_URL}/w/{identifier}`

## Related Skills

- **omni-query** — run queries against discovered content
- **omni-content-builder** — create or update dashboards
- **omni-embed** — embed dashboards in external apps
- **omni-admin** — manage permissions on content
