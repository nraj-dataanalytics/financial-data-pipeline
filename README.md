# Financial Data Pipeline for Market Analytics

## Overview

This project builds an end-to-end financial data pipeline that extracts, cleans, and validates stock market datasets to produce an analytics-ready dataset for financial analysis and reporting.

Financial datasets often arrive in raw formats that are inconsistent, poorly structured, or not suitable for analytical workflows. The goal of this project is to transform raw financial market data into a clean, validated structure that can support analytics, modeling, and dashboard development.

The pipeline processes multiple datasets including stock price data, S&P 500 index data, and company metadata, preparing them for integration and financial analysis.

---

## Project Objectives

The key objectives of this project are:

- Extract financial market data using Python
- Clean and standardize raw datasets
- Validate data integrity and logical consistency
- Transform datasets into an analytics-ready structure
- Prepare data for financial analysis and visualization

---

## Datasets Used

The pipeline processes three primary datasets.

### 1. Stock Prices Dataset

Historical stock price data for major technology companies.

Companies included:
- Apple (AAPL)
- Microsoft (MSFT)
- Amazon (AMZN)
- NVIDIA (NVDA)
- Tesla (TSLA)

Variables:
- Open
- High
- Low
- Close
- Volume
- Date
- Ticker

This dataset contains daily trading data from 2015–2024.

---

### 2. S&P 500 Index Dataset

The S&P 500 index dataset provides a benchmark for the overall market.

Variables:
- Date
- Open
- High
- Low
- Close
- Volume

This dataset allows stock performance to be analyzed relative to broader market movements.

---

### 3. S&P 500 Companies Dataset

This dataset contains metadata for companies in the S&P 500 index.

Variables include:
- Ticker Symbol
- Company Name
- Sector
- Industry
- Headquarters Location
- Date Added to Index
- CIK Identifier
- Founded Year

This dataset enriches financial analysis with business context such as sector and industry classification.

---

## Data Pipeline Architecture

The project follows a simplified ETL architecture.


Data Extraction
↓
Raw Data Layer
↓
Data Cleaning Pipeline
↓
Data Validation
↓
Clean Data Layer
↓
Dataset Integration
↓
Analytics and Visualization


---

## Data Extraction

Financial data is collected using the **yfinance API** in Python.

The extraction scripts automatically download:

- S&P 500 market index data
- Stock price data for selected companies
- Historical financial records

The extracted data is stored in the **raw data layer** before cleaning and transformation.

---

## Data Cleaning Pipeline

The cleaning pipeline standardizes raw datasets to make them suitable for analysis.

Key transformations include:

- Removing metadata rows
- Standardizing column names
- Converting data types
- Reshaping datasets from wide to long format
- Extracting ticker symbols and financial metrics
- Reconstructing analytical dataset structure

The final dataset structure follows a tidy format where each row represents:

**One stock on one trading day**

Columns:

- Date
- Ticker
- Open
- High
- Low
- Close
- Volume

---

## Data Validation

After cleaning, the datasets are validated to ensure analytical reliability.

Validation checks include:

- Dataset shape verification
- Column structure validation
- Missing value detection
- Duplicate record checks
- Duplicate Date–Ticker pair validation
- Logical financial rule validation (High ≥ Low)
- Negative value checks for financial variables

These steps ensure the dataset is structurally consistent and logically valid.

---

## Technologies Used

- Python
- Pandas
- NumPy
- yFinance API
- Data Transformation (ETL)
- Data Validation Techniques

---

## Project Structure


financial-data-pipeline/

data/
raw/
stock_prices.csv
sp500_index.csv
sp500_companies.csv

cleaned/
stock_prices_clean.csv
sp500_index_clean.csv
sp500_companies_clean.csv

notebooks/
01_clean_stock_prices.ipynb
02_clean_sp500.ipynb
03_clean_company_info.ipynb

scripts/
data_extraction.py

README.md


---

## Business Applications

The cleaned datasets can support several financial analytics use cases.

Examples include:

- Portfolio performance analysis
- Market trend analysis
- Sector-level performance comparisons
- Risk and volatility analysis
- Financial dashboard development
- Investment data reporting pipelines

---

## Future Improvements

Potential extensions of the project include:

- Integrating additional financial assets
- Building automated ETL scheduling
- Adding financial feature engineering
- Developing predictive models for market trends
- Creating Power BI dashboards for financial insights

---

## Author

Nandani Raj  
MS Business Analytics  
University of New Haven

Portfolio:  
https://nrajdataanalytics.com
