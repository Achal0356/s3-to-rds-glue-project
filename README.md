# 🚀 Data Ingestion from S3 to RDS with Fallback to AWS Glue using Dockerized Python Application

## 📌 Project Overview

This project demonstrates how to build a **Dockerized Python application** that:

- 📥 Reads a CSV file from an Amazon **S3** bucket  
- 🗃️ Inserts the data into an **RDS MySQL** database  
- 🛡️ Automatically falls back to **AWS Glue Data Catalog** if the RDS is unavailable or the write operation fails  

> The goal is to create a resilient and containerized data pipeline using key AWS services.

---

## 🎯 Objective

- Automate ingestion of structured data (CSV) from Amazon S3  
- Push data to an RDS MySQL-compatible database  
- If RDS push fails, fallback to AWS Glue by:
  - Creating a Glue database & table
  - Registering the S3 data location as a schema-aware catalog table

---

## 🛠️ Technologies Used

- **Python 3.9+**  
- **Docker**  
- **AWS Boto3 SDK**  
- **Pandas**  
- **SQLAlchemy + PyMySQL**  
- **AWS Services**: S3, RDS, Glue

---

## 📂 Project Structure
s3-project/
├── ingest.py # Main Python script
├── Dockerfile # Docker container definition
├── requirements.txt # Python dependencies
└── README.md # This documentation


---

## ⚙️ Environment Variables

Set these environment variables when running the Docker container:

| Variable | Description |
|----------|-------------|
| `AWS_ACCESS_KEY_ID` | Your AWS access key |
| `AWS_SECRET_ACCESS_KEY` | Your AWS secret key |
| `AWS_DEFAULT_REGION` | AWS region (e.g., `us-east-1`) |
| `S3_BUCKET` | Name of the S3 bucket containing the CSV file |
| `CSV_KEY` | Path to the CSV file within the bucket (e.g., `data/student_data.csv`) |
| `RDS_HOST` | Endpoint of the RDS MySQL database |
| `RDS_USER` | RDS database username |
| `RDS_PASS` | RDS database password |
| `RDS_DB` | RDS database name |
| `RDS_TABLE` | RDS table name |
| `GLUE_DB` | Glue database name for fallback |
| `GLUE_TABLE` | Glue table name for fallback |
| `S3_LOCATION` | S3 location for Glue table fallback (e.g., `s3://your-bucket/data/`) |

---

## 🐳 How to Build & Run the Docker Container

### 🔧 Build the Docker Image

```bash
docker build -t s3-to-rds-glue .



