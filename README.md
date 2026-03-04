# Healthcare Data Warehouse & Analytics Project

## Overview

This project demonstrates the design and implementation of a healthcare analytics data warehouse using dimensional modeling principles. The goal is to transform raw healthcare operational data into a structured data warehouse that enables efficient reporting and analytical insights.

The system processes hospital admission and insurance claim data through an ETL pipeline, cleans and transforms the datasets using Python, and loads the processed data into a Snowflake data warehouse designed with a star schema.

This project simulates a real-world healthcare analytics environment where hospitals and insurance teams can monitor operational performance, financial metrics, and claim outcomes.

---

## Project Objectives

* Build a dimensional **healthcare data warehouse**
* Implement **ETL pipelines using Python and Pandas**
* Design a **Star Schema** for analytical workloads
* Implement **Slowly Changing Dimension (SCD Type 2)** for provider history tracking
* Perform **analytical queries on healthcare claims and admissions**

---

## Technology Stack

**Programming**

* Python
* Pandas

**Data Warehouse**

* Snowflake

**Query Language**

* SQL

**Concepts Implemented**

* ETL Pipelines
* Dimensional Modeling
* Star Schema Design
* Slowly Changing Dimensions (SCD Type 2)
* Healthcare Claims Analytics

---

## Data Warehouse Architecture

The warehouse follows a **Star Schema design** with one central fact table connected to multiple dimension tables.

### Fact Table

**FACT_CLAIMS_ADMISSIONS**

Stores transactional healthcare data including:

* Admission events
* Insurance claims
* Billing amounts
* Claim status

Key fields include:

* admission_key
* claim_key
* provider_key
* procedure_key
* admission_date_key
* claim_date_key
* billed_amount
* claim_status

---

### Dimension Tables

**DIM_PATIENT**

Stores patient demographic information.

Attributes include:

* patient_id
* first_name
* last_name
* gender
* city
* state
* date_of_birth

---

**DIM_PROVIDER (SCD Type 2)**

Tracks provider information with historical changes using Slowly Changing Dimension Type 2.

Attributes include:

* provider_id
* provider_name
* specialty
* city
* state
* effective_date
* expiry_date
* is_current

---

**DIM_DATE**

Standard time dimension used for analytical reporting.

Attributes include:

* date_key
* full_date
* year
* month
* day

---

**DIM_PROCEDURE**

Stores medical procedure reference data.

Attributes include:

* procedure_id
* procedure_code

---

## ETL Pipeline

The ETL pipeline processes healthcare datasets through the following stages:

1. Raw healthcare datasets are ingested.
2. Data cleaning and preprocessing are performed using Python and Pandas.
3. Cleaned datasets are generated and validated.
4. Data is loaded into Snowflake dimension tables.
5. Fact tables are populated using foreign key relationships.

This pipeline ensures that analytical queries run efficiently on structured warehouse tables.

---

## Example Analytical Queries

The data warehouse enables multiple healthcare analytics use cases, including:

* Admissions per month
* Average claim amount per provider
* Top procedures by cost
* Claim approval vs denial rates
* Provider performance metrics

These insights can help hospitals optimize operations and monitor insurance claim performance.

---

## Project Structure

```
healthcare-data-warehouse
│
├── data
│   ├── raw
│   └── cleaned
│
├── etl
│   └── python_scripts
│
├── sql
│   └── snowflake_queries.sql
│
├── architecture
│   └── star_schema.png
│
└── README.md
```

---

## Key Learning Outcomes

* Designing scalable dimensional data models
* Implementing Slowly Changing Dimensions (SCD Type 2)
* Building ETL pipelines using Python and Pandas
* Structuring analytical data warehouses in Snowflake
* Writing SQL queries for business intelligence use cases

---

## Future Improvements

* Add automated ETL scheduling
* Integrate data orchestration tools such as Airflow
* Build dashboards using Power BI or Tableau
* Implement data quality validation pipelines

---

## Author

Aman
Graduate Engineer | Data Engineering & Analytics
