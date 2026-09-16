# 📚 Data Dictionary

This document describes the fields used in the `sales_retail_etl` table for the **Retail Sales Analytics** project.

## 🗂️ Main Table

`sales_retail_etl`

## 📋 Fields

| Field | Data Type | Description | Business Meaning |
|---|---|---|---|
| `SKU` | Text | Unique product identifier | Identifies a product reference |
| `Produit` | Text | Product name | Name of the product sold |
| `Categorie` | Text | Product category | Groups products by category |
| `Marque` | Text | Brand name | Identifies the product brand |
| `Pays` | Text | Sales country | Geographic market |
| `Date` | Date | Sales date | Used for time analysis |
| `Unites` | Integer | Units associated with the record | Quantity indicator |
| `Unités Vendues` | Integer | Units sold | Measures sales volume |
| `CA Total` | Decimal | Total revenue | Overall sales revenue |
| `CA_EUR` | Decimal | Revenue in euros | Standardized revenue used in the dashboard |
| `Ads Total` | Decimal | Total advertising spend | Advertising expenditure |
| `Ads_EUR` | Decimal | Advertising spend in euros | Standardized advertising cost |
| `ROAS` | Decimal | Return on Advertising Spend | Measures advertising efficiency |
| `ROAS Global` | Decimal | Overall ROAS in the selected context | Global advertising performance |
| `Marge Estimée` | Decimal | Estimated commercial margin | Profitability indicator |
| `Performance` | Text / Numeric | Performance indicator | Used to evaluate performance |

## 📊 Dynamic DAX Measures

### `Insight_Pays_CA`
Identifies the country generating the highest revenue within the current filter context.

### `Insight_Marque_ROAS`
Identifies the brand with the highest ROAS within the current filter context.

### `Insight_Produit_CA`
Identifies the product generating the highest revenue within the current filter context.

These measures power the dynamic insights displayed in the dashboard.

## 📐 Key Metrics

### Revenue

```text
CA Total = SUM(CA_EUR)
```

### ROAS

```text
ROAS = Revenue / Advertising Spend
```

A ROAS of 5 means that €1 spent on advertising generated €5 in revenue.

### Estimated Margin

`Marge Estimée` provides an estimated profitability indicator based on the available dataset.

## 🔄 Dashboard Filters

The dashboard can be filtered by:

- **Marque** — Brand
- **Pays** — Country
- **Période d'analyse** — Date range

KPI cards, charts and dynamic insights respond to these filters.

## 📈 Main Analysis Dimensions

### Product
- Top products by revenue
- Product performance

### Brand
- Revenue by brand
- ROAS by brand
- Brand performance

### Country
- Revenue by country
- ROAS by country
- Geographic performance

### Time
- Revenue evolution
- Sales trends
- Performance over selected periods

## 💶 Currency

Financial metrics are standardized and displayed in **EUR (€)**:

- Revenue
- Advertising spend
- Estimated margin

## ⚠️ Data Considerations

- `CA_EUR` and `Ads_EUR` are the standardized euro values used for analysis.
- ROAS is a ratio, not a percentage.
- `Marge Estimée` is an estimated indicator and should not be interpreted as a complete accounting profit measure.
- Dashboard results depend on the selected filters.
- Dynamic insights adapt to the current filter context.

## 🎯 Intended Use

This dataset supports:

- Retail performance analysis
- Sales reporting
- Advertising performance analysis
- Business Intelligence
- KPI monitoring
- Data-driven decision making
