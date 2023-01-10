# Amazon_Vine_Analysis

## Overview of Project

Since the work with Jennifer on the SellBy project was so successful, I’ve been tasked with another, larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, I’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. I’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, I’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in my dataset. Then, write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.

In this challenge, I am helping Jeremy and the data analytics team do the following:

- Deliverable 1: Perform ETL on Amazon Product Reviews.
- Deliverable 2: Determine Bias of Vine Reviews
- Deliverable 3: A Written Report on the Analysis (README.md)

# Resources
Data: challenge_schema.sql; Amazon_Reviews_ETL_Starter_code.ipynb converted to Amazon_Reviews_ETL.ipynb

Amazon Dataset: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Home_Improvement_v1_00.tsv.gz

Technologies: Google Colab;Pyspark; AWS RDS, PgAdmin4: Postgres SQL; VSCode;

# Deliverable 1:
## Perform ETL on Amazon Product Reviews 
Using your knowledge of the cloud ETL process, you’ll create an AWS RDS database with tables in pgAdmin, pick a dataset from the Amazon Review datasets Links to an external site., and extract the dataset into a DataFrame. You'll transform the DataFrame into four separate DataFrames that match the table schema in pgAdmin. Then, you'll upload the transformed data into the appropriate tables and run queries in pgAdmin to confirm that the data has been uploaded.

### Results

An Amazon Review dataset is extracted as a DataFrame (used the Home_Improvement dataset)
![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/reading%20files.jpg)

####The review_id_table DataFrame

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/review_id_df.jpg)


####The products_table DataFrame

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/products_df.jpg)


####The customers_table DataFrame

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/customers_df.jpg)

####The vine_table DataFrame

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/vine_df.jpg)

###Query to call each table:

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/Query%20to%20call%20each%20table.jpg)


# Deliverable 2:
## Determine Bias of Vine Reviews
### Overview
Using your knowledge of PySpark, Pandas, or SQL, you’ll determine if there is any bias towards reviews that were written as part of the Vine program. For this analysis, you'll determine if having a paid Vine review makes a difference in the percentage of 5-star reviews.


- Filter the data and create a new DataFrame or table to retrieve all the rows where the total_votes count is equal to or greater than 20 to pick reviews that are more likely to be helpful and to avoid having division by zero errors later on.

### Results

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/pgAdmin%20total_votes_20_df.jpg)

- Filter the new DataFrame or table created in Step 1 and create a new DataFrame or table to retrieve all the rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%.

### Results

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/helpful_votes_df.jpg)

- Filter the DataFrame or table created in Step 2, and create a new DataFrame or table that retrieves all the rows where a review was written as part of the Vine program (paid), vine == 'Y'.


### Results

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/paid_vine_reviews_df.jpg)

- Repeat Step 3, but this time retrieve all the rows where the review was not part of the Vine program (unpaid), vine == 'N'.

### Results

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/unpaid_vine_reviews_df.jpg)


- Determine the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the two types of review (paid vs unpaid).

### Results

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/reviews%20and%20pct%20of%20reviews.jpg)




# Deliverable 3:
##  A Written Report on the Analysis 
### Overview of Analysis 


### Results

![image](https://github.com/ras52017/Amazon_Vine_Analysis/blob/main/Images/reviews%20and%20pct%20of%20reviews.jpg)

![image](https://github.com/ras52017/MechaCar_Statistical_Analysis/blob/main/Images/PSI%20each%20indicdiual%20Lot.jpg)


