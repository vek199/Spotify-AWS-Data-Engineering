# 🎵 Spotify AWS Data Pipeline 🚀

## 📌 Overview
This project extracts, transforms, and loads (ETL) **Spotify streaming data** using AWS services.  
The goal is to **analyze user listening patterns** and generate insights using **AWS Glue, S3, Athena, and Quicksight**.

## 🏗️ Architecture
![AWS Architecture](screenshots/aws-architecture.png)
(Full AWS pipeline diagram)

1️⃣ **Spotify Data Extraction** → Extracts raw data from Spotify API  
2️⃣ **AWS Glue ETL** → Cleans and transforms the data  
3️⃣ **S3 Data Warehouse** → Stores processed data  
4️⃣ **AWS Glue Crawler** → Creates metadata tables  
5️⃣ **Athena Queries** → SQL-based analysis  
6️⃣ **Amazon Quicksight** → Data visualization  

## 📦 Tech Stack
- **AWS Services**: Glue, S3, Athena, Quicksight  
- **Programming**: Python, SQL  
- **Data Processing**: Pandas, PySpark  


1. IAM Roles and Policies

IAM Role

The IAM role configured in the pipeline has necessary permissions to access and interact with AWS services. The role is used by AWS Glue and other services that require permission to access S3 and perform ETL operations.

(Screenshot: screenshot/iam-role.png)

IAM User Policy

The IAM user policy defines the necessary permissions for a user to access and manage AWS services securely. It ensures appropriate access to S3, Glue, Athena, and QuickSight.

(Screenshot: screenshot/iam-user-policy.png)

2. S3 Bucket Structure

The S3 bucket is organized into multiple folders for structured data storage. It includes raw data, processed data, and output files used by Athena and QuickSight.

(Screenshot: screenshot/s3-bucket-folders.png)

3. AWS Glue Setup

AWS Glue is used for ETL (Extract, Transform, Load) processes. The Glue crawler scans the S3 bucket to create a metadata catalog that is later queried using AWS Athena.

AWS Glue Crawler

The Glue crawler automatically discovers datasets and updates the AWS Glue Data Catalog.

(Screenshot: screenshot/AWS-Glue-Crawler.png)

AWS Glue Jobs

AWS Glue jobs are used for data transformation and processing before making it available for querying.

(Screenshot: screenshot/AWS-Glue.png)

4. AWS Athena

AWS Athena is used to query the processed data stored in S3 using standard SQL syntax. The query results are stored in a designated S3 output folder.

(Screenshot: screenshot/AWS-Athena-Output.png)

5. AWS QuickSight

AWS QuickSight is used for data visualization and analytics. It connects to Athena and enables interactive dashboards for business insights.

(Screenshot: screenshot/AWS-Quicksight-Dashboard.png)

6. AWS Architecture

The overall AWS architecture integrates IAM, S3, Glue, Athena, and QuickSight into a seamless data pipeline. The architecture diagram illustrates the flow of data from ingestion to visualization.

(Screenshot: screenshot/aws-architecture.png)