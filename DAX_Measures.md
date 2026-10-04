# DAX Measures

The following measures are used for the core Supply Chain dashboard KPIs.

## 1. Total Revenue

```DAX
Total Revenue =
SUM(FactSupplyChain[Revenue])
```

Calculates total generated revenue in the current filter context.

## 2. Total Products Sold

```DAX
Total Products Sold =
SUM(FactSupplyChain[Number of products sold])
```

Calculates total products sold.

## 3. Total Stock

```DAX
Total Stock =
SUM(FactSupplyChain[Stock Level])
```

Calculates total stock available in the current filter context.

## 4. Total Supply Chain Cost

```DAX
Total Supply Chain Cost =
SUM(FactSupplyChain[Supply Chain Cost])
```

Calculates total supply-chain cost.

## 5. Average Lead Time

```DAX
Average Lead Time =
AVERAGE(FactSupplyChain[Lead Time])
```

Calculates the average supplier/operational lead time represented by the `Lead Time` field.

## 6. Average Defect Rate

```DAX
Average Defect Rate =
AVERAGE(FactSupplyChain[Defect rates])
```

Calculates the average defect rate.

## Notes

All measures are designed to respond to the current filter context in Power BI.

Additional visual-level aggregations are used directly in charts where appropriate, such as totals or averages by product, supplier, carrier, route, or transportation mode.
