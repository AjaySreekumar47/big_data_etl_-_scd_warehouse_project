# 🛠️ Big Data ETL & SCD Warehouse Modeling Project

This project demonstrates a complete big data pipeline using **PySpark** for scalable data processing and **SCD (Slowly Changing Dimension)** modeling for dimensional data warehousing. It simulates transactional data, transforms it, and builds enriched fact and dimension tables that mirror real-world enterprise warehouse patterns.

---

## 📁 Project Structure

```

big\_data\_etl\_project/
├── data\_ingestion/
│   ├── customer\_logs.parquet
│   ├── product\_master.csv
│   └── sales\_logs.parquet
├── warehouse/
│   ├── dim\_customer/
│   ├── dim\_product\_scd1/
│   ├── dim\_product\_scd2/
│   └── fact\_sales\_enriched/
├── notebooks/
│   └── etl\_pipeline.ipynb
└── README.md

````

---

## 🚀 Key Features

### ✅ ETL Pipeline
- PySpark-based ingestion of sales, customer, and product data.
- Data cleaning, casting, and enrichment through joins and transformations.
- Output saved as partitioned Parquet files.

### 📦 Dimensional Modeling
- Creation of dimension tables:
  - `dim_customer` (basic)
  - `dim_product_scd1` (SCD Type 1)
  - `dim_product_scd2` (SCD Type 2 with historical tracking)
- `fact_sales_enriched` combines sales with full product metadata.

### 🔍 Analytics
- Sample SQL queries using Spark SQL:
  - Category-level revenue analysis
  - Product performance over time
  - Temporal analysis with SCD logic

---

## 🧪 Technologies Used

- **PySpark** for distributed ETL and modeling
- **Google Colab** for interactive development
- **Google Drive** for intermediate data storage
- **Parquet** format for warehouse-style output

---

## 📊 Sample Analytics Query

```sql
SELECT
  category,
  price_band,
  COUNT(*) AS total_orders,
  SUM(quantity * price) AS total_revenue
FROM fact_sales_enriched
GROUP BY category, price_band
ORDER BY total_revenue DESC
````

---

## 📂 How to Run

1. Open `notebooks/etl_pipeline.ipynb` in Google Colab
2. Mount Google Drive if needed
3. Run each section step-by-step:

   * Environment setup
   * Data ingestion
   * ETL processing
   * Dimension + Fact table creation
   * SCD handling
   * Analytics queries
---

## 🧑‍💻 Author

Ajay Sreekumar
*AI Research Engineer | Data Scientist*
[LinkedIn](https://www.linkedin.com/in/ajay-sreekumar) • [GitHub](https://github.com/AjaySreekumar)
```
