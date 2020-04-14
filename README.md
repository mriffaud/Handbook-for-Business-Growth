# Handbook of the Business Growth

![banner](https://www.rapidhits.net/wp-content/uploads/2018/06/data-driven-advertising-850x350.jpg)

In the data area, there is an abundance of customer information and tools available to businesses in order to make informed business decision. In this handbook I followed a method to use customer data to grow a business using a combination of programming, data analysis, and machine learning.

## Table of Content
1. [ Data ](#data)
2. [ Step 1 - Key Performance Indicators ](#step1)


<a name="data"></a>
## Data
This is a transnational data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

The dataset is available on Kaggle: [E-Commerce Data](https://www.kaggle.com/carrie1/ecommerce-data)

The dataframe is composed of 541,909 rows and 8 features

#### Data Dictionary

* InvoiceNo: the invoice number
* StockCode: the stock code of the product
* Description: the description of the product
* Quantity: the number of items purchased
* InvoiceDate: the date the order has been invoiced
* UnitPrice: the price per item
* CustomerID: the unique customer ID
* Country: the country from which the order has been placed


<a name="step1"></a>
## Step 1 - Key Performance Indicators

The first step is to understand the main metrics the business wants to track, depending on the company’s product, position, targets & more. Most businesses already track their key performance indicators (KPIs) already. In this example, the main KPIs can be revenue related, such as the revenue, the average order value, the order frequency...

### Revenue by Country

![revenue by country](https://raw.githubusercontent.com/mriffaud/Handbook-of-the-Business-Growth/master/images/Revenue%20by%20Country.png?token=AKRWJIAHWZZMB6A7RC6RHOS6SXMQG)

United Kingdom is the region that generates most of the company's revenue. For the purpose of this analysis, we will focus on UK customers.

### Monthly Revenue

![Monthly Revenue]()

The chart above shows upward trend for the revenue generated up to the November 2011 (as the December data is incomplete). Up to August 2011, the business had a monthly revenue between 400K and 600K, since then, the business has seen its revenue dramatically increase reaching 1.2M in November 2011.

![Montly Growth Rate]()

September was an outstanding months with almost 60% growth compared with the previous month. November was also very good month with 46.2% growth. March and May are both up by more than 30% but this may be explain by the poor performance of the previous months.

January and April 2011 are poor performance months. We will have to investigate the data to understand why.

### Monthly Active Customers



