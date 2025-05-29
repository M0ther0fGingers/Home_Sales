# Home_Sales
Module 22 Challenge

## File Structure
 - Home_Sales_colab.ipynb contains the code for this challenge. It was completed using Google Colab. 
 - There is no Resources folder for this challenge. The data is stored in an AWS S3 bucket as a .csv file and accessed in the code. 

## Code Method
 - Import google colab dependencies, make sure to change the spark-version to 'spark-3.5.5'
 - Import packages pyspark and time and create a SparkSession. 
 - Read in the .csv and create a dataframe. 
 - Use the .createOrReplaceTempView function to create a temporary view. 
 - Complete the questions using SQL to query the data. Each question builds on the next, finally resulting in a a table that shows:
   - The average price of a home per "view" rating, rounded to two decimal places
   - Filtered to homes priced greater than or equal to $350,000
   - Ordered by descending view rating
   - Check the time in seconds needed to create the final table. 
 - Cache the data and run the same final SQL query again, checking the time in seconds needed to create the table. 
 - Create a partition by the 'date-built' field using partionBy function and read in the parquet formatted data.
 - Create a new temporary view with the partitioned data. 
 - Check the time in seconds needed to create the table with partiioned data. 

## Results
 - Using the dataframe with a temporary view, it took 1.31 seconds to create the final table. 
 - Using the cached data, it took .62 seconds to create the same table. 
 - Using the parquet partioned data, it took 1.78 seconds to create the same table. 
 - The cached data was by far the most effecient. It ran 1.16 seconds faster than the partitioned data. If this were a very large data set, that 1.16 seconds would be proportionally larger. 

## Code Development source
 - This code was developed using Bootcamp lessons and classroom demonstration videos. 
 - Some additional help was found using Copilot. 