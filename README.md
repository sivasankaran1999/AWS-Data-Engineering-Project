# YouTube Data Engineering Project
Overview :

This project processes and analyzes raw YouTube video data to understand what makes a video trending. By analyzing the top trending videos, we aim to identify key factors, such as user interaction, views, shares, comments, and likes, which contribute to a video's popularity. Additionally, this analysis will help us build targeted advertising strategies around trending categories.

# Project Goals

The primary goal of this project is to analyze the factors that contribute to a YouTube video becoming trending and leverage this information for business insights, such as targeted advertising.

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
Today's dataset is the Top Trending Videos Dataset available on Kaggle. YouTube uses various factors, including user interaction, views, shares, comments, and likes, to determine which videos become trending. This dataset provides insights into what makes a video trend, allowing us to leverage this information for future use cases, such as building advertisements around popular video categories.

https://www.kaggle.com/datasets/datasnaek/youtube-new

Features of the Dataset
Video Details: Title, channel, publication time, tags, description, etc.
Engagement Metrics: Views, likes, dislikes, and comment counts.
Category Information: Region-specific category_id in JSON format.

# Architecture Diagram
![Architecture Diagram](./architecture.jpeg)

# Workflow Summary

Data Pipeline Overview
This project processes and analyzes raw YouTube video data, transforming it into a structured format for better insights. The pipeline uses a range of AWS services to ingest, clean, transform, and analyze the data, which is then visualized through interactive dashboards.

1. Data Ingestion and Storage : The raw data, including CSV and JSON files, is uploaded to Amazon S3 for centralized storage.
2. Data Cataloging : AWS Glue crawlers are used to scan and create metadata tables for the raw data, enabling easy access and management of the data in AWS.
3. Data Cleaning : AWS Lambda functions process the raw JSON data, extracting key information and reformatting it into the Parquet format, which is more optimized for querying and analysis. The cleaned data is stored separately in S3 for further processing.
4. Data Transformation : AWS Glue ETL is used to transform the CSV data into Parquet format, ensuring that the data is consistently structured and optimized for analytics.
5. Data Analysis : AWS Athena is used to run SQL queries on the cleaned and transformed data to perform comprehensive analysis. The data is joined and analyzed to uncover valuable insights.
6. Data Visualization : Amazon QuickSight is used to create interactive dashboards that visualize key metrics, trends, and insights from the YouTube video data.

# Future Enhancements
Automate end-to-end workflows using AWS Lambda triggers.
Incorporate additional datasets to expand insights.
Optimize data processing pipelines for real-time analytics.
