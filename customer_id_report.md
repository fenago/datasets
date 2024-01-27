
# Customer ID Report

Based on the analysis of the `df_customers` DataFrame, we have the following findings regarding the `customer_id` and `customer_unique_id` columns:

- `customer_id` has a one-to-one correspondence with rows in the DataFrame, with each `customer_id` being unique to a row. This suggests that `customer_id` is likely to be a transaction-specific identifier.
- `customer_unique_id` has fewer unique entries than the total number of rows. This implies that the `customer_unique_id` is not unique to each row and likely represents a higher-level identifier that can span across multiple transactions for a single customer.

## Recommendations for Use

- Use `customer_id` to reference individual transactions or interactions when defining relationships to other tables that require a unique transaction-level identifier.
- Use `customer_unique_id` when analyzing customer-level behavior across multiple transactions. This identifier can be used to join with other tables that contain customer-specific information across different transactions or interactions.

## Conclusion

The `customer_id` should be used as a foreign key in transaction-level tables, while the `customer_unique_id` should be utilized for customer-level analysis and relationships in the database schema.
