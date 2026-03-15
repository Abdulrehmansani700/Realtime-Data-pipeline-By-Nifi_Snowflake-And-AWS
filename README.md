# 🚀 Real-Time Data Pipeline with AWS, NiFi, and Snowflake (SCD Implementation)
This project demonstrates a robust, enterprise-level real-time data orchestration pipeline. It automates the flow of data from a source (Jupyter/EC2) to a cloud data warehouse (Snowflake) while maintaining historical data using Slowly Changing Dimensions (SCD).

# 🏗️ Architecture Overview
The pipeline follows a seamless path from raw data generation to structured analytics:

* Source: Data is managed via Jupyter Notebooks running inside Docker containers on an AWS EC2 Instance.
* Orchestration: Apache NiFi ingests and routes the data in real-time.
* Storage: Raw files are landed in Amazon S3.
* Auto-Loading: Snowpipe triggers automatically on new S3 arrivals to load data into Snowflake's Stage Table.
* Transformation: Snowflake Streams track changes (CDC), and Snowflake Tasks execute the final logic to update target tables (SCD Implementation).

# 🛠️ Tech Stack
* Cloud: AWS (EC2, S3)
* Containerization: Docker
* Data Ingestion: Apache NiFi
* Data Warehouse: Snowflake
* Features: Snowpipe, Streams, Tasks, SCD (Type 1/2)
* Processing: Python (Jupyter)

# ⚡ Key Features
* ✅ Real-Time Processing: Zero manual intervention from ingestion to loading.
* ✅ SCD Implementation: Keeps track of historical changes in data.
* ✅ Scalable Infrastructure: Hosted on AWS using Dockerized environments.
* ✅ Automated Triggering: Snowpipe and Tasks ensure the pipeline stays "Always-On".

#🚀 How to Set Up
* AWS EC2: Launch an instance and install Docker/Docker-Compose.
* NiFi: Set up a GetFile/PutS3 processor flow.
* Snowflake: - Create an external stage for S3.
* Configure a Pipe with AUTO_INGEST = TRUE.
* Create Streams on the stage table and Tasks for merging data into final tables.

# 📊 Pipeline Flow Diagram
`EC2 >> Docker >> Jupyter >> NiFi >> S3 >> Snowpipe >> Stage Table >> Stream >> Task >> Final Tables`
