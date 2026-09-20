# Retail Data Preprocessing & Visualization

## Overview
This repository contains an APEX FDP Week 1 assignment project focused on retail data preprocessing, feature engineering, and visualization using Python.

## Objective
The goal is to transform raw retail transaction records into a clean, analysis-ready dataset and generate business-oriented visual insights for customer behavior, sales trends, city performance, and payment preferences.

## Dataset
Place the dataset file at:

`data/retail_transactions_2000.csv`

Expected columns:
- TransactionID
- CustomerID
- Gender
- Age
- City
- ProductCategory
- Quantity
- Price
- TotalAmount
- PurchaseDate
- PaymentMode

## Data Preprocessing
The notebook includes:
- Data inspection
- Missing value handling
- Duplicate removal
- Categorical standardization
- Invalid numeric value handling
- Date conversion and extraction
- Feature engineering
- Age grouping
- Categorical encoding
- Normalization/scaling
- Final verification checks

## Visualizations
Generated charts:
- `visualizations/age_distribution.png`
- `visualizations/gender_distribution.png`
- `visualizations/top_10_cities.png`
- `visualizations/sales_by_category.png`
- `visualizations/monthly_sales.png`
- `visualizations/payment_mode.png`
- `visualizations/age_group_spending.png`
- `visualizations/city_revenue.png`
- `visualizations/category_payment_heatmap.png`

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Structure
```text
Retail-Data-Preprocessing-Visualization/
│
├── data/
│   ├── retail_transactions_2000.csv
│   └── Retail_Cleaned.csv
│
├── notebooks/
│   └── retail_analysis.ipynb
│
├── visualizations/
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
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run
1. Clone the repository.
2. Install dependencies.
3. Place `retail_transactions_2000.csv` inside the `data` folder.
4. Open the notebook.
5. Run all cells from top to bottom.

Commands:

```bash
pip install -r requirements.txt
jupyter notebook
```

Then open:
`notebooks/retail_analysis.ipynb`

## Output
The project generates:
- Cleaned dataset: `data/Retail_Cleaned.csv`
- Customer demographic visualizations
- Sales and trend visualizations
- Payment analysis charts
- Age-group spending insights
- City-wise revenue insights
- Product-category vs payment-mode heatmap

## Learning Outcomes
This project demonstrates:
- Real-world data cleaning
- Missing-value handling
- Feature engineering
- Data transformation
- Exploratory data analysis
- Data visualization
- Business-oriented data storytelling

## Author
Your Name
