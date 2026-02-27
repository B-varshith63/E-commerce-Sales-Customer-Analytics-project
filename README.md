# 🛒 E-commerce Sales & Customer Analytics

A complete end-to-end data analytics project covering data cleaning, SQL analysis, RFM customer segmentation, and an interactive Power BI dashboard — built on a synthetic e-commerce dataset of **100,000 transactions**.

---

## 📁 Project Structure

```
ecommerce-analytics/
│
├── data/
│   ├── synthetic_ecommerce_data.csv       # Raw dataset (100K transactions)
│   ├── ecommerce_cleaned.csv              # Cleaned & feature-engineered dataset
│   └── ecommerce_rfm.csv                  # RFM scores per customer
│
├── notebooks/
│   ├── Python_data_cleaning.ipynb         # Data cleaning & feature engineering
│   ├── ecommerce_sql_analysis.ipynb       # SQL-based business analysis
│   └── ecommerce_rfm_analysis.ipynb       # RFM segmentation analysis
│
├── results/
│   ├── ecommerce_sql_results.xlsx         # SQL query outputs & summaries
│   └── ecommerce_rfm_results.xlsx         # RFM segment results & metrics
│
├── dashboard/
│   └── Ecommerce_Analytics_Dashboard.pbix # Power BI dashboard
│
└── README.md
```

---

## 📊 Dataset Overview

| Attribute | Detail |
|---|---|
| Total Transactions | 100,000 |
| Unique Customers | 19,865 |
| Unique Products | 1,000 |
| Date Range | July 2023 – December 2024 |
| Categories | Electronics, Home Appliances, Toys, Clothing, Books |
| Regions | Europe, Asia, North America |
| Total Revenue | $55,311,081 |
| Total Profit | $44,263,357 |
| Overall ROAS | 5.01x |

**Key columns:** `Transaction_ID`, `Customer_ID`, `Product_ID`, `Transaction_Date`, `Units_Sold`, `Discount_Applied`, `Revenue`, `Clicks`, `Impressions`, `Conversion_Rate`, `Category`, `Region`, `Ad_CTR`, `Ad_CPC`, `Ad_Spend`

---

## 🔧 Phase 1 — Data Cleaning (`Python_data_cleaning.ipynb`)

Performed using **Python (Pandas & NumPy)**:

- Removed duplicate transactions and dropped rows with null values in critical fields (`Transaction_ID`, `Customer_ID`, `Transaction_Date`, `Revenue`)
- Filled missing ad metrics (`Discount_Applied`, `Clicks`, `Impressions`, `Ad_Spend`, `Ad_CTR`, `Ad_CPC`) with 0
- Parsed and standardized `Transaction_Date`, then extracted `Year`, `Month`, `Quarter`, `YearMonth` columns
- Removed records with negative revenue or zero units sold
- Standardized `Category` and `Region` text (strip + title case)

**Engineered Features:**

| Column | Formula |
|---|---|
| `Profit` | Revenue − Ad_Spend |
| `Profit_Margin_Pct` | (Profit / Revenue) × 100 |
| `Revenue_Per_Unit` | Revenue / Units_Sold |
| `ROAS` | Revenue / Ad_Spend |

---

## 🗄️ Phase 2 — SQL Analysis (`ecommerce_sql_analysis.ipynb`)

Business questions answered using SQL queries on the cleaned dataset:

- Monthly and quarterly revenue trends
- Top-performing product categories by revenue and profit margin
- Regional sales performance comparison
- Ad spend efficiency (ROAS) by category and region
- Conversion rate analysis by product and channel
- High-value customer identification

Results exported to `ecommerce_sql_results.xlsx`.

---

## 👥 Phase 3 — RFM Customer Segmentation (`ecommerce_rfm_analysis.ipynb`)

**RFM (Recency, Frequency, Monetary)** analysis was used to segment customers into actionable groups:

- **Recency** — Days since the customer's last purchase
- **Frequency** — Total number of transactions
- **Monetary** — Total revenue generated

Customers were scored on a 1–5 scale for each dimension and grouped into segments such as:

| Segment | Description |
|---|---|
| Champions | Bought recently, buy often, spend the most |
| Loyal Customers | Regular buyers with high spend |
| At Risk | Were great customers but haven't bought recently |
| Need Attention | Above-average recency, frequency, and spend — but declining |
| Lost | Lowest recency, frequency, and spend scores |

Results exported to `ecommerce_rfm_results.xlsx`.

---

## 📈 Phase 4 — Power BI Dashboard (`Ecommerce_Analytics_Dashboard.pbix`)

An interactive dashboard built in **Power BI** covering:

- Revenue & profit KPIs (overall and over time)
- Sales trends by month, quarter, and year
- Category and region performance breakdown
- Ad performance metrics (ROAS, CTR, CPC, Ad Spend)
- RFM customer segment distribution
- Top customers and top products by revenue

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python (Pandas, NumPy) | Data cleaning & feature engineering |
| SQL (via Jupyter) | Business analysis & aggregations |
| Power BI | Interactive dashboard & visualization |
| Excel | Exporting and sharing tabular results |
| Jupyter Notebook | Development environment |

---

## 🚀 Getting Started

**Prerequisites:**
```
Python 3.8+
pandas
numpy
jupyter
openpyxl
```

**Install dependencies:**
```bash
pip install pandas numpy jupyter openpyxl
```

**Run the notebooks in order:**
```
1. Python_data_cleaning.ipynb
2. ecommerce_sql_analysis.ipynb
3. ecommerce_rfm_analysis.ipynb
```

**Update file paths** in each notebook to point to your local data directory before running.

---

## 📌 Key Insights

- Overall **ROAS of 5.01x** indicates strong return on advertising spend across all categories.
- **Profit margin of ~80%** (after ad spend) reflects efficient ad operations.
- RFM segmentation revealed that a small portion of customers (Champions + Loyal) drive a disproportionate share of revenue — a classic Pareto effect.
- Regional and category breakdowns highlight opportunities for targeted marketing and inventory optimization.

---

## 👤 Author

**Varshith Bhimanathi**
Data Analyst | Python · SQL · Power BI

---

## 📄 License

This project uses a synthetic dataset generated for educational and portfolio purposes. Feel free to fork, adapt, and build on it.
