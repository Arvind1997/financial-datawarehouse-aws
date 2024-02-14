# financial-datawarehouse-aws
AWS-powered pipeline loads stock data (AAPL, AMZN, BRKA, FB, GOOG, JNJ, MA, MSFT, V, WMT) to S3, Glue for crawling, Athena for querying. Python scripts handle ETL, storing cleaned data in S3. Glue ETL job transfers to Redshift for advanced analytics, ensuring seamless storage, processing, and visualization.

# Financial Stock Data Pipeline Project

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
Redshift: Provision a Redshift cluster for data warehousing.
Python Environment: Install necessary Python libraries specified in requirements.txt.




