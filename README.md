# Big-Data-ETL
Repository of Jupyter notebooks utilized to perform ETL processes and create DataFrames of Amazon Reviews datasets that are then loaded into an RDS instance.

## Background
Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. They are quite large and can exceed the capacity of local machines. One dataset alone contains over 1.5 million rows; with over 40 datasets, data analysis can be very demanding on the average local computer. The first goal is to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal is to use PySpark or SQL to perform a statistical analysis of selected data.

- Extract two Amazon customer review datasets, transform each dataset into four DataFrames, and load the DataFrames into an RDS instance.

## Instructions
1. Upload the `part_one_starter_code.ipynb` into Google Colab and create a duplicate of this file.

2. Explore the [Amazon Reviews](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) datasets and pick two datasets to perform ETL.

3. Rename each `part_one_starter_code.ipynb` file according to the dataset you are using. For example, if you are going to use the Video Game reviews file, rename file to `part_one_video_games.ipynb`. Repeat the process for the duplicate file you created in Step 2.

### Extract the Data
1. Read in each dataset using the correct `header` and `sep` parameters.

2. Get the number of rows in the dataset.

### Transform the Data
For each dataset use the `schema.sql` file to create the four DataFrames as follows:

1. Create the "review_id_df" DataFrame with the appropriate columns and data types.

2. Create the "products_df" DataFrame that drops the duplicates in the "product_id" and "product_title columns.

3. Create the "customers_df" DataFrame that groups the data on the "customer_id" by the number of times a customer reviewed a product.

4. Create the "vine_df" DataFrame that has the "review_id", "star_rating", "helpful_votes", "total_votes", and "vine" columns.

### Load the Data into an RDS Instance

Export each DataFrame into the RDS instance to create four tables for each dataset.