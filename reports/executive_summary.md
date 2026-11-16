# Executive summary: The Grocery Store That Ran Out First

## Objective

Identify historical grocery products and categories with strong repeat demand so a retailer could prioritize them for closer replenishment monitoring.

## Data and method

The analysis used Instacart's prior-order history: 32,434,489 product-order rows linked to order, product, aisle, and department attributes. The audit found no duplicate order IDs, product IDs, or order-product pairs, and no broken product/order links. The only missing values were `days_since_prior_order` on first customer orders.

Product reorder rates were calculated as reorder rows divided by all product-order rows. A historical monitoring shortlist included products with at least 1,000 order rows that also ranked in the top quartile for both volume and reorder rate. Basket associations were assessed among the 20 most frequently ordered products, with lift used to account for individual product popularity.

## Key findings

- **Repeat purchasing:** 59.0% of product-order rows in the prior file are marked as reorders.
- **High-volume staple:** Banana was the most frequently ordered product, with 472,565 rows and an 84.4% reorder rate.
- **Category demand:** Produce led departments with 9.48 million product-order rows. Fresh fruits led aisles by volume with 3.64 million rows.
- **Repeat-heavy category:** The milk aisle had a 78.1% reorder rate across 891,015 rows.
- **Time pattern:** 10:00 was the busiest hour for order and product-line volume. 22:00 had the largest average basket at 11.03 product lines per order, despite much lower overall order volume.
- **Customer cadence:** 50.4% of recorded intervals between orders fell within 0–7 days; 17.2% fell within 22–30 days.
- **Basket association:** Organic Yellow Onion and Organic Garlic had a lift of 5.70 across 22,073 baskets. Bag of Organic Bananas and Organic Hass Avocado were the most common tested pair, appearing in 62,341 baskets.
- **Monitoring shortlist:** 485 products met the high-volume and high-reorder thresholds.

## Recommendation

Use the 485 products as a screening list for inventory review. Combine these historical demand signals with actual on-hand inventory, supplier lead times, and stockout records before setting replenishment rules.

## Limitations

This dataset does not include inventory levels, confirmed stockouts, physical quantities, product costs, or promotions. Product-order rows are not units sold. The project identifies descriptive patterns, not causal effects or an operational stockout forecast. Pair analysis is limited to the top 20 products by order volume. Weekday codes have not been mapped to names because available dataset mirrors give inconsistent mappings.

## Resume bullet

Analyzed 32.4M grocery product-order records with Python and pandas; identified repeat-demand patterns across products and departments and created a 485-product replenishment-monitoring shortlist, including a co-purchase analysis with a 5.70 lift association.
