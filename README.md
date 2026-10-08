# Three-Statement Financial Dashboard — Lucky Cement

An interactive Power BI dashboard (`waseem.pbix`) that summarises Lucky Cement's financial performance across the income statement, balance sheet and cash flow statement. It tracks profitability, leverage, liquidity and cash generation year by year in a single one-page view.

## Overview

| Item | Detail |
|---|---|
| File | `waseem.pbix` |
| Report title | Three Statement Financial Lucky Cement Dashboard |
| Pages | 1 (1280 × 720) |
| Data model | 1 table, `data` (one row per year) |
| Theme | Power BI base theme `CY24SU10` with a custom background, logo and images |
| Created with | Power BI Desktop (release 2025.06) |

## Dashboard contents

### KPI cards
Six headline metrics for the selected year(s):

- Revenue
- EBITDA Margin
- Free Cash Flow
- Total Debt
- Return on Equity
- FCF Conversion

### Charts

| Visual | Type | Fields |
|---|---|---|
| Revenue vs. leverage | Stacked column + line | Revenue (columns), Net Debt / EBITDA (line), by Years |
| Cash generation | Clustered column + line | Cash from Operations, Free Cash Flow, by Years |
| Debt and liquidity | Clustered column + line | Total Debt, Cash and Equivalents, by Years |
| Margin trends | Line | Gross Margin, Net Profit Margin, by Years |

### Interactivity
A **Years** slicer filters every visual on the page. Click a year (or select several) to focus the analysis.

## Data fields

All fields come from the `data` table:

| Field | Statement / category |
|---|---|
| Years | Time dimension |
| Revenue | Income statement |
| Gross Margin | Profitability |
| EBITDA Margin | Profitability |
| Net profit margin | Profitability |
| Return on Equity | Returns |
| Cash from operations | Cash flow statement |
| Free Cash Flow | Cash flow statement |
| FCF Conversion | Cash flow quality |
| Total Debt | Balance sheet |
| Cash And Equavalent | Balance sheet (field name as spelled in the model) |
| Net Debt / EBITDA | Leverage |

The years referenced in the slicer filter are 2022–2024 and 2026–2029, so the data appears to mix historical figures with forward-looking estimates. Check the source table before treating the later years as actuals.

## How to use

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows).
2. Open `waseem.pbix`.
3. Use the **Years** slicer to filter the page.
4. Hover over any visual for tooltips with exact values.

To refresh or change the data, go to **Home → Transform data** and edit the `data` table. The report was created from the cloud service, and the data appears to be embedded in the file rather than linked to an external source.

## Notes and limitations

- **KPI cards use `Sum`.** Ratios such as EBITDA Margin, Return on Equity and FCF Conversion are summed across the selected years. With several years selected, these cards show a total of percentages, which is not meaningful. Either select a single year or switch those cards to Average or Latest value.
- **Typo in a field name:** `Cash And Equavalent` should be "Equivalent". Renaming it in the model will not break the visuals.
- **Missing year:** 2025 does not appear in the slicer filter. Confirm whether that is intentional.
- **Single-table model:** there are no relationships or DAX measures, so adding new calculations means creating measures from scratch.

## Possible improvements

- Add DAX measures (YoY growth, average margins) in place of raw `Sum` aggregations.
- Add pages for each statement (income statement, balance sheet, cash flow) with the full line items.
- Document the data source and units (for example, PKR millions) on the report page.

## Author

Prepared by Waseem.

