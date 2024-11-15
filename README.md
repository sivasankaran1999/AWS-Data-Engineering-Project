# YouTube Data Engineering Project
Overview
This project aims to securely manage, streamline, and perform analysis on structured and semi-structured YouTube videos data based on video categories and trending metrics.

# Project Goals
Data Ingestion: Build a mechanism to ingest data from different sources.
ETL System: Transform raw data into a proper format for analysis.
Data Lake: Centralize data storage from multiple sources.
Scalability: Ensure the system scales as data volume increases.
Cloud Integration: Use AWS to process large-scale data efficiently.
Reporting: Create dashboards to gain insights from the data.

# Services Used
Amazon S3: Scalable object storage for data availability and performance.
AWS IAM: Identity and access management to securely control access to AWS services.
AWS Glue: Serverless data integration for discovering, preparing, and combining data.
AWS Lambda: Compute service to preprocess and clean data without managing servers.
AWS Athena: Interactive query service to analyze data directly from S3.
Amazon QuickSight: Business intelligence service for visualizing and analyzing data.

# Dataset Used
This dataset, sourced from Kaggle, contains statistics on daily trending YouTube videos for multiple regions.

https://www.kaggle.com/datasets/datasnaek/youtube-new

Features of the Dataset
Video Details: Title, channel, publication time, tags, description, etc.
Engagement Metrics: Views, likes, dislikes, and comment counts.
Category Information: Region-specific category_id in JSON format.

# Architecture Diagram
![Architecture Diagram](./architecture.jpeg)

# Workflow Summary
Data Pipeline Overview
This project involves processing, transforming, and analyzing data from raw CSV and JSON formats using AWS services. The pipeline is designed to ingest, clean, transform, and analyze YouTube video data, ultimately visualizing it through interactive dashboards.

1. Data Storage
Upload Raw Data: Store raw data files (CSV and JSON) in separate folders within an Amazon S3 bucket.
Folder Structure:
/raw_data/csv/
/raw_data/json/
2. Data Cataloging
AWS Glue Crawlers: Use AWS Glue to create data catalogs for the raw CSV and JSON data.
Crawling Process: AWS Glue will automatically scan the data files in the S3 buckets to infer the schema and create metadata tables.
Output: These tables can be accessed by services like Athena for querying.
3. Data Cleaning
AWS Lambda for JSON Data Processing:

Process the raw JSON data in AWS Lambda functions to extract relevant data and reformat it into a more structured format (Parquet).
Output: Store the cleaned JSON data as Parquet files in a separate S3 bucket for efficient querying.
Lambda Role: Ensure proper IAM roles and permissions are set up to allow AWS Lambda to access the data in the S3 bucket.
Data Storage:

Cleaned data is stored in the /cleaned_data/json/ folder in S3.
4. Data Transformation
AWS Glue ETL for CSV Data:

Use AWS Glue to extract, transform, and load (ETL) the raw CSV files from S3 into Parquet format for better performance and storage optimization.
Schema Management: Update the schema of the CSV files during the transformation process to ensure consistency across the data.
Handle Regional Variations: Address any regional variations in the data (e.g., language or regional identifiers) during the ETL process.
Output: Store the transformed Parquet files in a dedicated S3 bucket (e.g., /transformed_data/csv/).

5. Data Analysis
Query Data with AWS Athena:
Use AWS Athena to run SQL queries on the cleaned and transformed Parquet data stored in S3.
Combine datasets, such as the cleaned JSON data with the CSV data, for comprehensive analysis.
6. Data Visualization
Amazon QuickSight:
Create interactive dashboards to analyze the data and generate insights.
Visualizations will help answer key business questions related to video trends, engagement metrics, and performance across regions.

# Future Enhancements
Automate end-to-end workflows using AWS Lambda triggers.
Incorporate additional datasets to expand insights.
Optimize data processing pipelines for real-time analytics.
