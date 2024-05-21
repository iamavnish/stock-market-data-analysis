# Real-Time Analytics on AWS

## Overview 

This is Proof of Concept for real-time or streaming anaytics on AWS. 

## Architecture

![Architecture](https://github.com/iamavnish/stock-market-data-analysis/assets/13760927/5ba38201-3c3e-4fbd-8ff1-c5f9da943146)

## Tech Stack

- AWS
  - EC2
  - S3
  - Glue Crawler
  - Glue Catalog
  - Athena
  - IAM
- Apache Kafka (hosted on EC2)
- Python3

## Dataset

CSV file containing stock market data -
https://github.com/iamavnish/stock-market-data-analysis/blob/main/indexProcessed.csv

## Solution

Stock market events are being sent to Kafka Producer application which in turn writes them to Kafka topic. Kafka Consumer application reads those events from Kafka topic which are further written to files in S3 bucket. Glue Crawler determines the schema of data stored in S3 bucket and creates metadata in Glue Catalog. Then data from files stored in S3 bucket is being queried for insights through Athena.
