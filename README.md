# 🛒 Retail Data Preprocessing & Visualization

<p align="center">

### 📊 From Raw Transactions to Business Insights

**APEX FDP — Week 1 Assignment**

</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge\&logo=pandas\&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical_Analysis-013243?style=for-the-badge\&logo=numpy\&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C9A9A?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge\&logo=jupyter\&logoColor=white)

</p>

---

## 📌 About The Project

This project is developed as part of the **APEX FDP Week 1 – Exercise on Data Preprocessing & Visualization**.

The project focuses on transforming raw retail transaction data into a **clean, structured, and analysis-ready dataset**.

The analysis explores customer demographics, sales performance, purchasing behavior, payment preferences, city-wise revenue, and product-category trends.

### 🎯 Project Goal

> **Clean the data → Transform the data → Analyze the data → Visualize the insights**

The final objective is to create a reliable dataset and meaningful visualizations that can support better **marketing, sales, and inventory decisions**.

---

# 📖 Table of Contents

* [Project Overview](#-project-overview)
* [Objectives](#-objectives)
* [Dataset](#-dataset)
* [Data Preprocessing](#-data-preprocessing)
* [Feature Engineering](#-feature-engineering)
* [Data Visualization](#-data-visualization)
* [Key Results](#-key-results)
* [Project Structure](#-project-structure)
* [Technologies Used](#-technologies-used)
* [How to Run](#-how-to-run)
* [Learning Outcomes](#-learning-outcomes)
* [Future Improvements](#-future-improvements)
* [Author](#-author)

---

# 🔎 Project Overview

A retail company operating across multiple cities wants to understand its customers and sales performance.

However, raw transactional data may contain:

* Missing values
* Duplicate transactions
* Inconsistent categorical values
* Invalid numerical values
* Incorrect or incomplete dates
* Unstructured information

This project addresses these issues through systematic **data preprocessing and exploratory data analysis (EDA)**.

---

# 🎯 Objectives

## 🧹 Data Preprocessing

* Inspect dataset structure
* Identify missing values
* Identify duplicate records
* Handle missing Age values
* Handle missing City values
* Remove records with missing critical fields
* Standardize categorical values
* Handle invalid Quantity and Price values
* Convert dates into appropriate formats

## ⚙️ Feature Engineering

Create useful features such as:

* `TotalAmount`
* `Month`
* `DayOfWeek`
* `AgeGroup`

## 📊 Data Visualization

Create visualizations for:

* Age distribution
* Gender distribution
* Top 10 cities
* Sales by product category
* Monthly sales trend
* Payment mode usage
* Average spending by age group
* City-wise revenue
* Product category vs payment mode

---

# 🗂️ Dataset

The dataset contains retail transaction records.

### Dataset Attributes

| Column            | Description                            |
| ----------------- | -------------------------------------- |
| `TransactionID`   | Unique identifier for each transaction |
| `CustomerID`      | Unique identifier for each customer    |
| `Gender`          | Customer gender                        |
| `Age`             | Customer age                           |
| `City`            | City where the purchase occurred       |
| `ProductCategory` | Category of purchased product          |
| `Quantity`        | Number of units purchased              |
| `Price`           | Price per unit in ₹                    |
| `TotalAmount`     | Total transaction amount               |
| `PurchaseDate`    | Date of purchase                       |
| `PaymentMode`     | Payment method used                    |

---

# 🔄 Data Processing Workflow

```text
                 ┌─────────────────────┐
                 │   Raw Retail Data   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Data Inspection   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Data Cleaning    │
                 └──────────┬──────────┘
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
        Missing Data    Duplicates   Invalid Values
              │             │             │
              └─────────────┼─────────────┘
                            ▼
                 ┌─────────────────────┐
                 │ Feature Engineering │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Transformation &    │
                 │     Encoding        │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Final Verification  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Visualization    │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │  Business Insights  │
                 └─────────────────────┘
```

---

# 🧹 Data Preprocessing

## 1. Data Inspection

The dataset is inspected using Pandas to understand:

* Dataset dimensions
* Column names
* Data types
* Statistical information
* Missing values
* Duplicate records
* Unique categorical values

---

## 2. Missing Value Handling

The following strategy is used:

| Column            | Treatment                            |
| ----------------- | ------------------------------------ |
| `Age`             | Missing values replaced using median |
| `City`            | Missing values replaced using mode   |
| `TransactionID`   | Rows with missing values removed     |
| `ProductCategory` | Rows with missing values removed     |

---

## 3. Duplicate Removal

Duplicate transactions are identified and removed to ensure that the analysis is not affected by repeated records.

---

## 4. Categorical Data Cleaning

Inconsistent categorical values are standardized.

For example:

```text
m
male
MALE
Male
```

are converted to:

```text
Male
```

Similarly, other categorical fields are cleaned to maintain consistency.

---

## 5. Invalid Numerical Values

The following columns are checked for invalid values:

* `Quantity`
* `Price`

Negative and zero values are identified and handled appropriately before analysis.

---

# ⚙️ Feature Engineering

## 💰 Total Amount

The total transaction amount is calculated using:

```text
TotalAmount = Quantity × Price
```

This ensures that transaction revenue is available for analysis.

---

## 📅 Month

The month is extracted from `PurchaseDate` to analyze monthly sales trends.

---

## 📆 Day of Week

The day of the week is extracted from the purchase date to support further customer behavior analysis.

---

## 👥 Age Group

Customers are categorized into:

| Age Group |
| --------- |
| 18–25     |
| 26–40     |
| 41–60     |
| 60+       |

This allows spending behavior to be compared across different customer age groups.

---

# 📊 Data Visualization

The project generates **9 major visualizations**.

---

## 1️⃣ Customer Age Distribution

Shows the distribution of customers across different age ranges.

![Age Distribution](visualizations/age_distribution.png)

---

## 2️⃣ Gender Distribution

Shows the distribution of transactions/customers by gender.

![Gender Distribution](visualizations/gender_distribution.png)

---

## 3️⃣ Top 10 Cities

Displays the cities with the highest number of transactions.

![Top 10 Cities](visualizations/top_10_cities.png)

---

## 4️⃣ Sales by Product Category

Shows the total sales generated by each product category.

![Sales by Category](visualizations/sales_by_category.png)

---

## 5️⃣ Monthly Sales Trend

Shows how sales change over time.

![Monthly Sales](visualizations/monthly_sales.png)

---

## 6️⃣ Payment Mode Usage

Shows the distribution of different payment methods.

![Payment Mode](visualizations/payment_mode.png)

---

## 7️⃣ Average Spending by Age Group

Compares average spending across different customer age groups.

![Age Group Spending](visualizations/age_group_spending.png)

---

## 8️⃣ City-wise Revenue

Shows the revenue contribution of different cities.

![City Revenue](visualizations/city_revenue.png)

---

## 9️⃣ Product Category vs Payment Mode

A heatmap showing the relationship between product categories and payment methods.

![Category Payment Heatmap](visualizations/category_payment_heatmap.png)

---

# 📈 Key Results

> **The values in this section should be updated with the actual results generated from the dataset.**

## 📊 Dataset Summary

| KPI                       |      Actual Result |
| ------------------------- | -----------------: |
| Total Transactions        |   **[Add Result]** |
| Total Customers           |   **[Add Result]** |
| Total Revenue             | **₹ [Add Result]** |
| Average Transaction Value | **₹ [Add Result]** |
| Number of Cities          |   **[Add Result]** |
| Product Categories        |   **[Add Result]** |

---

## 🏆 Top Performing Categories

| Rank | Product Category | Total Sales |
| ---: | ---------------- | ----------: |
|    1 | **[Category]**   |  ₹ [Result] |
|    2 | **[Category]**   |  ₹ [Result] |
|    3 | **[Category]**   |  ₹ [Result] |
|    4 | **[Category]**   |  ₹ [Result] |
|    5 | **[Category]**   |  ₹ [Result] |

---

## 🏙️ Top Performing Cities

| Rank | City       |    Revenue |
| ---: | ---------- | ---------: |
|    1 | **[City]** | ₹ [Result] |
|    2 | **[City]** | ₹ [Result] |
|    3 | **[City]** | ₹ [Result] |
|    4 | **[City]** | ₹ [Result] |
|    5 | **[City]** | ₹ [Result] |

---

## 💳 Payment Analysis

The analysis identifies the most frequently used payment methods.

**Most Used Payment Mode:** `[Actual Result]`

**Percentage:** `[Actual Result]%`

---

## 👥 Customer Spending

The analysis compares average spending between:

* 18–25
* 26–40
* 41–60
* 60+

**Highest Average Spending Age Group:** `[Actual Result]`

**Average Spending:** `₹ [Actual Result]`

---

# 💡 Business Insights

Based on the actual analysis, this project can help identify:

### 🛍️ Product Insights

Which product categories generate the highest revenue and which categories may require additional attention.

### 🏙️ City Insights

Which cities contribute significantly to overall revenue and transaction volume.

### 📅 Seasonal Insights

How sales change from month to month and whether particular periods show higher demand.

### 💳 Payment Insights

Which payment methods customers prefer most.

### 👥 Customer Insights

How spending behavior differs across customer age groups.

> **Important:** All numerical conclusions should be based on the actual processed dataset.

---

# 📁 Project Structure

```text
Retail-Data-Preprocessing-Visualization/
│
├── 📂 data/
│   ├── retail_transactions_2000.csv
│   └── Retail_Cleaned.csv
│
├── 📂 notebooks/
│   └── retail_analysis.ipynb
│
├── 📂 visualizations/
│   ├── age_distribution.png
│   ├── gender_distribution.png
│   ├── top_10_cities.png
│   ├── sales_by_category.png
│   ├── monthly_sales.png
│   ├── payment_mode.png
│   ├── age_group_spending.png
│   ├── city_revenue.png
│   └── category_payment_heatmap.png
│
├── 📄 README.md
├── 📄 requirements.txt
└── 📄 .gitignore
```

---

# 🛠️ Technologies Used

| Technology          | Purpose                           |
| ------------------- | --------------------------------- |
| 🐍 Python           | Data analysis                     |
| 🐼 Pandas           | Data preprocessing                |
| 🔢 NumPy            | Numerical operations              |
| 📊 Matplotlib       | Visualization                     |
| 🎨 Seaborn          | Statistical visualization         |
| 📓 Jupyter Notebook | Interactive analysis              |
| 🐙 GitHub           | Version control & project hosting |

---

# 🚀 How to Run

## 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

## 2. Open the Project

```bash
cd Retail-Data-Preprocessing-Visualization
```

## 3. Install Required Libraries

```bash
pip install -r requirements.txt
```

## 4. Add the Dataset

Place the original dataset inside:

```text
data/
```

The file should be named:

```text
retail_transactions_2000.csv
```

## 5. Open Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
notebooks/retail_analysis.ipynb
```

## 6. Run the Notebook

Run all cells sequentially.

The notebook will:

```text
Load Data
    ↓
Inspect Data
    ↓
Clean Data
    ↓
Engineer Features
    ↓
Transform Data
    ↓
Verify Data
    ↓
Generate Visualizations
    ↓
Save Clean Dataset
```

---

# 📦 Output Files

After successful execution, the project generates:

### Clean Dataset

```text
data/Retail_Cleaned.csv
```

### Visualizations

```text
visualizations/
│
├── age_distribution.png
├── gender_distribution.png
├── top_10_cities.png
├── sales_by_category.png
├── monthly_sales.png
├── payment_mode.png
├── age_group_spending.png
├── city_revenue.png
└── category_payment_heatmap.png
```

---

# 🎓 Learning Outcomes

This project demonstrates practical knowledge of:

* ✅ Data Inspection
* ✅ Data Cleaning
* ✅ Missing Value Handling
* ✅ Duplicate Removal
* ✅ Categorical Data Standardization
* ✅ Feature Engineering
* ✅ Data Encoding
* ✅ Numerical Transformation
* ✅ Exploratory Data Analysis
* ✅ Data Visualization
* ✅ Business Data Storytelling
* ✅ Git & GitHub Project Management

---

# 🔮 Future Improvements

Possible future improvements include:

* 📊 Interactive dashboard using Power BI
* 🌐 Interactive Plotly dashboard
* 🤖 Customer segmentation using Machine Learning
* 📈 Sales forecasting
* 🔍 Customer churn analysis
* 🧠 Predictive analytics
* 📱 Real-time sales monitoring dashboard

---

# 📌 Academic Information

**Programme:** APEX Faculty Development Programme

**Assignment:** Week 1 – Exercise on Data Preprocessing & Visualization

**Domain:** Data Analytics / Artificial Intelligence

**Focus Areas:**

```text
Data Cleaning
     +
Data Preprocessing
     +
Feature Engineering
     +
Exploratory Data Analysis
     +
Data Visualization
```

---

# 👨‍💻 Author

### **Your Name**

🎓 B.Tech Computer Science Engineering
🔐 Specialization: Cyber Security
📚 APEX FDP — Week 1
💻 Retail Data Analysis Project

---

<p align="center">

## ⭐ If you found this project useful, consider giving it a star!

### 🐍 Python • 📊 Data Analysis • 💡 Business Insights

**Turning Data into Insights 🚀**

</p>
