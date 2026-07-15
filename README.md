# Data Engineering Foundation: ETL, Web Scraping & SQLite Database Management

A production-oriented collection of Python projects demonstrating the core concepts of **Data Engineering**. This repository covers the complete data lifecycle—from extracting data from multiple sources, transforming and cleaning datasets, scraping live web content, storing structured data in relational databases, and maintaining execution logs for auditing.

The project is designed as a learning resource for anyone beginning their journey in **Data Engineering, Data Analytics, or Data Science**.

---

## Features

* **Multi-format ETL Pipeline**

  * Extract data from CSV, JSON, and XML files
  * Merge heterogeneous datasets into a unified structure
  * Apply data normalization and transformation
  * Export processed data to a target CSV

* **Web Scraping Automation**

  * Collect structured information from web pages
  * Parse HTML using BeautifulSoup
  * Clean and filter scraped records
  * Save results to CSV and SQLite database

* **SQLite Database Integration**

  * Create lightweight relational databases
  * Import datasets using Pandas
  * Execute SQL queries
  * Retrieve and analyze stored records

* **Logging & Auditing**

  * Record ETL execution events
  * Track pipeline progress
  * Generate timestamped audit logs
  * Improve debugging and monitoring
---

# Project Structure
```text
Data-Engineering-Foundation/
│
├── data/
│   ├── sample.csv
│   ├── sample.json
│   ├── sample.xml
│   └── INSTRUCTOR.csv
│
├── output/
│   ├── transformed_data.csv
│   ├── top_50_films.csv
│   ├── Movies.db
│   └── STAFF.db
│
├── logs/
│   └── log_file.txt
│
├── etl_pipeline.py
├── web_scraping_pipeline.py
├── sqlite_database.py
├── logging.py
│
├── requirements.txt
└── README.md
```
---
# Technologies Used

| Technology      | Purpose                              |
| --------------- | ------------------------------------ |
| Python 3        | Core programming language            |
| Pandas          | Data manipulation and transformation |
| Glob            | File discovery                       |
| XML ElementTree | XML parsing                          |
| Requests        | HTTP requests                        |
| BeautifulSoup4  | HTML parsing and web scraping        |
| SQLite3         | Relational database management       |
| Datetime        | Logging timestamps                   |
---

# ETL Pipeline
The ETL pipeline processes multiple data formats into a standardized dataset.

## Architecture

```text
              +------------+
              | CSV Files  |
              +------------+
                     |
                     |
              +------------+
              | JSON Files |
              +------------+
                     |
                     |
              +------------+
              | XML Files  |
              +------------+
                     |
                     ▼
          +--------------------+
          |     Extraction     |
          +--------------------+
                     |
                     ▼
          +--------------------+
          |   Transformation   |
          | Unit Normalization |
          +--------------------+
                     |
                     ▼
          +--------------------+
          |        Load        |
          | transformed_data   |
          +--------------------+
```

## Workflow

### Extract
* Reads all CSV files
* Reads newline-delimited JSON files
* Parses XML documents
* Combines all records into a single DataFrame

### Transform
Performs unit normalization:

| Attribute | Conversion         |
| --------- | ------------------ |
| Height    | Inches → Meters    |
| Weight    | Pounds → Kilograms |

### Load
Exports the cleaned dataset into:

```text
transformed_data.csv
```
---

# Automated Web Scraping Pipeline

This module demonstrates how to collect structured information from an archived webpage.

## Workflow

```text
Website
    │
    ▼
Requests
    │
    ▼
BeautifulSoup
    │
    ▼
Extract HTML Table
    │
    ▼
Pandas DataFrame
    │
    ├────────► CSV
    │
    └────────► SQLite Database
```

## Processing Steps
* Download webpage content
* Parse HTML tables
* Extract movie information
* Convert data into a DataFrame
* Filter movies released after 2000
* Save results to CSV
* Store records in SQLite

---

# SQLite Database Management

SQLite provides a lightweight relational database for local storage.

## Operations Performed

* Create database connection
* Load CSV into a DataFrame
* Create SQL table
* Insert records
* Execute SQL queries
* Retrieve results
* Close database connection

# Logging System

Every execution stage is recorded with timestamps for auditing purposes.

## Logged Events
* ETL Job Started
* Extraction Started
* Extraction Completed
* Transformation Started
* Transformation Completed
* Loading Started
* Loading Completed
* ETL Job Finished
---

# Installation

Clone the repository:

```bash
git clone https://github.com/your-username/Data-Engineering-Foundation.git
```

Move into the project directory:

```bash
cd Data-Engineering-Foundation
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

# Requirements

```text
pandas
requests
beautifulsoup4
lxml
```

Install manually:

```bash
pip install pandas requests beautifulsoup4 lxml
```

---

# Running the Projects

Run the ETL pipeline:

```bash
python etl_pipeline.py
```

Run the web scraping pipeline:

```bash
python web_scraping_pipeline.py
```

Run the SQLite database example:

```bash
python sqlite_database.py
```

---

# Learning Outcomes

By completing these projects, you will understand how to:

* Design end-to-end ETL pipelines
* Process structured and semi-structured datasets
* Perform data transformation and normalization
* Build automated web scraping workflows
* Store data in relational databases
* Execute SQL queries with SQLite
* Implement execution logging and auditing
* Organize data engineering projects using industry-inspired practices

---

# Future Improvements

* Add Apache Airflow for workflow orchestration
* Integrate PostgreSQL and MySQL
* Support incremental ETL pipelines
* Add data validation with Great Expectations
* Dockerize the project
* Create unit tests using pytest
* Integrate cloud storage (AWS S3, Azure Blob Storage, GCP Storage)
* Schedule pipelines using cron or Airflow
* Add CI/CD with GitHub Actions

---

# Author

**Your Name**

Aspiring **Data Engineer | Data Analyst | Python Developer**

---

# License

This project is licensed under the **MIT License**. Feel free to use, modify, and distribute it for educational and personal purposes.
