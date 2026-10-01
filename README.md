# Enterprise Data Reconciliation & CFO Dashboard

## Project
This project reconciles customer status history, raw transaction server logs, and EUR/USD daily exchange rates.

## What I did
1. Used a SQL `ROW_NUMBER()` window function to select each user's latest record and keep only the latest Active users.
2. Removed `ERROR` server-log rows.
3. Used vectorized Pandas Regex extraction to get Date, User ID, Product ID and EUR value.
4. Forward-filled missing exchange-rate values for weekend dates.
5. Merged transactions with exchange rates and the latest Active customer list.
6. Calculated USD revenue.
7. Built a monthly revenue view and a Top 5 customer view.

## Validation
- Raw log rows: 100,000
- ERROR rows removed: 5,098
- Clean transaction rows: 94,902
- Latest Active users: 14,183
- Final reconciled rows: 53,899
- Total USD revenue: $148,274,622.91

## Main files
- `Enterprise_Data_Reconciliation.ipynb` — completed notebook
- `cfo_dashboard.png` — dashboard image
- `final_reconciled_data.csv` — final merged data
- `monthly_revenue.csv` — monthly summary
- `top_5_customers.csv` — Top 5 customer summary

## Note
The final revenue view uses only customers whose latest database status is Active, as required by the assignment.
