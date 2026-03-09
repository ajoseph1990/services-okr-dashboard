# Services Business OKR Dashboard

FY2025 Performance Dashboard for GEP Services - Strategy | Consulting | Managed Services

## Features

- **MTD / YTD / Forecast Views** - Toggle between different time perspectives
- **Executive Summary** - Key metrics at a glance
- **Tab Navigation** - Exec Summary, Overview, Consulting, Managed Services, People & Culture, SC Strategy
- **Deal Intelligence** - Closed deals, Active Pipeline, Bonus opportunities
- **Dynamic Data** - Reads from embedded Excel data (or SharePoint when deployed)

## Views

| View | Cards Shown | Tables Shown |
|------|-------------|--------------|
| MTD | Revenue, ACV, Margin, Agentic ARR | Closed Deals |
| YTD | Revenue, ACV, Margin, Agentic ARR | Closed Deals |
| Forecast | Revenue, Margin | Closed Deals, Pipeline, Bonus |

## Data Structure

The dashboard expects data from an Excel file with these sheets:
- **Monthly Metrics** - KPIs with columns: Metric, Annual Target, Jan-Dec, YTD
- **Deals** - Closed deals with: Month, Client, Type, Scope, ACV ($M)
- **Pipeline** - Active opportunities with: Client, Scope, ACV ($M), Weighted ACV ($M), Probability
- **Bonus** - Bonus opportunities with: Client, Estimated Bonus ($M), Probability

## Deployment

### Local Development
Simply open `index.html` in a browser.

### Azure Static Web Apps
```bash
az login
az staticwebapp create \
  --name services-okr-dashboard \
  --resource-group <your-resource-group> \
  --source . \
  --location "eastus2" \
  --branch main \
  --app-location "/" \
  --output-location "/"
```

## Updating Data

1. Update the `EMBEDDED_DATA` object in `index.html` with new values
2. Or connect to SharePoint/Microsoft 365 MCP for live data (requires Azure deployment)

## Tech Stack

- Vanilla HTML/CSS/JavaScript
- No build process required
- Inter font (Google Fonts)
