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

The initial review found:

* 135,080 rows without a Customer ID
* 1,454 missing product descriptions
* 5,268 exact duplicate rows
* 10,624 rows with non-positive quantities
* 2,517 rows with non-positive unit prices
* 9,288 cancelled invoice rows

### Final Analysis Data

Two datasets were used in the final analysis:

* **Cleaned transactions:** 392,692 product-level transaction lines and 10 columns
* **RFM customer segments:** 4,338 customer-level records and 9 columns

The cleaned transaction data contains `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`, `Total_price` and `Customer_Type`.

The RFM data contains `CustomerID`, `Recency`, `Frequency`, `Monetary`, `R_Score`, `F_Score`, `M_Score`, `RFM_Score` and `Segment`.


## Data Cleaning & Validation

Before starting the analysis, the data was cleaned for customer behaviour, retention and RFM analysis.

The cleaning process reduced the dataset from 541,909 to 392,692 transaction lines:

406,829 rows remained after removing missing Customer IDs
401,604 remained after removing exact duplicates
392,732 remained after excluding non-positive quantities
392,692 remained after excluding non-positive unit prices

CustomerID and InvoiceDate were converted into suitable formats, and Total_price was calculated as Quantity × UnitPrice.






