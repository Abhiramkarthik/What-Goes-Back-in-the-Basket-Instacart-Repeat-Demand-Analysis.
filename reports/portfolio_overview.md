# Portfolio overview

## Business question
Which products show strong repeat demand and deserve closer replenishment monitoring?

## Findings
- The prior-order table contains 32,434,489 product-order rows; 59.0% are marked as reorders.
- Produce is the highest-volume department, with 9.48 million product-order rows.
- Banana is the most frequently ordered product (472,565 rows), with an 84.4% reorder rate.
- The highest-volume pair among the top 20 products is Bag of Organic Bananas + Organic Hass Avocado (62,341 baskets).
- Organic Yellow Onion + Organic Garlic has the strongest association among tested pairs (lift 5.70; 22,073 baskets).
- The product monitoring shortlist includes 485 products above the 75th-percentile cutoffs for both volume and reorder rate.

## Recommendation
Use high order volume and high reorder rate together to prioritize a replenishment review. Validate the shortlist against real inventory and stockout records before treating it as an operational forecast.

## Limitation
This dataset records sampled historical purchases, not inventory, shelf availability, physical quantities, or confirmed stockouts. Product-order rows are not units sold. Findings describe demand patterns and associations, not causation.

See `portfolio_overview.png` for the combined charts and the individual analysis files in this folder.
