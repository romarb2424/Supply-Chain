# Power Query Steps

## Main Query

The source CSV was imported into Power BI and prepared as the main table:

`FactSupplyChain`

## Preparation

1. Imported the supply-chain CSV.
2. Reviewed column names and data quality.
3. Renamed source fields to business-friendly names used by the DAX/model.
4. Applied suitable data types to numeric, text, and categorical fields.
5. Checked for null, blank, and error values.
6. Kept the operational records in the main `FactSupplyChain` table.
7. Created a reference table for products and named it `DimProduct`.
8. Created a reference table for suppliers and named it `DimSupplier`.
9. Removed duplicate supplier records where required for the supplier dimension.
10. Used SKU as the product relationship key.
11. Used Supplier name as the supplier relationship key.
12. Loaded the model using Close & Apply.

## Relationships

```text
DimProduct[SKU]  1 ─────── *  FactSupplyChain[SKU]

DimSupplier[Supplier name]  1 ─────── *  FactSupplyChain[Supplier name]
```

This produces a simple star-schema-style model with the operational data in the fact table and reusable product/supplier attributes in dimensions.

## Data Quality

The project used Power Query profiling to check validity, errors, and empty values before building the report.
