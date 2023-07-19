# Handbook of the Business Growth

![banner](https://www.rapidhits.net/wp-content/uploads/2018/06/data-driven-advertising-850x350.jpg)
![banner](https://images.pexels.com/photos/185576/pexels-photo-185576.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2)

In the data era, there is an abundance of customer information and tools available to businesses in order to make informed business decision. In this handbook I followed a method to use customer data to grow a business using a combination of programming, data analysis, and machine learning.

---
## Table of Content
1. [ Data ](#data)
2. [ Step 1 - Key Performance Indicators ](#step1)
3. [ Step 2 - Customer Segmentation ](#step2)
4. [ Step 3 - Customer Lifetime Value ](#step3)
5. [ Step 4 - Predicting Customer's Next Purchase ](#step4)
6. [ Step 5 - A/B Testing ](#step5)


---
<a name="data"></a>
## Data
This is a transactional data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

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

---
<a name="step3"></a>
## Step 3 - Customer Lifetime Value

The Customer Lifetime Value is a metric that indicates the total revenue a business can reasonably expect from a single customer. For this, it considers the revenue generated by a customer, and compares it to the company's predicted customer lifespan. The higher the Customer Lifetime Value is, the greater the profits. Businesses have to allocate budget to acquire new customers and retain existing ones, but the former tend to be more cost-effective. Therefore, by knowing the Customer Lifetime Value, a business can work ond focus its efforts on improving it by retaining existing customers through email marketing, SMS marketing, social media marketing...

In this section, we are going to build a simple machine learning model that predicts the Customer Lifetime Value using the RFM scores we have calculated in *Step 2 - Customer Segmentation* and split the dataset into a 3 months dataset and use it for predicting the next 6 months.

### Calculate the RFM for 3 Months Customers and 6 Months Lifetime Value

The fisrt step is to define an appropriate time frame for Customer Lifetime Value calculation. For the purpose of this analysis we are going to use a 3 months RFM from March to June 2011 to predict the following 6 months Customer Lifetime Value. 

After calculating the RFM score for each customers, we calculate the 6 months customer Lifetime Value using the revenue generated by each customer as no cost are provided in the dataset.

![Six Months Revenue Histogram](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Customer%20Lifetime%20Value/Six%20Months%20Revenue%20Histogram.png)

We can see in the histogarm above that we have some customers generating negative Lifetime Value, we are going to filter them out before building the model.

![Lifetime Value vs Overall RFM Score](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Customer%20Lifetime%20Value/Lifetime%20Value%20vs%20Overall%20RFM%20Score.png)

In the plot above we can see a positive correlation between the revenue genarted and the RFM score, such that the higher the score the greater the revenue.

### Lifetime Value Segmentation

In order to give the business functions actional insights, we are going to classify our customers into Lifetime Value segments. Therefore, we are going to apply K-means clustering to identify 3 Lifetime Value groups:
* Low LTV
* Mid LTV
* High LTV

![df_cluster](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Customer%20Lifetime%20Value/df_cluster.png)

The table above shows that the most valuable segment is LTV_Clusters 2 with on average a Lifetime Value of £4,841.08 while the least valuable is LTV_Clusters 0 with an average Lifetime Value of £306.17.

### Feature Engineering

After changing the categorical feature into numical ones, we created a correlation matirx between each features and the Lifetime Value clusters.

![correl matrix](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Customer%20Lifetime%20Value/correl%20matrix.png)

We can see that 6 months Revenue, Frequency and RFM scores will be helpful in building the predictive model.

### Build the Customer Lifetime Value Predictive Model

To build the predictive model we used XGBoost library to do the classification.

![xgb_model](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Customer%20Lifetime%20Value/xgb_model.png)

Accuracy shows 78.5% accuracy on the test set which could be considered as a good score however, Low LTV cluster represents 76.5% of the total customers, so if the model was classifying all the customers in this cluster we would achieve 76.5% accuracy. Thus, whilst not perfect, the model still helps a bit in classifying the customers.

Also, the model only scores 93% accuracy on the training dataset, which indicate that the model should be improved by adding more features and improve feature engineering, try different models other than XGBoost, apply hyper parameter tuning to current model or add more data to the model if possible. 

---
<a name="step4"></a>
## Step 4 - Predicting Customer's Next Purchase

Since we now know the most valuable customers by segments and their predicted lifetime value, we can look into predicting customer's next purchase date.

Predicting when customers are going to purchase next gives a business the opportunity to implement an appropriate marketing strategy; knowing that a customer is going to take an order soon means that the business does not need to provide incentive to that customer, however if a purchase as not occured during the predicted period then the custoemrs should be targeted with marketing emails and offers to action an order.

### Data Wrangling

To build our model, we use nine months of behavioral data to predict customers’ first purchase date in the next three months. This will also take into account the customers that did not purchase. The goal is to find the number of days between the last purchase in the behavioral data and the first one in the next purchase data.

![NextPurchaseDay_table](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/NextPurchaseDay_table.png)

We have some NaN value sin our dataset therefore we are going to select only the rows where we can identify the customers.

We also have to deal with the customers that only purchased one and therefore returned a NextPurchaseDay = NaN, in this instance we cannot fill these with zero as it would skew the prediction nor can we drop them as some customers may purchase within the next 3 months. A way of dealing with NaN is to take a high value as we are working with a year (365 days) worth of data; we choose 999. This will allow us to quickly identify them later.

![NextPurchaseDay_without_NaN_table](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/NextPurchaseDay_without_NaN_table.png)

### Feature Engineering

In this part we are going to add the result of part 2 of this handbook, namely the RFM segmentation, as a feature for our model.

![customer_table](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/customer_table.png)

We then calculate the number of days for each customer’s next purchase.

![customer_table_with_npd](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/customer_table_with_npd.png)

![customer_description_npd](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/customer_description_npd.png)

The description above shows that median number of order is 4, therefore we are going to use as features the number of days between the last four orders:

![last_four_orders](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/last_four_orders.png)

We can now identify the classes in our label data, NextPurchaseDay. For this we are going to look at the percentiles:

![describe_nextdaypurchase](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/describe_nextdaypurchase.png)

Deciding the number of classes and their boundaries is a question for both statistics and business priorities and needs. Looking at the description above, we could split the data into three classes:
* Class 2 - customers will purchase again within 6 weeks (between 0 to 42 days) 
* Class 1 - customer will purchase again within 12 weeks (between 43 to 84 days)
* Class 0 - customer will purchase in more than 12 weeks

This split enables us to have the time to communicate the information across to the marketing team that can then plan to take action.
The last step is to plot the correlation between our features and label.

![correlation_table](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/correlation_table.png)

Looking at the matrix above, the highest positive correlation is with the Frequency Cluster (0.52) while Segment Low-Value has the highest negative correlation (-0.51).

### Selecting a Machine Learning Model

We first select our prediction target, NextDayPurchase, and store it in y. All the other features will be stored in X.
We then split the data into train and test sets

![train_test_split](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/train_test_split.png)

We are now going to use cross validation in order to find the most stable model for our data. It does it by providing the score of the model by selecting different test sets, the lower the deviation, the more stable the model is. For the purpose of this analysis we use two test sets and four models:
* Gaussian Naive Bayes: NB
* Random Forest Classifier: RF
* Decision Tree Classifier: Tree
* XGBoost Classifier: XGB

![results_cross_val](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/results_cross_val.png)

As we can see in the results above the lowest deviation is for the XGBoost and Random Forest classifiers. For the purpose of this analysis, we are going to select XGBoost classifier and use hyperparameter tuning to improve our accuracy score.

### Build the Model

We run the model a first time setting only the random state:

![first_model](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/first_model.png)

Our accuracy on the test set is 56% on the test set.

#### Hyperparameter Tuning

This process helps us choose the optimal values for the parameters of our model:

![hyperparameters](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/hyperparameters.png)

#### Final Model

We run the model using the parameters generated above:

![final_model](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/final_model.png)

We can see that our accuracy increased to 58%.

#### Create an output
We can now link the results back to a customer and create an output.

![ output](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/Predicting%20Customer's%20Next%20Purchase/output.png)

---
<a name="step5"></a>
## Step 5 - A/B Testing

In the last step we predicted customer's next purchase. In the event a customer does not purchase at that was predicted the business should has a strategy to ensure that this customer does not churn and recapture its interest and engagement with the company's products. A way of doing so it to incentivise customer to purchase by offering a coupon code. However, in order to assess if this strategy is working, we need to conduct an A/B test.

But first, we need to have clear objectives in mind. What we want to know is if customers who received a coupon code have a greater retention rate than the control group:
* Test Group → Offer → Higher Retention
* Control Group → No offer → Lower Retention

We could have also use the revenue as success metric but for the purpose of this analysis we are using retention as we are trying to prevent churn.

For the purpose of the analysis we are using the rfm data generated in Step 2. We select the customerIds and segment columns from dataset. 

![rfm_data](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/A:B%20Testing/rfm_data.png)

We then split the data into two test and control groups:

![control_test_groups](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/A:B%20Testing/control_test_groups.png)

Ideally, purchase count should be a Poisson distribution. There will be customers with no purchase and we will have less customers with high purchase counts.

![customer_distribution](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/A:B%20Testing/customer_distribution.png)

The chart above shows promessing results as the density of the test group’s purchase is better starting from 1. In order to assess if this is a result of the coupon code we are going to check if the upward trend in the test group is statistically significant and not a result of other factors.

First we need to formulate our null hypothesis, in this case: 
* *h0: the test and control groups have the same retention rate.*

We are going to use a t-test to perform hypothesis testing.

![t-test](https://github.com/mriffaud/Handbook-for-Business-Growth/blob/master/images/A:B%20Testing/t-test.png)

The results produced above show that the p-value is < 0.05, therefore we can reject the null hypothsesis.
