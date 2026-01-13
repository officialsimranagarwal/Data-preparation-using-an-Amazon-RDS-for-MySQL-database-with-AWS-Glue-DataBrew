# Data Preparation with AWS Glue DataBrew & RDS 🧹

![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![ETL](https://img.shields.io/badge/ETL-Glue_DataBrew-success?style=for-the-badge)

## 📖 Overview

This repository documents the integration of **Amazon RDS for MySQL** with **AWS Glue DataBrew** to build a codeless ETL (Extract, Transform, Load) pipeline. It details the architectural setup required to clean and normalize raw database data using cloud-native managed services.

## 🏗️ Technical Architecture

### 1. Data Source (Amazon RDS)
-   **Engine**: MySQL.
-   **Network**: Hosted in a Private Subnet for security.
-   **Security**: Secured via Security Groups allowing inbound traffic specifically from the Glue DataBrew ENI (Elastic Network Interface).

### 2. Connection Layer (AWS Glue)
-   **DBC (Jdbc Connection)**: Uses JDBC strings to establish connectivity.
-   **Crawler**: (Optional) Used to catalog the schema of the RDS tables into the AWS Glue Data Catalog.

### 3. Transformation Layer (AWS Glue DataBrew)
-   **Project Setup**: Binds the dataset to a "Recipe".
-   **Recipe Steps**: A sequence of transformations applied to the data:
    -   **Cleaning**: Handling null values (fill/drop).
    -   **Normalization**: Standardizing string formats (e.g., casing, trimming).
    -   **Encoding**: Converting categorical features (e.g., One-Hot Encoding) for downstream ML / Analytics usage.

### 4. Output
-   **S3 Destination**: Transformed data is written to an Amazon S3 bucket in optimized formats (Parquet/CSV) for further analysis in Athena or Redshift.

## 🛠️ Configuration Details

-   **IAM Roles**: Requires `AWSGlueServiceRole` and `AWSDataBrewServiceRole` policies to allow the service to access RDS and write to S3.
-   **VPC Endpoints**: Configured to ensure traffic between Glue and S3 remains within the AWS network.

## 📂 Contents

-   **`Data preparation using an Amazon RDS for MySQL database with AWS Glue DataBrew.pdf`**: The master configuration guide.

## 🚀 Getting Started

1.  Clone this repository:
    ```bash
    git clone https://github.com/officialsimranagarwal/Data-preparation-using-an-Amazon-RDS-for-MySQL-database-with-AWS-Glue-DataBrew.git
    ```
2.  Follow the PDF guide to replicate the infrastructure.

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## 👤 Author

**Simran Agarwal**
-   [Profile](https://github.com/officialsimranagarwal)
-   [LinkedIn](https://linkedin.com/in/simran-agarwal-54751b191)

---
*Generated with ❤️ by Simran Agarwal*
