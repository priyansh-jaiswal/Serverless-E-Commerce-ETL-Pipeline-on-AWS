# Serverless E-Commerce ETL Pipeline on AWS

## Project Overview
An automated, serverless ETL pipeline that ingests raw 
e-commerce sales data, transforms it using PySpark, and 
serves business insights through SQL queries and a 
live dashboard.

## Architecture
CSV Upload → S3 (Raw) → Lambda → Glue (PySpark) 
→ S3 (Parquet) → Athena (SQL) → QuickSight (Dashboard)

## AWS Services Used
- Amazon S3       — Raw and processed data storage
- AWS Glue        — PySpark ETL transformation job
- AWS Lambda      — Event-driven pipeline trigger
- Amazon Athena   — Serverless SQL query engine
- Amazon QuickSight — Business intelligence dashboard
- AWS IAM         — Role-based access control

## What the Pipeline Does
1. Raw CSV sales data lands in S3 raw bucket
2. Lambda automatically detects the upload and triggers Glue
3. Glue PySpark job cleans, transforms and enriches the data
4. Processed data saved as Parquet partitioned by region/year
5. Athena queries the processed data using standard SQL
6. QuickSight dashboard shows revenue, trends and top products

## Key Transformations Applied
- Type casting for dates and numeric columns
- Null value removal and data validation
- Derived columns: days_to_ship, profit_margin,
  shipping_speed, order_size, is_profitable
- Partitioning by region and order year
- Separated cancelled orders into dedicated folder

## Dashboard Insights
- Total revenue by region (bar chart)
- Top products by revenue (horizontal bar)
- Orders by category (pie chart)
- Monthly revenue trend (line chart)

## Tech Stack
Python | PySpark | SQL | AWS S3 | AWS Glue | 
AWS Lambda | Amazon Athena | Amazon QuickSight | AWS IAM
