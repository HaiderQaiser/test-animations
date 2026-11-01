## 🏗️ Project Architecture: ETL Data Pipeline

This pipeline extracts raw e-commerce order data, processes it through a Python-based ETL engine using Pandas and NumPy, and loads the cleaned data into a SQL Server database. Finally, an automated visualization engine generates key business metrics using Matplotlib.

```mermaid
graph LR
    A[karachi_ecommerce_orders_dirty.csv] --> B(Pandas/ Numpy ETL Engine)
    B -->|Data Cleaning: Typecasting, Null Handling| C[(SQL Server DB)]
    B -.-> D[rejected_records_logs.csv]
    B -.-> E[karachi_ecommerce_orders_clean.csv]
    C -->|01_create_table.sql & 02_revenue_and_order_metrics.sql| F(Visualization Engine)
    F -->|Matplotlib Rendering| G[category_revenue_summary.png]
    F -->|Matplotlib Rendering| H[order_status_distribution.png]
    F -->|Matplotlib Rendering| I[daily_revenue_trend.png]
