# AWS ETE Data Engineering Pipeline

## Introduction

This project serves as a concise and practical guide to building an end-to-end data lake and data warehouse solution on AWS. It walks through every critical step in a data engineering workflow—starting from data ingestion and transformation to analytical querying and orchestration. The pipeline uses a medallion architecture-inspired approach (bronze → silver → gold layers) and showcases the integration of popular AWS services such as Amazon Redshift, AWS Glue, Apache Hudi, Amazon EMR, and Managed Workflows for Apache Airflow (MWAA).

## System Architecture

The project is designed with the following components and flow:

1. **AWS Glue Crawler**  
   Parses raw CSV input files from S3 and creates metadata tables in the AWS Glue Data Catalog.

2. **AWS Glue PySpark Job**  
   Loads and transforms raw CSV data into Hudi-format tables stored in S3 (data lake) using PySpark.

3. **Amazon EMR (Apache Hudi)**  
   Reads Hudi tables (silver layer) and transforms them into analytics-ready Hudi tables (gold layer).

4. **Amazon Redshift Spectrum**  
   Reads Hudi tables directly from the S3 data lake and creates snapshot tables for analytical queries.

5. **Managed Workflows for Apache Airflow (MWAA)**  
   Orchestrates the entire ETL pipeline by automating and sequencing the above steps.

## Technologies Used

- AWS Glue (Crawler, ETL Jobs with PySpark)
- Apache Hudi
- Amazon EMR (with Spark)
- Amazon Redshift
- Managed Workflows for Apache Airflow (MWAA)
- Amazon S3
- AWS IAM (Role-based access control)

## Goals

The main goals of this project are to explore AWS data engineering services and learn how to build scalable, production-ready data pipelines in the cloud. Specific objectives include:

- Understanding how to set up and integrate key AWS data services such as Glue, EMR, and Redshift.
- Implementing a medallion architecture pattern using Hudi for lakehouse-style storage.
- Gaining hands-on experience with orchestration using MWAA (Apache Airflow on AWS).
- Learning how to build and manage a data lake and data warehouse on AWS with cost-effective and modular design.


