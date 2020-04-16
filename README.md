# Handbook of the Business Growth

![banner](https://www.rapidhits.net/wp-content/uploads/2018/06/data-driven-advertising-850x350.jpg)

In the data area, there is an abundance of customer information and tools available to businesses in order to make informed business decision. In this handbook I followed a method to use customer data to grow a business using a combination of programming, data analysis, and machine learning.

---
## Table of Content
1. [ Data ](#data)
2. [ Step 1 - Key Performance Indicators ](#step1)
3. [ Step 2 - Customer Segmentation ](#step2)

---
<a name="data"></a>
## Data
This is a transnational data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

The dataset is available on Kaggle: [E-Commerce Data](https://www.kaggle.com/carrie1/ecommerce-data)

The dataframe is composed of 541,909 rows and 8 features

![data](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/data/data.png)

#### Data Dictionary

* InvoiceNo: the invoice number
* StockCode: the stock code of the product
* Description: the description of the product
* Quantity: the number of items purchased
* InvoiceDate: the date the order has been invoiced
* UnitPrice: the price per item
* CustomerID: the unique customer ID
* Country: the country from which the order has been placed

---
<a name="step1"></a>
## Step 1 - Key Performance Indicators

The first step is to understand the main metrics the business wants to track, depending on the company’s product, position, targets & more. Most businesses already track their key performance indicators (KPIs) already. In this example, the main KPIs can be revenue related, such as the revenue, the average order value, the order frequency...

### Revenue by Country

![revenue by country](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Revenue%20by%20Country.png)

United Kingdom is the region that generates most of the company's revenue. For the purpose of this analysis, we will focus on UK customers.

### Monthly Revenue

![Monthly Revenue](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20Revenue.png)

The chart above shows upward trend for the revenue generated up to the November 2011 (as the December data is incomplete). Up to August 2011, the business had a monthly revenue between 400K and 600K, since then, the business has seen its revenue dramatically increase reaching 1.2M in November 2011.

![Montly Growth Rate](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Montly%20Growth%20Rate.png)

September was an outstanding months with almost 60% growth compared with the previous month. November was also very good month with 46.2% growth. March and May are both up by more than 30% but this may be explain by the poor performance of the previous months.

January and April 2011 are poor performance months. We will have to investigate the data to understand why.

### Monthly Active Customers

![Monthly Active Customers](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20Active%20Customers.png)
![Montly Active Customers Rate](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Montly%20Active%20Customers%20Rate.png)

In January the company lost almost 200 customers, going from 871 in December to 684 in January which represents -21.47% decrease. Similarly, in April the business went from 923 customer to 817 which represents a decrease of 11.48%.

### Monthly Order Count

![Monthly Orders](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20Orders.png)
![Monthly Orders Rate](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20Orders%20Rate.png)

The number of orders has been decreasing between December and February going from 1,885 to 1,259 orders representing -33.21% decrease. The orders went up until May growing by 56.71%. The orders dropped again until August by -27.72% and finally took up to November by 50.34%.

### Average Order Value

![Monthly AOV](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20AOV.png)
![Montly AOV Rate](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Montly%20AOV%20Rate.png)

Between December and April the company's AVG lost 24.05%, it went back up until September going from £272.66 in April to £412.45 in September which represents an increase of 51.27%. the month of October registered a decrease (-9.89) to go back to almost the AVG as September's one in November (£412.08 which represents 10.88% increase compared with October's AVG.

### New Customer Ratio

A new customer is a customers that purchased for the first time within a period of time defined by the business. For the purpose of this analysis, a new customer is the first time a customerID appears in the dataset, this means that all the customers for December 2010 will be classed as new customers.

![Monthly New Customer Ratio](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20New%20Customer%20Ratio.png)

As expected the new customer ratio declines over the year as we assumed that all the customers in December 2010 were new ones. (we assumed on Feb, all customers were New). For the last six months of the year, the new customer ratio is of about 20%.

### New Customer vs Existing Customer Revenue

![New Customer vs Existing Customer Revenue](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/New%20Customer%20vs%20Existing%20Customer%20Revenue.png)

We can see on the chart above that the new customers' revenue decreases as time goes on, this may be because we only have a year worth of data. However the existing customer shows a positive trend which suggests that the business retains most of its customers.

### Retention Rate

Retention rate the percentage of customers a business has retained over a given time period. It is a very important KPI and should be monitored very closely because it indicates how good of a job the marketing and sales teams are doing. It is also cost effective to focus on keeping the retention rate up because it requires more time, money and effort to convince and convert someone new to make a purchase or sign up for a services rather than keeping your existing customers that already know the business.

Fot the purpose of this analysis, we are going to calculate the monthly retention rate.

![Monthly Retention Rate](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Monthly%20Retention%20Rate.png)

Overall the retention rate is good with the highest rate at 47% in January and the lowest at 33% in February. The three best months in term of customer retention are January, June and August. Over the 11 months, the rentention rate is 42%.

### Retentention by Cohort

A cohort retention analysis help understand how many customers return after a defined period of time.

![Customers Cohorts Retention](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/KPIs/Customers%20Cohorts%20Retention.png)

Ove the year the company retained 27% of its customers.

---
<a name="step2"></a>
## Step 2 - Customer Segmentation

With the most important metrics tracked and monitored, we can now focus on segmenting the customers. Customer segmentation is the process of grouping customers with common characteristics into homogenous groups. This allows businesses to target consumers with specific needs, use its resources more effectively and make better strategic marketing decisions.

For the purpose of this analysis, we are using the RFM (Recency - Frequency - Monetary) method to segment the customers into groups on their business value:
* Low Value: Customers who are less active than others, not very frequent buyer/visitor and generates very low maybe negative revenue.
* Mid Value: In the middle of everything. Often using our platform (but not as much as our High Values), fairly frequent and generates moderate revenue.
* High Value: The group we don’t want to lose. High Revenue, Frequency and low Inactivity.

### Calculate Recency

The recency shows how recently a customer has made a purchase. Thus, we need to extract the last invoice date for each customer and then calculate the number of day they have been inactive.

![recency](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/recency.png)

Although the average number of day since last purchase is 90, the median is 49 this means that the data is spread.

Now, we are going to apply K-means clustering to assign a recency score. We are using a for loop to test different k-estimators and plot them in an inertia graph to select the optimal number of cluster.

![inertia graph](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/inertia%20graph.png)

Looking at the graph above, the optimal number of cluster is 3, therefore we are going to apply 3 recency clusters.

![recency clusters](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/recency%20clusters.png)

The table above shows the different characteristics of each clusters we have generated. The customers in Cluster 2 are the most recent customers with on average 30 days recency while cluster 1 and 2 have on average 153 and 294 days recency respectively. The customers in cluster 2 are more recent compared with cluster 1 and 0.

### Calculate Frequency

We follow the same process as for the recency clustering but this time extracting the total number of orders for each customer.

![Frequency](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/Frequency.png)

On average customers pass 5 orders, however this is inflated by customers taking a lot of small orders.

![Frequency Inertia Graph](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/Frequency%20Inertia%20Graph.png)

The optimal number of frequency cluster is 4.

![Frequency clusters](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/Frequency%20clusters.png)

The table above shows that customers in Cluster 0 pass on average 3 orders while cluster 1, 2 and 3 have 14, 45 and 151 orders respectively. Cluster 3 has a higher order frequency meaning that customers pass more orders and therefore are better value compared with the other clusters.

### Calculate Revenue

Now we are going to repeat the process for the revenue for each customer, plot a histogram and apply the clustering method.

![revenue](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/revenue.png)

The histogram shows some customers generating negative revenue, this is because our dataset contains returns. The average revenue generated by a customer is £1,713.39. However, the median is £627.06, this means that the revenue is very spread accross the customers.

![Revenue Inertia Graph](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/Revenue%20Inertia%20Graph.png)

Looking at the graph above, are going to take 3 clusters.

![revenue_clusters](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/revenue_clusters.png)

The table above shows that cluster 0 generate less revenue than the other clusters, 2 being the most revenue generating cluster.

### RFM Segmentation

Now that we have the scores for recency, frequency and revenue, we can calculate a general score using the average of each of clusters for each customers.

![OverallScore](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/OverallScore.png)

The table above shows that the customers in OverallScore 4 are more valuable than customers in OverallScore 0. In order to keep in line with the business requirements laid out at the biginning of *Step 2 - Customer Segmentation*, we are going to classify the scores as follow:
* 0 : Low Value
* 1 and 2: Mid Value
* 3 and 4: High Value

![3d plot](https://github.com/mriffaud/Handbook-of-the-Business-Growth/blob/master/images/RFM%20Segmentation/3d%20plot.png)

With this simple RFM segmentation, we can support marketing to make informative strategic decisions. In this instance:
* High Value: improve Retention and Frequency
* Mid Value: improve Retention and Frequency
* Low Value: increase Frequency

