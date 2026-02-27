# 🛒 E-Commerce Analytics — End-to-End Data Analytics Project

> **Analyzing 100,000 transactions to uncover revenue drivers, customer behavior, and profitability insights using Python, SQL, and Power BI.**

---

## 📌 Business Problem

An e-commerce company wants to understand:
- 👉 Where is revenue coming from?
- 👉 Which customers are most valuable?
- 👉 Which products and categories are most profitable?
- 👉 How to improve customer retention and business decisions?

---

## 🏆 Project Highlights

| Metric | Value |
|--------|-------|
| 💰 Total Revenue | $55,311,081 |
| 📈 Total Profit | $44,263,357 |
| 🛒 Total Transactions | 100,000 |
| 👥 Unique Customers | 19,865 |
| 📦 Unique Products | 1,000 |
| 📢 Overall ROAS | 5.01x |
| 🗓️ Date Range | Dec 2023 – Dec 2024 |
| 🌍 Regions | Asia, Europe, North America |
| 🗂️ Categories | Electronics, Books, Toys, Clothing, Home Appliances |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| 🐍 Python (Pandas, NumPy, Matplotlib) | Data cleaning & RFM analysis |
| 🗄️ SQL (SQLite via Python) | Business queries & analysis |
| 📊 Power BI Desktop | 4-page interactive dashboard |
| 📓 Jupyter Notebook | Code & documentation |
| 📁 Excel | Results storage |

---

## 📁 Repository Structure

```
ecommerce-analytics/
│
├── 📓 notebooks/
│   ├── Python_data_cleaning.ipynb       ← Step 1: Data cleaning
│   ├── ecommerce_sql_analysis.ipynb     ← Step 2: SQL queries
│   └── ecommerce_rfm_analysis.ipynb     ← Step 3: RFM segmentation
│
├── 📊 data/
│   ├── ecommerce_cleaned.csv            ← Cleaned dataset (100K rows, 24 cols)
│   └── ecommerce_rfm.csv                ← RFM scores (19,865 customers)
│
├── 📈 results/
│   ├── ecommerce_sql_results.xlsx       ← SQL results (5 sheets)
│   └── ecommerce_rfm_results.xlsx       ← RFM segment summary
│
├── 📉 charts/
│   └── rfm_segments_chart.png           ← RFM visualization
│
├── 📋 dashboard/
│   └── Ecommerce_Analytics_Dashboard.pbix  ← Power BI dashboard
│
└── 📄 README.md
```

> ⚠️ Raw dataset not included due to file size. Download from [Kaggle — Comprehensive Synthetic E-Commerce Dataset](https://www.kaggle.com/datasets/imranalishahh/comprehensive-synthetic-e-commerce-dataset)

---

## ⚙️ Step 1 — Data Cleaning (Python)

**Notebook:** `notebooks/Python_data_cleaning.ipynb`

| Task | Details |
|------|---------|
| Removed duplicates | Based on Transaction_ID |
| Handled null values | Dropped critical nulls, filled numeric nulls with 0 |
| Fixed date format | Parsed to datetime, extracted Year/Month/Quarter |
| Removed negatives | Revenue ≥ 0, Units_Sold > 0 |
| Standardized text | Title case for Category and Region |
| Created new columns | Profit, Profit_Margin_Pct, Revenue_Per_Unit, ROAS |

**Output:** `ecommerce_cleaned.csv` — 100,000 rows × 24 columns

---

## 🗄️ Step 2 — SQL Analysis

**Notebook:** `notebooks/ecommerce_sql_analysis.ipynb`

### Sample Query
```sql
-- Monthly Revenue Trend
SELECT YearMonth, SUM(Revenue) AS Monthly_Revenue
FROM ecommerce
GROUP BY YearMonth
ORDER BY YearMonth;
```

### All Queries Built (12 total)

| Category | Queries |
|----------|---------|
| Sales | Total revenue, monthly trend, top 10 products, revenue by category/region |
| Customer | New vs repeat customers, top 10 customers, avg order value |
| Profitability | Profit by category, discount impact, monthly profit trend |
| Marketing | ROAS by category, ad spend efficiency |

**Output:** `results/ecommerce_sql_results.xlsx` — 5 sheets

---

## 🎯 Step 3 — RFM Customer Segmentation

**Notebook:** `notebooks/ecommerce_rfm_analysis.ipynb`

Each of 19,865 customers scored **1–5** on:
- **R — Recency:** Days since last purchase (lower = better)
- **F — Frequency:** Number of orders (higher = better)
- **M — Monetary:** Total revenue generated (higher = better)

### Segment Results

| Segment | Customers | % of Base | Revenue | Avg Spend |
|---------|-----------|-----------|---------|-----------|
| 🏆 Champion | 3,295 | 16.6% | $15.2M | $4,620 |
| 💛 Loyal | 3,857 | 19.4% | $13.4M | $3,483 |
| 🌱 Potential Loyal | 3,523 | 17.7% | $6.4M | $1,817 |
| 📢 Needs Attention | 3,709 | 18.7% | $6.3M | $1,709 |
| 🚨 Cannot Lose | 1,396 | 7.0% | $6.0M | $4,303 |
| ⚠️ At Risk | 1,336 | 6.7% | $4.0M | $2,986 |
| ❌ Lost | 2,749 | 13.8% | $3.9M | $1,424 |

![RFM Segments](charts/rfm_segments_chart.png)

---

## 📊 Step 4 — Power BI Dashboard (4 Pages)

**File:** `dashboard/Ecommerce_Analytics_Dashboard.pbix`

| Page | Content |
|------|---------|
| 1️⃣ Executive Overview | KPI cards, monthly trend, revenue by category & region |
| 2️⃣ Product Performance | Top 10 products, revenue vs profit, profit margin % |
| 3️⃣ Customer Analytics | RFM segments, top customers, new vs repeat (96.72% repeat!) |
| 4️⃣ Geography Insights | Interactive map, revenue by region, region × category matrix |

---

## 💡 Key Business Insights

**1. Clothing Drives Highest Profit Margins**
> Clothing delivers 54.4% profit margin vs Home Appliances at 36.5%. Reallocating ad budget to Clothing improves overall profitability.

**2. Top 36% of Customers Drive 51.8% of Revenue**
> Champion customers (16.6%) generate $15.2M alone. A VIP loyalty program targeting this group directly protects the largest revenue segment.

**3. $6M At-Risk Revenue Needs Urgent Action**
> 1,396 "Cannot Lose" customers averaged $4,303 spend but have not purchased in 105 days. An urgent win-back campaign could recover $6M.

**4. Exceptional 96.72% Repeat Buyer Rate**
> Nearly all customers buy again — focus should shift to increasing basket size and order frequency rather than new customer acquisition.

**5. Revenue Peaks October–November**
> Monthly revenue peaks at $4.83M in November. Campaigns should be planned 6–8 weeks in advance to capture seasonal demand.

---

## 📋 Business Recommendations

| Priority | Action | Expected Impact |
|----------|--------|-----------------|
| 🔴 Immediate | VIP loyalty program for 3,295 Champions | Protect $15.2M revenue |
| 🔴 Immediate | Win-back campaign for Cannot Lose segment | Recover up to $6M |
| 🟡 Short-term | Shift ad spend toward Clothing (54% margin) | Improve profit margin |
| 🟡 Short-term | Nurture 3,523 Potential Loyal customers | Convert to Loyal segment |
| 🟢 Strategic | Audit Home Appliances SKUs (36% margin) | Improve margin to 45%+ |
| 🟢 Strategic | Build Q4 seasonal campaign calendar | Capitalize on peak demand |

---

## 🚀 How to Run This Project

### Prerequisites
```bash
pip install pandas numpy matplotlib openpyxl jupyter
```

### 1 — Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/ecommerce-analytics.git
cd ecommerce-analytics
```

### 2 — Download raw dataset
Download from [Kaggle](https://www.kaggle.com/datasets/imranalishahh/comprehensive-synthetic-e-commerce-dataset) and save as `data/synthetic_ecommerce_data.csv`

### 3 — Run notebooks in order
```bash
jupyter notebook
```
Run in this sequence:
1. `notebooks/Python_data_cleaning.ipynb` — update file path in Cell 2
2. `notebooks/ecommerce_sql_analysis.ipynb`
3. `notebooks/ecommerce_rfm_analysis.ipynb`

### 4 — Open Power BI Dashboard
Open `dashboard/Ecommerce_Analytics_Dashboard.pbix` in Power BI Desktop.
Update source path: **Home → Transform Data → Data Source Settings**

---

## 📄 Resume Bullet Point

```
Built end-to-end e-commerce analytics project analyzing 100,000+ transactions
using Python, SQL, and Power BI. Performed RFM customer segmentation across
19,865 customers identifying 7 actionable segments, and delivered a 4-page
interactive dashboard with insights to improve customer retention and
profitability by $6M+.
```

---

## 👤 Author

**Bheemanathi**
Data Analyst | Python · SQL · Power BI

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/YOUR_PROFILE)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/YOUR_USERNAME)

---

*Portfolio project demonstrating end-to-end data analytics skills for UAE/GCC e-commerce market analysis.*
