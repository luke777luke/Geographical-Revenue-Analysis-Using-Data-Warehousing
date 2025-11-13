# Geographical-Revenue-Analysis-Using-Data-Warehousing

# Data Warehouse Business Process
Using the SAP bike company dataset, the CEO of the associated company is interested in knowing which geographical location they should consider spending more resources on marketing towards. In particular, they are interested in knowing where most of their revenue is coming from as well as whether each geographical location (in this case America or Europe) changes their spending habits over periods of time.

# Grain of FACT table 
"The grain of the fact table is at the transaction level involving the purchasing of unique orders for bikes and bike accessories that occurred within a given time period from all customers regardless of location." At this level of grain, we can be able to determine to whom each order belongs to, when it was processed, and where the order is being placed from.

# Facts and Dimensions Fact Table 
(OrderNumber, SalesQuantity,ProductId, Date, CustomerId) 
Contains foreign keys that connects to the dimension tables and aggregate values.
Dim_Time(Date,Year,Month,Day) 
Contains information on the dates per each order as well as individual measures of time like year and month. This table will allow us to see when customers are more likely to place orders and if there are variations among Europeans and Americans. 
Dim_Product(ProductId,ProdDescr,CatDescr,Division) 
Contains information on item purchased to see which ones are most often to appear within orders placed. 
Dim_Customer (CustomerId,Customer_Desc,Currency) 
Shows information regarding each customer and which geographical location they placed the order from using the value of “Currency”. 
Dim_Order (OrderNumber,Date,CustomerId) 
Shows order information, the time it was placed, and the customer who placed it.

# Discussion 
After creating the fact table and dimension tables, the resulting data was illustrated using several graphs. As it turns out, there are slightly more customers residing in European countries however this difference is too small to be significant. The label “Currency” was used in order to determine the geolocation of where the order was placed (Europe or America). When looking at the total items purchased over time and dividing these results by currency, we can see that regardless of the time period, European customers place more orders than US customers do. In fact, 2008 and 2009 were two years were a substantially small number of orders was placed by US customers. In comparison, those years remained stable for European countries. When looking at individual customers, grouped by geolocation, and observing the number of items purchased among each, we can see that there is at least one US customer and one European customer who buys substantially more items than the rest. This could result in results being skewed. However, observing the other customers we can see that most US customers place similar amounts of orders, while European customers are more varied. Regardless, it would be advised to market more towards European customers in order to generate higher levels of revenue. It’s not because there are more European customers nor is it because European customers individually purchase more than US customers. It is because, when looking a te total number of sales, Europe always has an advantage over the US regardless of the year.

# Software/Programs Used
Python (including Pandas and SQLite) was used to read in original datasets and SQLite was used to create tables out of these datasets. Based on the desired Fact and Dimension tables attributes, SQLite was then used to create views of the original tables. These views were then converted in new csv files. These csv files were then placed into Tableau to create the graphs.
