# First analysis: repeat-demand signals

Reorder rate is calculated as `reorder_count / times_ordered`. Here, `times_ordered` counts product-order rows in the prior-order file, not unique customers. We rank only products with at least 1,000 product-order rows to reduce small-sample noise.

## Findings

- Among products with at least 1,000 order rows, **Half And Half Ultra Pasteurized** has the highest reorder rate: **86.2%** across 2,921 product-order rows.
- **Banana** is the most frequently ordered product: **472,565** product-order rows, with an **84.4%** reorder rate.
- **Bag of Organic Bananas** is second by volume: **379,450** rows, with an **83.3%** reorder rate.

## Interpretation

Repeat demand and total order volume highlight different inventory signals. High reorder rate suggests habitual repurchasing; high order volume indicates broad demand. A retailer could use both to prioritize products for closer monitoring.

These are historical sample patterns, not future forecasts. The dataset contains no inventory counts or stockout events, so it cannot show whether a product actually ran out.
