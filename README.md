# aditya-l1-isro
# Aditya-L1 CME Data Pipeline (SWIS-ASPEX)

This repository provides a real-time data pipeline for processing CME (Coronal Mass Ejection) data from the SWIS-ASPEX instrument on ISRO's Aditya-L1 satellite.

## Objective

- Collect raw CME proton and solar wind data from Aditya-L1 SWIS-ASPEX instrument
- Stream the data via Kafka for real-time processing
- Transform and store structured data in a Delta Lake table
- Enable querying via Presto/Trino for analysis and visualization

## Architecture Overview

1. **Data Ingestion**: Download or receive raw telemetry from the ASPEX source (CDF/TXT/JSON)
2. **Kafka Producer**: Push real-time formatted events into Kafka topics
3. **Stream Processing**: Use Spark Structured Streaming or Flink to clean and enrich data
4. **Lakehouse Storage**: Store results in Delta format on S3/HDFS
5. **Query Layer**: Use Presto or Trino to run analytical SQL queries

## Directory Structure

- `data_ingestion/`: Scripts to fetch raw ASPEX data
- `kafka/`: Kafka producer for streaming telemetry
- `spark_streaming/`: Spark jobs for processing the Kafka stream
- `lakehouse/`: Code to build and manage Delta tables
- `presto_queries/`: Sample SQL queries for exploration
- `utils/`: Configuration and helper functions

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/aditya-l1-cme-pipeline.git
   cd aditya-l1-cme-pipeline
