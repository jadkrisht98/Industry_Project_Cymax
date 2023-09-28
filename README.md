# Industry_Project_Cymax
Data Cleaning Script for the data related to the industry project I did with Cymax Group Technologies. 

Script Insights:

DATA CLEANING:

*Daily Sales:

•	Reorder column names

•	There is a -ve marketing cost (for 4 rows) ? why ? maybe a typo ! apply absolute value

•	Converting columns with date into ‘datetime’ data type

•	Put orders with zero quantity sold (orders with no products sold) in a separate table (these are SKUs browsed on amazon or Cymax owned websites but not bought so they just incur marketing cost, zero quality sold, zero gross sales)

•	 “PriceWalmart” , “PriceAmazon”, “PriceWebsite” are correlated by 99.6% so it is logical to have only one column with price, which makes sense since the products have the same prices across all platforms. Create a new “Price” column with the median price of all 3, this will solve the alleviate the missing price issue initially

•	Drop “IsAvailable” column since sold products are obviously available 

•	There are 39,075 rows with outliers (zscore >=3 or <=-3)  remove? not sure 

•	Replace missing price with the price from the product table

•	Added profit per unit 

•	Added profit column for each market place & total profit


*Campaigns:

•	Converting columns with date into ‘datetime’ data type

•	Column Status has different classes for the same meaning (['Active' 'removed' nan 'Paused' 'ACTIVE' 'PAUSED' 'Deleted'])  replace Accordingly

•	Campaigns with AccountID 0 or ‘”0” which represent NaN (to be confirmed)  replace with NaN

•	Make AccoutID more consistent (some NaN could be filled by referring to account name)

•	Drop column AccountStatus since its “Active” for all rows

•	Drop rows with product ID as zero since they are unknown SKUs

•	Drop idLocation, idCarrier since its zero for all rows

•	There is a -ve PPC cost (for 21 rows) ? why ? maybe a typo ! apply absolute value

•	convert date into datetime data type

•	“idSource” , “idPaymentType”, “IdBusinessChannel” are correlated by 98%

