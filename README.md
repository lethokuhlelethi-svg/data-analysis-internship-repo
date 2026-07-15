# 📊 AnalystLab Africa — Data Analytics Internship

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?style=flat-square)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?style=flat-square&logo=googlecolab)
![SQL Server](https://img.shields.io/badge/SQL%20Server-SSMS-CC2927?style=flat-square&logo=microsoftsqlserver)
![Duration](https://img.shields.io/badge/Duration-8%20Weeks-green?style=flat-square)

---

## 👤 About

| | |
|---|---|
| **Intern** | Lethokuhle Mathebula |
| **Programme** | AnalystLab Africa Data Analytics Internship |
| **Duration** | 8 Weeks |
| **Tools** | Python, Pandas, NumPy, Matplotlib, Google Colab, SSMS |
| **Year** | 2026 |

---

## 📁 Repository Structure

```
analytlab-africa-internship/
│
├── datasets/
│   ├── online_retail.csv           # UK e-commerce transaction data
│   └── netflix_titles.csv          # Netflix movies and TV shows catalogue
│
├── notebooks/
│   ├── week1_online_retail.ipynb   # Cleaning and EDA — Online Retail
│   └── week2_netflix_titles.ipynb  # Cleaning and EDA — Netflix Titles
│
├── reports/
│   └── Data_Analytics_Summary_Report.docx
│
└── README.md
```

---

## 📦 Datasets

### Dataset 1 — Online Retail

| Attribute | Detail |
|---|---|
| **Rows** | 541,909 |
| **Columns** | 8 |
| **Period** | December 2010 – December 2011 |
| **Description** | Transactional sales data from a UK-based online retailer |

**Columns:** `InvoiceNo` · `StockCode` · `Description` · `Quantity` · `InvoiceDate` · `UnitPrice` · `CustomerID` · `Country`

---

### Dataset 2 — Netflix Titles

| Attribute | Detail |
|---|---|
| **Rows** | 8,807 |
| **Columns** | 12 |
| **Period** | 2008 – 2021 |
| **Description** | Catalogue of movies and TV shows available on Netflix globally |

**Columns:** `show_id` · `type` · `title` · `director` · `cast` · `country` · `date_added` · `release_year` · `rating` · `duration` · `listed_in` · `description`

---

## 🧹 Data Cleaning

### Online Retail Dataset

| Issue | Action Taken | Records Affected | Status |
|---|---|---|---|
| Missing CustomerID | Flagged + filled with "Guest" | 135,080 rows | ✅ Resolved |
| Duplicate rows | Removed with `drop_duplicates()` | Confirmed via `.sum()` | ✅ Resolved |
| Negative quantities (returns) | Separated into returns dataset | Invoices starting with "C" | ✅ Resolved |
| Non-product entries | Removed POSTAGE, DISCOUNT entries | Filtered by StockCode | ✅ Resolved |
| Outliers — Quantity & UnitPrice | Removed using IQR method | 58,501 / 39,450 rows | ✅ Resolved |
| Inconsistent date format | Converted to YYYY-MM-DD | All rows | ✅ Resolved |
| Text & column standardisation | Uppercased, stripped, renamed | All columns | ✅ Resolved |

---

### Netflix Titles Dataset

| Issue | Action Taken | Records Affected | Status |
|---|---|---|---|
| Missing director, cast, country, rating | Filled with "Unknown" | Multiple columns | ✅ Resolved |
| date_added stored as text | Parsed to YYYY-MM-DD format | All rows | ✅ Resolved |
| Inconsistent text casing | Uppercased and stripped | All text columns | ✅ Resolved |
| Column names inconsistent | Lowercased and underscored | All columns | ✅ Resolved |
| Duplicate rows | Removed with `drop_duplicates()` | Confirmed via `.sum()` | ✅ Resolved |

---

## 📊 Exploratory Data Analysis

### Online Retail — Analyses Performed
- Top-selling products by quantity
- Highest revenue-generating countries
- Monthly sales trends
- Most purchased products by order frequency
- Customer purchasing behaviour (registered vs guest)

### Netflix Titles — Analyses Performed
- Movies vs TV Shows distribution
- Content added to Netflix by year
- Top content-producing countries
- Most common age ratings
- Most common genres and categories

---

## 📈 Visualizations

| Chart Type | Online Retail | Netflix Titles |
|---|---|---|
| **Bar Chart** | Total Quantity Sold by Country | Top 10 Countries by Number of Titles |
| **Histogram** | Distribution of Unit Prices | Distribution of Content by Release Year |
| **Pie Chart** | Top 10 Countries by Revenue | Movies vs TV Shows Proportion |
| **Line Chart** | Quantity Sold Over Time (Monthly) | Content Added to Netflix Over Time |
| **Box Plot** | Revenue Distribution | Spread of Release Years |

---

## 🔍 Key Insights

### Online Retail Dataset

> **1. UK market dominance**
> The United Kingdom accounts for over 3.75 million units sold — dwarfing every other country combined. Referenced in: Bar Chart.

> **2. Low-cost, high-volume model**
> Most products are priced under £3. Revenue is driven by quantity sold, not premium pricing. Referenced in: Histogram.

> **3. 24% guest transactions**
> 135,080 CustomerIDs were null — limiting customer-level analysis to 76% of the dataset. Referenced in: Data Cleaning.

> **4. Returns distort geographic data**
> Negative quantity values from cancelled orders pulled multiple countries below zero on the bar chart. Referenced in: Bar Chart.

> **5. Wholesale buying behaviour**
> IQR analysis flagged bulk orders of 24–96 units, indicating a significant wholesale customer segment. Referenced in: Box Plot.

---

### Netflix Titles Dataset

> **6. USA dominates content production**
> The United States produces significantly more Netflix content than any other country. Referenced in: Bar Chart.

> **7. Movies outnumber TV Shows**
> Movies make up the larger share of the catalogue, though TV Shows drive longer per-title engagement. Referenced in: Pie Chart.

> **8. Content peaked in 2019–2020**
> A sharp drop in 2021 aligns with COVID-19 production disruptions worldwide. Referenced in: Line Chart.

> **9. Netflix favours recent content**
> Most titles were released after 2015, confirming the platform prioritises modern productions. Referenced in: Histogram.

> **10. Older classic titles exist as outliers**
> Titles from the 1940s appear in the box plot — retained to serve niche audiences. Referenced in: Box Plot.

---

## 💻 Core Cleaning Patterns

```python
# Lock in raw copy before any cleaning
df_raw = df.copy()

# Flag and fill missing ID columns
df['CustomerID_missing'] = df['CustomerID'].isnull()
df['CustomerID'] = df['CustomerID'].fillna('Guest')

# Standardise column names
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')

# Standardise text columns
df['description'] = df['description'].str.strip().str.upper()

# Standardise date format
df['formatted_date'] = pd.to_datetime(df['date_added']).dt.strftime('%Y-%m-%d')

# Remove duplicates
df = df.drop_duplicates()

# IQR outlier removal
Q1 = df['quantity'].quantile(0.25)
Q3 = df['quantity'].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df['quantity'] < (Q1 - 1.5 * IQR)) | (df['quantity'] > (Q3 + 1.5 * IQR)))]
```

---

## 🛠️ Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, and manipulation |
| `numpy` | Numerical operations and array handling |
| `matplotlib` | All data visualizations and charts |
| `datetime` | Date parsing and format standardisation |

---

## 🚀 How to Run

### Google Colab
1. Open [Google Colab](https://colab.research.google.com)
2. Click **File → Upload Notebook**
3. Select the `.ipynb` file from the `notebooks/` folder
4. Upload the relevant dataset from the `datasets/` folder
5. Click **Runtime → Run All**

### Local Jupyter
```bash
pip install pandas numpy matplotlib
jupyter notebook notebooks/week1_online_retail.ipynb
```

---

## 💡 Key Learnings

- **Never drop ID column nulls blindly** — Missing CustomerIDs represent real guest transactions, not bad data
- **Always lock in a raw copy first** — `df_raw = df.copy()` before any cleaning step prevents unrecoverable data loss
- **Cleaning decisions shape analysis** — Every action taken during cleaning directly affects what the EDA can and cannot reveal
- **Outliers need context, not just removal** — High quantity outliers in retail are wholesale orders, not errors
- **Text standardisation matters** — Without consistent casing, pandas treats "United Kingdom" and "UNITED KINGDOM" as two separate countries
- **Returns must be separated, not deleted** — Negative quantity rows are valid business data representing cancellations

---

## 📝 License

This project was completed as part of the AnalystLab Africa 8-Week Data Analytics Internship Programme.

---

<div align="center">
  <p>Built by <strong>Lethokuhle Mathebula</strong> · AnalystLab Africa · 2026</p>
</div>
