E-Commerce SQL Analysis
SQL analysis of 800,000+ e-commerce transactions using a star schema database. The project covers customer behavior, product performance, store metrics, and time-based revenue trends — with Tableau visualizations for each analysis.
Tools & Skills
PostgreSQL — querying a multi-table star schema
DBeaver — query execution and result export
Tableau Public — data visualization
Techniques: JOIN (up to 4 tables), GROUP BY, HAVING, aggregate functions, ORDER BY, LIMIT, subqueries

Database Schema

fact_table
 customer_dim   (coustomer_key)
 store_dim      (store_key)
 item_dim       (item_key)
 time_dim       (time_key)
 trans_dim      (payment_key)

Analyses
1. Top 10 Customers by Revenue
Business question: Who are our most valuable customers?
Key findings:
Top customer C004349 spent $17,105 across 39 orders
Top 10 customers show consistent order frequency (38–39 orders each)
Average order value ranges from $113 to $137, suggesting stable pricing behavior
High-value customers are distinguished by order frequency, not just order size
 Visualization: TOP_customers.png
 Data: top_customers_csv.csv
2. Store Performance — Average Transaction Value
Business question: Which stores have the highest-value transactions?
Key findings:
S00266 leads with an average transaction of $111,337
Top 10 stores are tightly clustered between $105K–$111K, indicating consistent pricing across locations
The narrow spread suggests product mix rather than pricing drives store differentiation
 Visualization: Top_Stores.png
 Data: store_performance_csv.csv
3. Top 15 Products by Revenue
Business question: Which products drive the most revenue?
Key findings:
I00061 is the clear revenue leader at $1,305,700
Top 4 products (I00061, I00115, I00119, I00116) each exceed $1,100,000
Revenue drops significantly after the top 8, suggesting a classic 80/20 distribution
Inventory and marketing efforts should be concentrated on top-tier items
 Visualization: TOP_Products.png
 Data: product_performance_csv.csv

4. Revenue & Transaction Trends Over Time
Business question: How do sales fluctuate over time?
Key findings:
Revenue peaks at $2,461 (period T030980) with a corresponding transaction spike
Several periods show high revenue but low transaction count — indicating high-value single purchases
Volatility is significant throughout, with revenue ranging from ~$265 to $2,461
Transaction count and revenue are loosely correlated but not perfectly aligned
 Visualization: Revenue & Transaction Trends Over Time.png
 Data: TIME_TRENDS_CSV.csv

5. Customer Shopping Patterns — Multi-Table JOIN
Business question: How do customers shop across different stores and payment methods?
Complex query joining 4 tables: fact_table, customer_dim, store_dim, trans_dim
Key findings:
S00460 generates the highest revenue per customer interaction ($1,676)
Card is the dominant payment method across all store-customer combinations
Top interactions are concentrated in a small subset of store-customer pairs
The HAVING > $100 filter isolates meaningful transactions from noise
 Visualization: TOP_rev_Stores.png
 Data: MULTI_TABLE_JOIN_csv.csv

---
Author
Yevhenii — Data Analyst  
