# **UML-Capston_Project-Customer_Segmentation**

## *Introduction*
Customer segmentation is the process of separating customers into groups on the basis of their shared behavior or other attributes. The groups should be homogeneous within themselves and should also be heterogeneous to each other. The overall aim of this process is to identify high-value customer base i.e. customers that have the highest growth potential or are the most profitable.

Insights from customer segmentation are used to develop tailor-made marketing campaigns and for designing overall marketing strategy and planning.

A key consideration for a company would be whether or not to segment its customers and how to do the process of segmentation. This would depend upon the company philosophy and the type of product or services it offers. The type of segmentation criterion followed would create a big difference in the way the business operates and formulates its strategy. This is elucidated below:
  1. Zero segment (Undifferentiated approach)
  2. One segment (Focused approach)
  3. Two or more segments (Differentiated approach)
  4. Thousands of segments (Hyper segmentation approach)

Once the company has identified its customer base and the number of segments it aims to focus upon, it needs to decide the factors on whose basis it will decide to segment its customers.

**Factors for segmentation for a business to business marketing company:**
  1. Industry
  2. Number of employees
  3. Location
  4. Market cap/Company size
  5. Age of the company
  
**Factors for segmentation for a business to consumer marketing company:**
  1. Demographic: Age, Gender, Education, Ethnicity, Income, Employment, hobbies, etc.
  2. Recency, Frequency, and Monetary: Time period of the last transaction, the frequency with which the customer transacts, and the total monetary value of trade.
  3. Behavioral: Previous purchasing behavior, brand preferences, life events, etc.
  4. Psychographic: Beliefs, personality, lifestyle, personal interest, motivation, priorities, etc.
  5. Geographical: Country, zip code, climatic conditions, urban/rural areal differentiation, accessibility to markets, etc.
    
## ***Reason for Customer Segmentation***
Customer segmentation has a lot of potential benefits. It helps a company to develop an effective strategy for targeting its customers. This has a direct impact on the entire product development cycle, the budget management practices, and the plan for delivering targeted promotional content to customers. For example, a company can make a high-end product, a budget product, or a cheap alternative product, depending upon whether the product is intended for its most high yield customers, frequent purchasers or for the low-value customer segment. It may also fine-tune the features of the product for fulfilling the specific needs of its customers.

Customer segmentation can also help a company to understand how its customers are alike, what is important to them, and what is not. Often such information can be used to develop personalized relevant content for different customer bases. Many studies have found that customers appreciate such individual attention and are more likely to respond and buy the product. They also come to respect the brand and feel connected with it. This is likely to give the company a big advantage over its competitors. In a world where everyone has hundreds of emails, push notifications, messages, and ads dropping into their content stream, no one has time for irrelevant content.

Finally, this technique can also be used by companies to test the pricing of their different products, improve customer service, and upsell and cross-sell other products or services.

## ***Data Attributes***
* *InvoiceNo:* Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation.
* *StockCode:* Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.
* *Description:* Product (item) name. Nominal.
* *Quantity:* The quantities of each product (item) per transaction. Numeric.
* *InvoiceDate:* Invoice Date and time. Numeric, the day and time when each transaction was generated.
* *UnitPrice:* Unit price. Numeric, Product price per unit in sterling.
* *CustomerID:* Customer number. Nominal, a 5-digit integral number uniquely assigned to each customer.
* *Country:* Country name. Nominal, the name of the country where each customer resides.

## ***Diagnosing the DataFrame***
By diagnosing our data frame, we got the following:
  1. There are 8 features with 5,41,909 rows of data.
  2. There are 5 categorical columns and 3 numerical columns.
  3.Columns ‘Quantity’ is of *‘int64’* data type.
  4. Columns 'InvoiceNo', 'StockCode', 'InvoiceDate' and 'Country' are of *object* data type
  5. Columns 'UnitPrice' and 'CustomerID' are of *float64* data type

## ***Exploratory Data Analysis***
### *1. Unit Price Column*
  1. Minimum UnitPrice:                                     - 11062.06
  2. Maximum UnitPrice:                                     13541.33
  3. Mean:                                                  3.862
  4. Median:                                                2.08
  5. Standard deviation:                                    41.964
  6. % of data where UnitPrice is zero:                     0.48%
  7. Number of unique customers with unit price as zero:    31

### *2. Quantity Column*
  1. Minimum Quantity: 1
  2. Maximum Quantity: 80995
  3. Mean: 10.617
  4. Median: 4
  5. Standard Deviation: 156.28

### *3. Country v/s % of Customers*
![image](https://user-images.githubusercontent.com/98649231/178128101-7dc0b958-35d3-4343-8308-5f1cab8bf61d.png)
  1. Most of the customers are from UK.
  2. Followed by Germany and France.
  3. After France, the % tends to zero.

### *4. Country v/s % of total sales*
![image](https://user-images.githubusercontent.com/98649231/178128156-7f79259e-197f-4c5f-99b2-d56c76263462.png)
  1. Most of the sales are from UK.
  2. Followed by Netherlands, EIRE, Germany, France and Australia.
  3. After Australia, the sales % tends to zero.

## ***RFM Analysis***
RFM is a data modeling method used to analyze customer value It stands for Recency, Frequency and Monetary, which are just three metrics that describe what your customers did.
  * Recency (R) of a customer - Days since the last purchase
  * Frequency (F)     of the bookings/turnover of a customer - Number of purchases, e g in 6 months
  * Monetary (M) - The total turnover of a customer Sum of sales, e g in 6 months

For the analysis, we need to define a ‘analysis date’, which is the day on which we are conducting this analysis which I am taking as the next to last date in data and taking 1 year previous data from the selected date for recency calculation.
