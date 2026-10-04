# Supply Chain & Operations Performance — Power BI

A 3-page Power BI portfolio project for analyzing supply-chain operations, inventory, supplier performance, logistics, manufacturing cost, and quality.

## Business Questions

- How is the supply chain performing overall?
- Where are inventory and supplier risks?
- What are the major logistics and cost patterns?
- How do production, inventory, sales, lead time, and quality measures compare across business dimensions?

## Dataset

The source dataset contains **100 records and 24 columns** covering:

- Product and SKU information
- Sales and revenue
- Inventory and stock levels
- Supplier information
- Lead times and order quantities
- Shipping carriers, times, costs, and transportation modes
- Production volumes
- Manufacturing lead time and manufacturing costs
- Inspection results and defect rates
- Routes and costs

The original CSV used for the project is included in `data/supply_chain_data.csv`.

## Tools & Skills

- Power BI
- Power Query
- DAX
- Data modeling
- Star-schema-style relationships
- KPI design
- Interactive dashboard design
- Bar/column charts
- Combo charts
- Scatter charts
- Matrix/table analysis
- Donut chart
- Business-focused storytelling

## Data Model

The report uses three tables:

- `FactSupplyChain`
- `DimProduct`
- `DimSupplier`

Relationships:

```text
DimProduct[SKU]  1 ─────── *  FactSupplyChain[SKU]

DimSupplier[Supplier name]  1 ─────── *  FactSupplyChain[Supplier name]
```

The dimension tables were created to separate reusable product and supplier attributes from the main operational fact table.

## Dashboard Pages

### 1. Operations Overview

**KPIs**
- Total Revenue
- Average Defect Rate
- Total Products Sold
- Total Stock
- Total Supply Chain Cost
- Average Lead Time
- Average Defect Rate

**Visuals**
- Revenue by Product Type
- Revenue vs Supply Chain Cost
- Production Volume by Product Type
- Inventory vs Products Sold

Screenshot: `screenshots/operations_overview.png`

### 2. Inventory & Supplier Risk

**KPIs**
- Total Stock
- Average Stock per SKU
- Average Supplier Lead Time
- Average Defect Rate
- Total Order Quantity

**Visuals**
- Supplier Performance Matrix
- Supplier Cost vs Lead Time
- Stock Level by Product Type
- Inventory Risk
- Stock vs Sales

Screenshot: `screenshots/inventory_supplier_risk.png`

### 3. Logistics, Cost & Quality

**KPIs**
- Total Shipping Cost
- Average Shipping Time
- Average Manufacturing Cost
- Average Defect Rate
- Total Production

**Visuals**
- Cost by Transportation Modes
- Shipping Performance by Carrier
- Route Cost Analysis
- Average Manufacturing Cost by Product Type
- Quality Analysis
- Defect Rate by Supplier

Screenshot: `screenshots/logistics_cost_quality.png`

## Power Query

The source data was cleaned and prepared in Power Query. The project uses business-friendly column names and appropriate data types.

Key preparation steps:

- Imported the CSV
- Renamed source columns for clearer report modeling
- Applied appropriate numeric/text data types
- Checked the dataset for missing/error values
- Created `DimProduct` from product/SKU attributes
- Created `DimSupplier` from supplier attributes
- Removed duplicate supplier records where required
- Created relationships between the dimensions and `FactSupplyChain`

See [`Power_Query_Steps.md`](Power_Query_Steps.md) for the documented preparation process.

## DAX

The main reusable measures are documented in [`DAX_Measures.md`](DAX_Measures.md).

Core measures include:

- Total Revenue
- Total Products Sold
- Total Stock
- Total Supply Chain Cost
- Average Lead Time
- Average Defect Rate

## Business Value

The dashboard provides a structured view of:

- Revenue and sales activity
- Inventory versus products sold
- Supplier performance
- Supplier lead-time patterns
- Transportation and route costs
- Manufacturing cost patterns
- Inspection results and defect rates

The dashboard is designed for **descriptive analysis and investigation**, not forecasting.

## Important Analytical Limitation

The dataset is a point-in-time operational dataset. It does not include historical inventory/sales series, reorder points, safety-stock targets, supplier SLA targets, or other thresholds needed to make definitive stockout/overstock or service-level classifications.

## Portfolio Skills Demonstrated

- Data cleaning with Power Query
- Data modeling with dimension and fact tables
- One-to-many relationships
- DAX measures
- KPI cards
- Multi-page dashboard design
- Supplier and inventory analysis
- Logistics cost analysis
- Quality analysis
- Business-focused visualization

## Repository Structure

```text
supply-chain-operations-powerbi/
│
├── data/
│   └── supply_chain_data.csv
│
├── screenshots/
│   ├── operations_overview.png
│   ├── inventory_supplier_risk.png
│   └── logistics_cost_quality.png
│
├── README.md
├── DAX_Measures.md
├── Data_Dictionary.md
├── Power_Query_Steps.md
├── PROJECT_STATUS.md
└── .gitignore
```

## Power BI File

Save the completed Power BI report as:

`Supply_Chain_Operations_Performance.pbix`

Place it in the repository root if you want the PBIX included in your GitHub repository.

## Future Improvements

- Historical inventory and sales tracking
- Reorder-point and safety-stock targets
- Supplier SLA targets
- On-time delivery KPI
- Inventory turnover
- Demand forecasting
- Automated refresh
