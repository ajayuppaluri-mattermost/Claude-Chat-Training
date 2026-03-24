---
name: omni-content-builder
description: Create, update, and manage Omni Analytics documents and dashboards programmatically via the REST API. Use this skill whenever someone wants to create a new dashboard, build a report, add tiles to a dashboard, update dashboard content, set up filters, manage the document lifecycle, or any variant of "create a dashboard", "build a report", "make a chart showing", "set up a dashboard with", or "turn this data into a dashboard".
---

# Omni Content Builder

Create, update, and manage Omni documents and dashboards programmatically via the REST API — document lifecycle, workbook models, filters, and dashboard content.

## Known Issues & Safe Defaults

- **Chart rendering**: Complex chart types may show "No chart available" in the Omni UI if `config`, `visType`, or `prefersChart` are misconfigured. Default to `chartType: "table"` for reliable rendering.
- **Every query must include at least one measure** — a query with only dimensions produces empty/nonsense tiles.
- **Use `identifier` not `id`** for all document API calls — `.id` is null for workbook-type documents.
- **Boolean filters may be silently dropped** when a `pivots` array is present. If boolean filters aren't applying, remove the pivot and test again.

## Prerequisites

```bash
export OMNI_BASE_URL="https://yourorg.omniapp.co"
export OMNI_API_KEY="your-api-key"
```

## API Discovery

```bash
curl -L "$OMNI_BASE_URL/openapi.json" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

## Document Management

### Create Document (Name Only)

```bash
curl -L -X POST "$OMNI_BASE_URL/api/v1/documents" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "modelId": "your-model-id",
    "name": "Q1 Revenue Report"
  }'
```

Returns the new document's `identifier`, `workbookId`, and `dashboardId`.

### Create Document with Queries and Visualizations

Use `queryPresentations` to create a document pre-populated with query tabs and visualization configurations.

```bash
curl -L -X POST "$OMNI_BASE_URL/api/v1/documents" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "modelId": "your-model-id",
    "name": "Q1 Revenue Report",
    "queryPresentations": [
      {
        "name": "Total Revenue",
        "topicName": "order_items",
        "prefersChart": true,
        "visType": "omni-kpi",
        "fields": ["order_items.total_revenue"],
        "query": {
          "table": "order_items",
          "fields": ["order_items.total_revenue"],
          "join_paths_from_topic_name": "order_items",
          "visConfig": { "chartType": "kpi" }
        },
        "config": {
          "alignment": "left",
          "verticalAlignment": "top",
          "markdownConfig": [
            {
              "id": "kpi-1",
              "type": "number",
              "config": {
                "field": {
                  "row": "_first",
                  "field": { "name": "order_items.total_revenue", "pivotMap": {} },
                  "label": { "value": "Total Revenue" }
                },
                "descriptionBefore": ""
              }
            }
          ]
        }
      },
      {
        "name": "Monthly Revenue Trend",
        "topicName": "order_items",
        "prefersChart": true,
        "visType": "basic",
        "fields": ["order_items.created_at[month]", "order_items.total_revenue"],
        "query": {
          "table": "order_items",
          "fields": ["order_items.created_at[month]", "order_items.total_revenue"],
          "sorts": [{ "column_name": "order_items.created_at[month]", "sort_descending": false }],
          "filters": { "order_items.created_at": "this quarter" },
          "limit": 100,
          "join_paths_from_topic_name": "order_items",
          "visConfig": { "chartType": "lineColor" }
        },
        "config": {
          "x": { "field": { "name": "order_items.created_at[month]" } },
          "mark": { "type": "line" },
          "color": {},
          "series": [{ "field": { "name": "order_items.total_revenue" }, "yAxis": "y" }],
          "version": 0,
          "configType": "cartesian"
        }
      }
    ]
  }'
```

#### queryPresentation Object Reference

| Parameter | Required | Description |
|-----------|----------|-------------|
| `name` | Yes | Tile/tab title |
| `topicName` | Recommended | Topic name for the query |
| `prefersChart` | Yes | **Must be `true` to render a chart** |
| `visType` | Yes | `"omni-kpi"` for KPI tiles, `"basic"` for standard charts |
| `fields` | Yes | Duplicate of `query.fields` — must be at this level too |
| `config` | Yes | Chart-specific configuration object |
| `query` | Yes | Query definition |

#### visConfig chartType values

| chartType | Visualization |
|-----------|--------------|
| `kpi` | KPI / single value |
| `lineColor` | Line chart |
| `barColor` | Bar chart |
| `areaColor` | Area chart |
| `stackedBarColor` | Stacked bar chart |
| `pie` | Pie / donut chart |
| `scatter` | Scatter plot |
| `heatmap` | Heatmap |
| `map` | Map visualization |
| `table` | Data table |

### Rename Document

```bash
curl -L -X PATCH "$OMNI_BASE_URL/api/v1/documents/{documentId}" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "name": "Q1 Revenue Report (Updated)", "clearExistingDraft": true }'
```

Set `clearExistingDraft: true` if the document has an existing draft, otherwise the API returns 409 Conflict.

### Delete Document

```bash
curl -L -X DELETE "$OMNI_BASE_URL/api/v1/documents/{documentId}" \
  -H "Authorization: Bearer $OMNI_API_KEY"
```

### Move Document

```bash
curl -L -X PUT "$OMNI_BASE_URL/api/v1/documents/{documentId}/move" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "folderPath": "/Marketing/Reports", "scope": "organization" }'
```

### Duplicate Document

```bash
curl -L -X POST "$OMNI_BASE_URL/api/v1/documents/{documentId}/duplicate" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "name": "Copy of Q1 Revenue Report", "folderPath": "/Marketing/Reports" }'
```

Only published documents can be duplicated.

## Updating a Dashboard's Model

```bash
# Step 1: Get workbook_id
curl -L "$OMNI_BASE_URL/api/v1/documents/{documentId}" \
  -H "Authorization: Bearer $OMNI_API_KEY"

# Step 2: POST YAML to workbook model
curl -L -X POST "$OMNI_BASE_URL/api/unstable/models/{workbookId}/yaml" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "fileName": "order_items.view",
    "yaml": "views:\n  order_items:\n    dimensions:\n      is_high_value:\n        sql: \"${sale_price} > 100\"\n        label: High Value Order"
  }'
```

`fileName` must be `"model"`, `"relationships"`, or end with `.view` or `.topic`.

## Dashboard Filters

The most reliable way to create dashboard filters is to include `filterConfig` and `filterOrder` in the initial `POST /api/v1/documents` call:

```bash
curl -L -X POST "$OMNI_BASE_URL/api/v1/documents" \
  -H "Authorization: Bearer $OMNI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "modelId": "your-model-id",
    "name": "Filtered Dashboard",
    "filterConfig": {
      "date_filter": {
        "type": "date",
        "label": "Date Range",
        "kind": "TIME_FOR_INTERVAL_DURATION",
        "ui_type": "PAST",
        "left_side": "6 months ago",
        "right_side": "6 months"
      },
      "state_filter": {
        "type": "string",
        "label": "State",
        "kind": "EQUALS",
        "fieldName": "users.state",
        "values": []
      }
    },
    "filterOrder": ["date_filter", "state_filter"],
    "queryPresentations": []
  }'
```

## URL Patterns

```
Dashboard: {OMNI_BASE_URL}/dashboards/{identifier}
Workbook:  {OMNI_BASE_URL}/w/{identifier}
```

## Recommended Build Workflow

1. **Discover fields** — use `omni-model-explorer` to find topic + fields (1-2 calls)
2. **Optionally read a reference dashboard** — `GET /api/v1/documents/{id}` to capture `queryPresentations` patterns
3. **Create document** — single `POST /api/v1/documents` with `queryPresentations` + `filterConfig` + `filterOrder`
4. **Share the link** — return `{OMNI_BASE_URL}/dashboards/{identifier}` to the user
5. **Refine in UI** — tile layout, chart styling, and advanced config are best done in the Omni UI

## Docs Reference

- [Documents API](https://docs.omni.co/api/documents.md) · [Dashboard Filters](https://docs.omni.co/api/dashboard-filters.md) · [Dashboard Downloads](https://docs.omni.co/api/dashboard-downloads.md) · [Query API](https://docs.omni.co/api/queries.md)

## Related Skills

- **omni-model-explorer** — understand available fields
- **omni-model-builder** — create shared model fields
- **omni-query** — test queries before adding to dashboards
- **omni-content-explorer** — find existing dashboards to learn from
- **omni-embed** — embed dashboards in external apps
