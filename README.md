# Module 5 Challenge: athletic_sales_analysis

## Problem Statement
Analyze US sales of athletic wear by retailer, region, state, and city. After analyzing product units sold and total sales in general, focus on analyzing product sales of women's athletic footwear. At the end, determine the top 10 days and the top 10 weeks in which the most women's athletic footwear was sold.

## Solution
(I am very much following the prompts given in the initial Jupyter notebook.)  
The solution proceeds through the following steps:
1. Import the raw sales data for years 2020 and 2021 from two given CSV files into two dataframes.
2. Use the Pandas `concat` function to combine the data into one dataframe by appending the rows of the second dataframe to the rows of the first dataframe. Make sure that the rows of the combined dataframe is the sum of the rows of the separate dataframes and that the number of columns is the same in all three dataframes.  
   After combining the dataset, reset the index on the combined dataframe.  
   [!NOTE]  
   Before combining the dataframes make sure that the data has the same datatypes in corresponding columns and that it is organized using the same columns in both files.
3. Clean the combined dataframe if necessary by checking for `NULL` values. Comparing the number of rows for each column revealed that there were no `NULL` values.
4. Convert the data type of the `invoice_date` column to `datetime` for later analysis.
5. Using Pandas' `groupby` and `pivot_table` methods to aggregate over region, state, and city, then sorting by products sold, determine which regions sold the most products.  
    [!NOTE]  
    For the fun of it, here and throughout the rest of the solution, I implemented the solution using both `groupby` and `pivot_table`. In the real world, one would use one or the other method.
6. Apply the same procedure as described in step 5 above to determine the regions that had the largest total sales.
7. Add the `retailer` to the aggregation and use the same method as descibed above to determine which retailer had the most total sales in which regions.
8. Filtering the original combined dataframe by women's athletic footwear and using the same method described above determine which retailer sold the most units in which region.
9. Using the Pandas `resample` function determine the top ten days on which total sales of women's athletic footwear was largest.
10. Using the Pandas `resample` function again determine the top ten weeks in which total sales of women's athletic footwear was largest.
