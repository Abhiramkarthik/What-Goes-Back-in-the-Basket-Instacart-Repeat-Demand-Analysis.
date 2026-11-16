# Initial data quality audit

This first pass streams the three source CSVs in chunks of 250,000 rows. It records row counts, missing values, and numeric ranges without loading the full prior-order file into memory.

| File | Rows | Missing values | Numeric range checks |
|---|---:|---|---|
| `orders.csv` | 3,421,083 | `days_since_prior_order`: 206,209 | `order_dow`: 0–6; `order_hour_of_day`: 0–23; `order_number`: 1–100; `days_since_prior_order`: 0–30 |
| `order_products__prior.csv` | 32,434,489 | None | `reordered`: 0–1; `add_to_cart_order`: 1–145; IDs are positive and within the product/order ranges |
| `products.csv` | 49,688 | None | `aisle_id`: 1–134; `department_id`: 1–21; `product_id`: 1–49,688 |

The missing `days_since_prior_order` values are consistent with a customer's first order, where there is no earlier order to measure from. We will preserve these as missing rather than replacing them with zero.

Duplicate-key checks found no repeated `order_id` values, no repeated `product_id` values, and no repeated `(order_id, product_id)` pairs in the prior-order file. Every prior-order row matched an order and a product in the other files.

This initial audit is complete. The data is structurally consistent for the planned joins. The missing `days_since_prior_order` values should remain blank; they represent orders without a previous order interval.
