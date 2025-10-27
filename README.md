PROCESS:
This project is based upon the adventureworks schema + tables. The goal of this project was to build an ETL pipeline that moved data from JSON files to MongoDB to MySQL. To prove functionality I ran SQL queries at the end of this pipeline.

1.Extract:
For this step, I loaded my JSON files into mongoDB collections. Then I was able to retrieve these collections using pandas dataframes.

2.Transform:
For this step, I cleaned and standardized my data by renaming columns, adding surrogate keys, dropping null columns, and fixing date-time format in columns. I also used dim_date to assign date keys for order dates, due dates, and ship dates in the fact tables. Finally, I merged the dataframes to include foreign keys between the fact and dimension tables.

3.Load:
For this step, I first loaded the dim_customers, dim_employees, dim_products, and dim_vendors tables. Later, I loaded the fact_sales_orders and fact_purchase_orders as well on a later step. These all were loaded back into MySQL.



CODE: 
data folder- json files extracted from MySQL
scripts folders- scripts used to create adventureworks in MySQL
ETL.ipynb- python pipeline notebook
README.md- documentation



DEPLOYMENT STRATEGY:
To deploy this project, I first ran my scripts found in the scripts folder in MySQL to setup the adventureworks schema+tables. Then I was able to export the json files for dim_customers, dim_employees, dim_products, dim_vendors, fact_sales_orders, and fact_purchases_orders which are found in my data folder. Then in my python notebook I connected to MySQL and mongoDB. I ran mongoDB locally on my computer using docker desktop. Once I was connected I was able to run my entire notebook smoothly.
