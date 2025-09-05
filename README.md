# Data Mining for Online Retail Transactions data

## Overview
This notebook represents a case study of using data mining techniques for customer-centric business intelligence for an online retailer. This is presented to help the business better understand its customers, including:
- Who are the most/least valuable customers to the business? What are the distinct characteristics of them?
- Who are the most/least loyal customers, and how are they characterized?
- What are customers’ purchase behaviour patterns? Which products/items have customers purchased together often? In what sequence were the products purchased?
- What are the sales patterns in terms of various perspectives such as products/items, regions, and time (weekly, monthly, quarterly, yearly, and seasonally), and so on?

## Description
The workflow includes:
- Feature engineering and cleansing, including negative values, gift transactions, and cancelled orders.
- EDA to answer business objectives above and action plans for the CRM team
- **Apriori / Cross-basket Analysis** of 1,000 most frequent items
- **RFM** is a way to segment customers based on their purchase behavior. There are 3 parameters to use:
  - *Recency*: When was the last time the customer purchased vs. today/reference date?
  - *Frequency*: Within a certain period (e.g. 1 year), how many purchases did the customer make?
  - *Monetary*: Within a certain period (e.g. 1 year), how much money did the customer spend?
- Calculate the overall RFM Score; we utilize **PCA**
- Calculate CLV using **Kaplan-Meier** to predict churn (Survival Analysis)
- Clustering using **K-Means++, DBScan**
- Evaluate the clustering result using the **Silhouette score**

## Dataset
The [Online Retail dataset from UCI](https://archive.ics.uci.edu/dataset/352/online+retail) is a transactional data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.
Variable information:
- **InvoiceNo**: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation. 
- **StockCode**: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.
- **Description**: Product (item) name. Nominal.
- **Quantity**: The quantities of each product (item) per transaction. Numeric.	
- **InvoiceDate**: Invoice Date and time. Numeric, the day and time when each transaction was generated.
- **UnitPrice**: Unit price. Numeric, Product price per unit in sterling.
- **CustomerID**: Customer number. Nominal, a 5-digit integral number uniquely assigned to each customer.
- **Country**: Country name. Nominal, the name of the country where each customer resides. 

## Result
- Silhouette score for:
  - DBScan: 0.9093102308410241
  - K-Means++ 0.6170356103586038

## Quick Start
- Clone this repository: git clone https://github.com/ignsagita/data-mining_online-retail.git cd data-mining_online-retail
- Install dependencies pip install -r requirements.txt
- Run the notebook: jupyter notebook data-mining_online-retail.ipynb

---
