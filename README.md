# YouTube Data Engineering Project
Overview :

This project processes and analyzes raw YouTube video data to understand what makes a video trending. By analyzing the top trending videos, we aim to identify key factors, such as user interaction, views, shares, comments, and likes, which contribute to a video's popularity. Additionally, this analysis will help us build targeted advertising strategies around trending categories.

# Project Goals

The primary goal of this project is to analyze the factors that contribute to a YouTube video becoming trending and leverage this information for business insights, such as targeted advertising.

Data Ingestion: Build a mechanism to ingest data from multiple sources.

ETL System: Transform raw data into a structured format suitable for analysis.

Data Lake: Centralize data storage from various sources in a single repository.

Scalability: Ensure the system is scalable to handle increasing data volumes.

Cloud Integration: Leverage AWS services to process and manage large-scale data efficiently.

Reporting: Create interactive dashboards to extract actionable insights from the data.


# Services Used

Amazon S3: Scalable object storage service for data availability and high performance.

AWS IAM: Identity and access management to securely control access to AWS resources.

AWS Glue: Serverless data integration service that helps discover, prepare, and combine data for analytics.

AWS Lambda: Compute service that runs code in response to events without managing servers, used here for data preprocessing.

AWS Athena: Interactive query service for analyzing data directly from S3 using SQL.

Amazon QuickSight: Business intelligence service to visualize and analyze data for decision-making.

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

Data Ingestion and Storage :

The raw data, including CSV and JSON files, is uploaded to Amazon S3 for centralized storage.

Data Cataloging : 

AWS Glue crawlers are used to scan and create metadata tables for the raw data, enabling easy access and management of the data in AWS.

Data Cleaning :

AWS Lambda functions process the raw JSON data, extracting key information and reformatting it into the Parquet format, which is more optimized for querying and analysis. The cleaned data is stored separately in S3 for further processing.

Data Transformation :

AWS Glue ETL is used to transform the CSV data into Parquet format, ensuring that the data is consistently structured and optimized for analytics.

Data Analysis : 

AWS Athena is used to run SQL queries on the cleaned and transformed data to perform comprehensive analysis. The data is joined and analyzed to uncover valuable insights.

Automation with Lambda: 

Triggers in AWS Lambda are set up to automatically process new data as it arrives in the raw data S3 bucket. Once the data is processed, it is automatically moved to the cleaned data S3 bucket, ensuring that the cleaning and transformation workflows run seamlessly without manual intervention.

Data Visualization :

Amazon QuickSight is used to create interactive dashboards that visualize key metrics, trends, and insights from the YouTube video data.

You can view the data visualization created in Amazon QuickSight here:

[ View YouTube Analytics Visualization PDF](Youtube_Analytics_Viz.pdf)

![YouTube Analytics Visualization](Youtube_Analytics_Viz.png)

# Future Enhancements
Automate end-to-end workflows using AWS Lambda triggers.

Incorporate additional datasets to expand insights.

Optimize data processing pipelines for real-time analytics.


# Conclusion

In this project, we successfully built a robust data pipeline using AWS services to analyze YouTube trending videos. By leveraging AWS S3 for data storage, AWS Glue for data cataloging and transformation, and AWS Lambda for automated data cleaning, we were able to process and prepare large datasets efficiently. The use of AWS Athena allowed for querying the cleaned and transformed data, and the insights gained were visualized through interactive dashboards in Amazon QuickSight.

This system is scalable and can be easily extended to accommodate new data sources and more complex analyses. By automating the data processing workflow with Lambda triggers, the entire process is streamlined, ensuring that as new data arrives, it is cleaned, transformed, and stored without manual intervention. The project provides a clear pathway for using cloud-based tools to gain valuable insights from large datasets, such as understanding what factors contribute to a YouTube video becoming trending, which can be used for targeted advertising and business decisions.

The integration of AWS services not only simplifies the handling of large data but also creates a scalable, automated solution suitable for continuous, real-time data processing. This project demonstrates the power of cloud computing and serverless architectures in modern data analytics.
