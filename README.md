## Project Background
***

The business represented in the UCI Online Retail dataset is a UK-based, registered non-store retailer that mainly sells unique all-occasion gifts. Many of its customers are wholesalers. The dataset records transactions between 1 December 2010 and 9 December 2011.

The company has a large volume of transaction data covering customer purchases, products, quantities, prices, order dates and customer countries. This project analyses and brings these records together to understand repeat purchasing, monthly customer retention, time to second purchase, revenue concentration and differences across RFM customer segments. The findings highlight practical opportunities for customer engagement, second-purchase campaigns and targeted re-engagement.

Sales show what customers bought, but not whether they returned or which customers generated the most revenue. This project explores repeat purchasing, cohort retention, time to second purchase, revenue concentration and RFM segments.

Each row represents one product within an invoice and includes:

- Invoice and product details
- Quantity and unit price
- Transaction date and time
- Customer ID
- Customer country

The analysis focuses on three key areas:

- **Repeat Purchasing and Retention:** Repeat-customer behavior, monthly cohorts and time to second purchase.
- **Customer Value and Segmentation:** Revenue concentration and differences across RFM segments.
- **Revenue Patterns:** Monthly performance, order values and country-level contribution.

  The interactive Power BI dashboard can be downloaded [here.](https://raw.githubusercontent.com/Megh01744/Online_Retail_Retention_RFM_Analysis/refs/heads/main/Online_Retail_Retention_RFM_Dashboard.pbix)
  
  The Python analysis notebook can be viewed [here](notebooks/01_Online_Retail_Customer_Retention_and_RFM_Analysis.ipynb).

  The SQL analysis notebook can be viewed [here](notebooks/02_Online_Retail_SQL_Analysis.ipynb).

## Data Structure & Initial Checks

The original dataset contains **541,909 transaction lines and 8 columns**. Each row represents one product recorded within an invoice.

Initial checks identified the following issues:

| Data-quality issue           | Records |   
| ---------------------------- | ------: |
| Missing Customer IDs         | 135,080 |
| Missing product descriptions |   1,454 |
| Exact duplicate rows         |   5,268 |
| Non-positive quantities      |  10,624 |
| Non-positive unit prices     |   2,517 |
| Cancelled invoice rows       |   9,288 |

### Final Analysis Tables

| Dataset               | Each row represents                |    Rows | Columns |
| --------------------- | ---------------------------------- | ------: | ------: |
| Cleaned transactions  | One positive-purchase product line | 392,692 |      10 |
| RFM customer segments | One identifiable customer          |   4,338 |       9 |

The cleaned transaction table contains `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`, `Total_price` and `Customer_Type`.

The RFM table contains `CustomerID`, `Recency`, `Frequency`, `Monetary`, the three component scores, `RFM_Score` and `Segment`.






