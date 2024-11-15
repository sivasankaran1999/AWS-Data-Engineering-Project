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

# Workflow Summary
Data Storage:
Upload raw data (CSV and JSON) to S3 in separate folders.
Data Cataloging:
Use AWS Glue crawlers to create data catalogs for the raw data.
Data Cleaning:
Process JSON data using AWS Lambda to extract and reformat it into Parquet files.
Store cleaned data in a separate S3 bucket.
Data Transformation:
Convert CSV files to Parquet using AWS Glue ETL.
Ensure data consistency by updating schemas and handling regional variations.
Data Analysis:
Query data using AWS Athena.
Combine datasets (e.g., cleaned JSON with CSV) for analysis.
Visualization:
Create interactive dashboards in Amazon QuickSight to analyze and interpret results.
Future Enhancements
Automate end-to-end workflows using AWS Lambda triggers.
Incorporate additional datasets to expand insights.
Optimize data processing pipelines for real-time analytics.
