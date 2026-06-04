# 🌦️ Weather ETL Pipeline with Apache Airflow, Docker & AWS RDS

## Overview

This project is a **production-style Weather ETL Pipeline** built using **Apache Airflow (Astro Runtime), Docker, PostgreSQL, and AWS RDS**.

The pipeline dynamically ingests weather data based on **latitude and longitude coordinates**, transforms the raw API response into structured data, and stores it in PostgreSQL for analytics and downstream use cases.

The goal of this project was to move beyond toy projects and build a workflow that reflects **real-world data engineering practices**, including orchestration, cloud deployment, and database validation.

---

## 🏗️ Architecture

**Input → Extract → Transform → Load**

### 📍 Input

Users provide:

* Latitude
* Longitude

### 🌍 Extract

Weather data is retrieved dynamically from the **Open-Meteo API**.

The pipeline collects:

* Temperature
* Wind Speed
* Wind Direction
* Weather Conditions / Weather Codes

Airflow connections are used for configuration management:

* `open_meteo_api`
* `postgres_default`

---

### 🔄 Transform

Raw API responses are cleaned and transformed into a structured format for downstream analytics.

This helps create a cleaner and more reusable data model.

---

### 🗄️ Load

Processed weather data is stored in **PostgreSQL**.

Development workflow:

* Local PostgreSQL using Docker
* Database validation with **DBeaver**
* SQL queries used to inspect and verify ingested data
* Migration to **AWS PostgreSQL RDS** for cloud deployment

---

## ⚙️ Technologies Used

* **Python**
* **Apache Airflow (Astro Runtime)**
* **Docker**
* **PostgreSQL**
* **AWS RDS**
* **DBeaver**
* **SQL**
* **Open-Meteo API**

---

## 🔄 Pipeline Workflow

The pipeline follows an ETL orchestration pattern:

1. **Extract** weather data from Open-Meteo API
2. **Transform** raw payload into structured data
3. **Load** data into PostgreSQL

Airflow features used:

* TaskFlow API
* HTTP Hooks
* Postgres Hooks
* XCom for inter-task communication

---

## 🛠️ Project Features

✅ Dynamic weather ingestion using coordinates
✅ Dockerized local development
✅ Airflow orchestration with Astro Runtime
✅ PostgreSQL database integration
✅ Cloud deployment with AWS RDS
✅ SQL-based validation using DBeaver

---

## ⚠️ Failure Handling Considerations

This project was designed with production thinking in mind.

Potential failure scenarios considered:

* API request failures
* Invalid coordinates
* Missing or incomplete payloads
* Database connection issues

Planned improvements include:

* Retry mechanisms
* Better error handling
* Parameterized DAG runs
* Data quality checks

---

## 🚀 Future Improvements

* Dynamic user-submitted coordinates
* Parameterized DAG execution
* Automated alerting and monitoring
* Improved retry and failure recovery logic
* Historical weather ingestion

---

## 📌 Key Learning

This project reinforced an important lesson:

**Data Engineering is not just moving data — it’s designing reliable systems that scale.**
