# Bank Marketing Campaign: Data Cleaning & ETL Pipeline

This project focuses on building an ETL (Extract, Transform, Load) pipeline for a bank's marketing campaign dataset. The goal is to take a raw, messy dataset and transform it into three clean, structured files—`client.csv`, `campaign.csv`, and `economics.csv`—optimized for loading into a PostgreSQL database.

## 📋 Project Overview

As the bank plans to launch new marketing efforts, this project ensures that the historical data is cleaned, reformatted, and logically split to support data-driven decision-making and scalable storage.

### Key Objectives:

* **Data Extraction:** Read raw marketing data from `bank_marketing.csv`.
* **Data Transformation:** * Standardizing categorical values (e.g., changing `.` to `_`).
* Converting data types (e.g., boolean mapping for 'yes'/'no' outcomes).
* Engineering new features (e.g., creating a `last_contact_date` from disparate date parts).


* **Data Loading:** Exporting the processed data into three distinct CSV files tailored for a relational database schema.

## 🛠️ Tech Stack

* **Language:** Python 3.x
* **Environment:** Jupyter Notebook
* **Libraries:** Pandas, NumPy

## 📁 Dataset Structure

The raw data is split into three logical tables:

### 1. Client Table (`client.csv`)

| Column | Description |
| --- | --- |
| `client_id` | Unique identifier for each client |
| `age` | Client's age |
| `job` | Occupation (Cleaned: `.` replaced with `_`) |
| `marital` | Marital status |
| `education` | Education level (Cleaned: `.` replaced with `_`, unknowns as nulls) |
| `credit_default` | Whether the client has credit in default (Boolean) |
| `mortgage` | Whether the client has a housing loan (Boolean) |

### 2. Campaign Table (`campaign.csv`)

| Column | Description |
| --- | --- |
| `client_id` | Unique identifier linking to the client |
| `number_contacts` | Contacts performed during this campaign |
| `contact_duration` | Duration of the last contact in seconds |
| `previous_campaign_contacts` | Contacts performed before this campaign |
| `previous_outcome` | Success/failure of the previous campaign (Boolean) |
| `campaign_outcome` | Success/failure of current campaign (Boolean) |
| `last_contact_date` | Aggregated date of contact (YYYY-MM-DD) |

### 3. Economics Table (`economics.csv`)

| Column | Description |
| --- | --- |
| `client_id` | Unique identifier linking to the client |
| `cons_price_idx` | Consumer price index (monthly indicator) |
| `euribor_three_months` | Euro Interbank Offered Rate 3-month (daily indicator) |

## 🚀 How to Run

1. **Clone the repository:**
```bash
git clone https://github.com/shadid-bhai/Bank-Marketing-Campaign-Data.git

```


2. **Install dependencies:**
```bash
pip install pandas numpy

```


3. **Run the Notebook:**
Open `notebook.ipynb` in Jupyter Notebook or VS Code and run all cells to generate the cleaned CSV files.

## 📈 Results

The script produces three clean CSV files ready for database ingestion. By achieving a standardized format, the bank can now:

* Perform efficient SQL queries for campaign analysis.
* Feed cleaned data into Machine Learning models for predicting term deposit subscriptions.
* Maintain a flexible data management system for future campaigns.
