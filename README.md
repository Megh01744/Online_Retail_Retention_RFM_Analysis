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
***

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
***

Before starting the analysis, the data was cleaned for customer behaviour, retention and RFM analysis.

The cleaning process reduced the dataset from 541,909 to 392,692 transaction lines:

* 406,829 rows remained after removing missing Customer IDs
* 401,604 remained after removing exact duplicates
* 392,732 remained after excluding non-positive quantities
* 392,692 remained after excluding non-positive unit prices

CustomerID and InvoiceDate were converted into suitable formats, and Total_price was calculated as Quantity × UnitPrice.

## Executive Summary
***

The cleaned data contains 4,338 identifiable customers and 18,532 orders, generating £8.89 million in positive purchase revenue. Average order value was £479.56, while 65.58% of customers purchased more than once.

Revenue increased strongly from September to November, with November recording the highest complete-month revenue. The United Kingdom contributed 81.97% of total revenue, meaning the overall results mainly reflect UK customer activity.


### Business Overview Dashboard

<img width="1375" height="800" alt="Business Overview png" src="https://github.com/user-attachments/assets/8ca9afee-4ac9-4442-a3a4-6f0c73ee3658" />


### RFM Segmentation & Retention Risk: 



* **High-Value Active Customers**



  * Represented **18.23% of total customers**

  * Generated **£4.89 million (55.05% of positive revenue)**

  * Showed the **most recent purchasing activity and highest average purchase frequency**

  * Identified as the most valuable and consistently active segment



* **High-Value At-Risk Customers**



  * Total of **715 customers**

  * Contributed **£1.37 million in revenue**

  * Had an average recency of approximately **122 days**

  * Previously high value but showing less recent purchasing activity

  * Strong candidates for **targeted re-engagement campaigns**



* **Loyal Customers**



  * Contributed **18.60% of total revenue**

  * Showed recent and frequent purchasing behaviour

  * Represent a stable and reliable revenue base



* **Combined High-Value Segments (Active + Loyal + At-Risk)**



  * Accounted for roughly **50% of all customers**

  * Generated **89.07% of total revenue**

  * Indicate strong revenue concentration among high-value groups



* **At-Risk and Inactive Customers**



  * Represented **33.08% of total customers**

  * Contributed only **4.87% of revenue**

  * Show minimal recent engagement and low revenue impact

  * Suggest that re-engagement should be **selective and value-driven**


<img width="1377" height="778" alt="Customer segments   RFM" src="https://github.com/user-attachments/assets/83f6e985-97db-4eb2-b792-8e9a904d9cba" />


## Recommendations



Based on customer behavior, the following actions can be tested:



* **Encourage a second purchase within 60 days:** The median time to repeat purchase is ~50 days, so reminders and recommendations between 30–60 days may improve retention.



* **Protect High-Value Active Customers:** This group drives 55.05% of revenue. Maintain engagement through recognition, relevant communication, and early product access.



* **Prioritize High-Value At-Risk Customers:** These 715 customers generated £1.37M. Start with personalized win-back messages and product reminders before offering incentives.



* **Develop Potential Loyalists:** Encourage repeat purchases using bundles or complementary product suggestions.



* **Avoid broad discounts for inactive customers:** They form 33.08% of customers but only 4.87% of revenue, so focus on low-cost re-engagement first.



* **Measure impact:** Track second-purchase rate, 60-day repeat rate, reactivation rate, and incremental revenue, ideally against a control group.



