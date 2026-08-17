# NYC Taxi — Azure Data Engineering Project

## 📌 Project Overview

This project implements an end-to-end data engineering pipeline for NYC Taxi data using Microsoft Azure services.

The project demonstrates how raw taxi data can be ingested, stored, transformed, and prepared for analytics using a modern Azure data engineering architecture.

### Azure Services Used

* **Azure Data Factory (ADF)** — Data ingestion and pipeline orchestration
* **Azure Data Lake Storage Gen2 (ADLS Gen2)** — Scalable cloud data storage
* **Azure Databricks** — Data processing and transformation using Apache Spark

---

## 🏗️ Architecture

![NYC Taxi Azure Data Engineering Architecture](./architecture/architecture.png)

```text
                    NYC Taxi Data
                         │
                         ▼
                Azure Data Factory
                 (Ingestion / ETL)
                         │
                         ▼
              Azure Data Lake Storage
                    Gen2 (ADLS)
                         │
              ┌──────────┴──────────┐
              ▼                     ▼
          Bronze Layer          Raw Data
              │
              ▼
        Azure Databricks
              │
              ▼
          Silver Layer
       (Cleaned / Transformed)
              │
              ▼
          Gold Layer
       (Business-Ready Data)
              │
              ▼
          Analytics / BI
```

---

## 🔄 Data Engineering Workflow

### 1. Data Ingestion

Azure Data Factory is used to orchestrate the movement of NYC Taxi data into Azure Data Lake Storage Gen2.

ADF manages:

* Data pipelines
* Datasets
* Linked services
* Data movement
* Pipeline execution

### 2. Bronze Layer

The Bronze layer contains the raw or minimally processed taxi data.

The purpose of this layer is to preserve the original data while making it available for downstream processing.

### 3. Silver Layer

Azure Databricks processes the Bronze data and creates the Silver layer.

Typical transformations include:

* Data cleaning
* Handling missing values
* Data type conversions
* Removing invalid records
* Standardizing columns
* Data quality transformations

### 4. Gold Layer

The Gold layer contains refined, business-ready data.

This layer is designed to support analytics and reporting by providing structured and meaningful datasets.

---

## 🛠️ Technologies

| Technology                   | Purpose                                  |
| ---------------------------- | ---------------------------------------- |
| Azure Data Factory           | Data ingestion and orchestration         |
| Azure Data Lake Storage Gen2 | Cloud data storage                       |
| Azure Databricks             | Data transformation and Spark processing |
| Apache Spark                 | Distributed data processing              |
| GitHub                       | Source control and project versioning    |
| Python / PySpark             | Data transformation                      |

---

## 📂 Repository Structure

```text
NYC-Taxi/
│
├── dataset/
│   └── ADF datasets
│
├── linkedService/
│   └── ADF linked services
│
├── pipeline/
│   └── ADF pipelines
│
├── Databricks/
│   ├── Silver/
│   │   └── Silver_notebook
│   │
│   └── Gold/
│       └── Gold_notebook
│
└── README.md
```

---

## 🔐 Security

Credentials and secrets should **never be stored directly in GitHub**.

The Databricks notebooks use placeholders/secure credential references instead of exposing Azure client secrets.

For production environments, credentials should be managed using secure services such as:

* Azure Key Vault
* Databricks Secrets
* Managed Identity
* Service Principal authentication

> **Important:** Never commit passwords, client secrets, access keys, SAS tokens, or other sensitive credentials to source control.

---

## 🔀 Git & Version Control

This project uses GitHub for source control.

### Azure Data Factory

ADF resources are connected to the GitHub repository, allowing pipelines, datasets, and linked services to be version controlled.

### Azure Databricks

Databricks Git folders are used to synchronize the Silver and Gold notebooks with the GitHub repository.

---

## 🚀 Project Flow

```text
1. NYC Taxi Data
       ↓
2. Azure Data Factory
       ↓
3. Azure Data Lake Storage Gen2
       ↓
4. Bronze Layer
       ↓
5. Azure Databricks
       ↓
6. Silver Layer
       ↓
7. Gold Layer
       ↓
8. Analytics / Reporting
```

---

## 🎯 Project Objectives

The main objectives of this project are to demonstrate:

* End-to-end Azure data engineering
* Cloud data ingestion
* Data lake architecture
* ETL/ELT pipeline development
* Apache Spark processing
* PySpark transformations
* Bronze/Silver/Gold data architecture
* Azure Data Factory orchestration
* Databricks data transformation
* Git and GitHub version control
* Secure credential management

---

## 📈 Future Improvements

Possible future enhancements include:

* Add Azure Key Vault integration
* Add automated data quality checks
* Add incremental data processing
* Add monitoring and alerting
* Add CI/CD deployment
* Add Power BI reporting
* Add automated testing
* Add pipeline parameterization

---

## 👨‍💻 Author

**Vikesh**

This project was created as an end-to-end Azure Data Engineering portfolio project using Azure Data Factory, Azure Databricks, and Azure Data Lake Storage Gen2.
