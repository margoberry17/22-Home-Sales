# 22-Home-Sales

I used my knowledge of SparkSQL to determine key metrics about home sales data. I used Spark to create temporary views, partitioned the data, cached and uncached a temporary table, and verified that the table had been uncached.


## Process

1. Imported the necessary PySpark SQL functions for this assignment.

2. Read the home_sales_revised.csv data into a Spark DataFrame.

![01 Home Sales Table](https://github.com/margoberry17/22-Home-Sales/assets/136475202/4f487b45-b5bd-42fe-b453-4d4e7a7879ce)

3. Created a temporary table called homeSales.

4. Using SparkSQL, I answered the following questions:

What is the average price for a four-bedroom house sold for each year?

![03 Avg Price Four Beds](https://github.com/margoberry17/22-Home-Sales/assets/136475202/7c27f932-9e77-4a1f-895a-6d19111a17ad)

What is the average price of a home for each year it was built that has three bedrooms and three bathrooms?

![04 Avg Price Three Bed Three Bath](https://github.com/margoberry17/22-Home-Sales/assets/136475202/73f55a5b-cdae-42d5-957e-cfc1784bc3e8)

What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet?

![05 Avg Price Three Bed Three Bath Plus](https://github.com/margoberry17/22-Home-Sales/assets/136475202/03530856-7dc1-4d6a-8bed-d4d86b60c89d)

What is the "view" rating for homes costing more than or equal to $350,000? I determined the run time for this query.

![06 Avg Price Per View Rating](https://github.com/margoberry17/22-Home-Sales/assets/136475202/6a96f5dd-1e0f-4dc5-acbe-93ed7320d2a0)

5. Cached my temporary table homeSales and checked if my temporary table was cached.

6. Using the cached data, I ran the query that filtered out the view ratings with an average price of greater than or equal to $350,000. I determined the runtime and compared it to the uncached runtime.

![09 Cached Avg Price Per View Rating](https://github.com/margoberry17/22-Home-Sales/assets/136475202/a968a32e-6b8d-401e-b6da-98a2e9f3c352)

The cached run time of .98 seconds is shorter than the original run time of 1.12 seconds


7. I partitioned the "date_built" field on the formatted parquet home sales data.

8. I created a temporary table for the parquet data.

9. I ran the query that filtered out the view ratings with an average price of greater than or equal to $350,000. I determined the runtime and compared it to the uncached runtime.

![13 Parquet Avg Price Per View Rating](https://github.com/margoberry17/22-Home-Sales/assets/136475202/264d3586-8943-4c56-8a97-63ab3a67d772)

The cached run time of .98 seconds is shorter than the parquet run time of 1.08 seconds


10. I uncached the homeSales temporary table and verified that the homeSales temporary table was uncached using PySpark.
