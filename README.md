# financial-datawarehouse-aws
AWS-powered pipeline loads stock data (AAPL, AMZN, BRKA, FB, GOOG, JNJ, MA, MSFT, V, WMT) to S3, Glue for crawling, Athena for querying. Python scripts handle ETL, storing cleaned data in S3. Glue ETL job transfers to Redshift for advanced analytics, ensuring seamless storage, processing, and visualization.

# Financial Stock Data Pipeline Project

## Problem Statement:

The financial stock data for top companies (AAPL, AMZN, BRKA, FB, GOOG, JNJ, MA, MSFT, V, WMT) needs a streamlined data engineering solution. The goal is to create an end-to-end data pipeline for ingesting, transforming, and visualizing this data efficiently.


## Dataset Overview:

This dataset contains 20 years of end-of-day stock data for the top 10 US companies by market capitalization. The companies included are AAPL, AMZN, BRKA, FB, GOOG, JNJ, MA, MSFT, V, and WMT.

## File Structure:

Each company's data is stored in a separate CSV file.
File names follow the convention: <Company Symbol>_stock_data.csv.

## Overview:

This Data Engineer project focuses on financial stock data for top companies (AAPL, AMZN, BRKA, FB, GOOG, JNJ, MA, MSFT, V, WMT). The pipeline involves loading CSV data into S3, using AWS Glue for crawling and Athena for querying. Python scripts perform ETL transformations, and Glue ETL jobs move data from S3 to Redshift for visualization.

### Project Structure:

#### AWS Services: 
Utilize S3 for storage, Glue for crawling and ETL, Athena for querying, and Redshift for data warehousing.

#### ETL Process: 
Python scripts (etl_script.py) connect to S3 and Glue, transforming data appropriately.
Transformed data loaded back into S3.

#### Redshift Integration: 
Glue ETL job (redshift_load_job) transfers transformed data from S3 to Redshift.

### Setup Instructions:
S3 Bucket: Create an S3 bucket to store raw and transformed data.
AWS Glue: Set up Glue for crawling and ETL jobs.
Athena: Configure Athena for querying data stored in S3.
Redshift: Provision a Redshift serverless namespace and workgroup for data warehousing.
Python Environment: Install necessary Python libraries specified in requirements.txt.

![Data Pipeline Architecture](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/58fee084-e6ba-4092-88ad-65818e6cd393)

## Redshift Serverless:

This project uses Redshift's serverless for data warehousing. Amazon Redshift automatically provisions and scales data warehouse capacity to deliver fast performance for demanding and unpredictable workloads. With Amazon Redshift Serverless, you use a console interface to reach a serverless data warehouse or APIs to build applications. Through the data warehouse, you can access your Amazon Redshift managed storage and your Amazon S3 data lake.


## Process

1. Downloading the dataset on to the S3 bucket. If the dataset is already on the S3 bucket, then port it over to your bucket.

   ![image](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/42ecad15-b12e-4bfc-94a8-adac8e9e4bef)

2. Crawl over the file using AWS Glue. The idea is to partition the data table in the best possible way and the tables will be populated in the AWS Data Catalog.

   ![image](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/efc579ee-5a45-47ad-a0f3-5793aaa76b09)4

3. The crawled data can be queried using Athena and for further extraction. We wont be doing the extraction over here though..

4. Connect Python with S3, Athena and Glue to get access to the data.
5. Upon connecting, perform the ETL steps by transforming the data into Data Warehouse model -- Dim and Fact tables. The model for my project is as below:

   ![image](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/2a9bc6e6-8518-4f2f-a7d8-726a729d2f41)

6. The created model are loaded on to the S3 bucket. 

7. The transformed model is then uploaded into S3 bucket through Glue where an ETL job is created to run a Python script to create the tables in Redshift.

8. After successful completion of the script, the tables are loaded onto the Datawarehouse for further analysis (Visualization tools - Tableau, PowerBI, Data Studio, etc)

   ![image](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/fb3fa875-fe30-4bac-b10c-132726490a3a)

   ![image](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/ed2e56f9-5551-496d-aad9-d02237ded7a5)

   ![image](https://github.com/Arvind1997/financial-datawarehouse-aws/assets/13155343/601421f0-2ff6-4909-a822-2f07aa989f71)


## Outputs:

#### Transformed Data in S3: Cleaned and processed data stored back in S3 for accessibility.
#### Redshift Data Warehouse: Transferred data stored in Redshift for advanced analytics and visualization.


## Impact:

#### Efficient Data Handling: Streamlined data processing ensures efficient handling of financial stock data.
#### Scalability: Utilization of AWS services allows for scalability with increasing data volumes.
#### Advanced Analytics: The data warehouse in Redshift enables complex analytics and visualization.
#### Data Insights: Querying capabilities in Athena facilitate exploration and extraction of valuable insights.




   

