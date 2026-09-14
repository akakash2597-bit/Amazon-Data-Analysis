# Amazon Sales Data Analysis

## 📌 Project Overview
This project focuses on analyzing Amazon sales data to gain insights into purchasing patterns, customer demographics, and product sales performance. The primary objective is to inspect, clean, and preprocess raw sales data using Python and Pandas to ensure data accuracy and quality before performing exploratory data analysis (EDA).

---

## 🛠️ Data Cleaning & Preprocessing Steps

Below is the summary of the data exploration and cleaning steps implemented in this project:

### 1. Initial Data Inspection & Exploration
```python
import pandas as pd

df = pd.read_csv("amazon_sales.csv")

df.head()
df.info()
df.describe()
df.columns
df.shape
```
* **Data Loading:** `pd.read_csv("amazon_sales.csv")` imports the Pandas library and reads the Amazon sales dataset from a CSV file into a DataFrame named `df`.
* **Data Exploration:** `df.head()`, `df.info()`, `df.describe()`, `df.columns`, and `df.shape` inspect the dataset by displaying the first few rows, column data types, basic summary statistics, column names, and overall row/column dimensions.

---

### 2. Identifying Missing Values
```python
df.isnull().sum()
```
* **Missing Value Identification:** `df.isnull()` scans every cell in the DataFrame, returning `True` for missing (`NaN`) values and `False` for non-null data.
* **Null Count Aggregation:** `.sum()` adds up all the `True` values for each column, displaying the exact total count of missing entries per feature.

---

### 3. Checking for Duplicate Rows
```python
df.duplicated().sum()
```
* **Duplicate Row Identification:** `df.duplicated()` checks each row against previous entries in the DataFrame, returning `True` for duplicate rows and `False` for unique ones.
* **Duplicate Count Aggregation:** `.sum()` adds up all the `True` values to calculate the total number of exact duplicate rows in the dataset.

---

### 4. Removing Duplicate Records
```python
df.drop_duplicates(inplace=True)
```
* **Duplicate Removal:** `df.drop_duplicates()` identifies and removes all duplicate rows from the dataset, keeping only unique records.
* **In-Place Modification:** `inplace=True` applies the change directly to the existing DataFrame `df` without creating a new copy.

---

### 5. Handling Missing Data (Imputation)
```python
df["City"] = df["City"].fillna("Unknown")
```
* **Missing Value Imputation:** `fillna("Unknown")` replaces all missing (`NaN`) values within the `"City"` column with the placeholder string `"Unknown"`.
* **Column Update:** `df["City"] = ...` overwrites the original `"City"` column with the newly imputed series, ensuring no null entries remain in that feature.

---

## 💻 Tech Stack & Prerequisites
* **Python 3.x**
* **Pandas** library (`pip install pandas`)
* **Jupyter Notebook / VS Code** (recommended environment)

---

## 🚀 How to Run the Project
1. Clone this repository or download the project files.
2. Ensure `amazon_sales.csv` is located in the root directory of the project.
3. Install required dependencies:
   ```bash
   pip install pandas
   ```
4. Run the Python script or Jupyter Notebook to execute the data cleaning pipeline.

## 📊 Key Findings

- Generated a total sales revenue of **₹XX,XXX**, highlighting the overall business performance during the analysis period.
- **Electronics** was the highest-performing product category, contributing the largest share of total sales.
- **[Top City]** recorded the highest sales, indicating it as one of the company's strongest markets.
- **[Top Product]** was the best-selling product based on total revenue.
- Sales showed noticeable fluctuations throughout the year, with the highest revenue recorded in **[Month]**, suggesting seasonal demand patterns.
- The average order value was **₹XXX**, providing insight into customer purchasing behavior.
- The analysis identified the top-performing products, categories, and cities, helping support data-driven business decisions.
- Based on the findings, increasing inventory for high-demand products and planning promotions during peak sales periods could improve future business performance.

###  Creator

* **AKASH.V** - [GitHub Profile](https://github.com/akakash2597-bit)
