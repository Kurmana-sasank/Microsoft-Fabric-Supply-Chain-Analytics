# Microsoft-Fabric-Supply-Chain-Analytics
# Microsoft Fabric Supply Chain Analytics Solution

## Project Overview

This project demonstrates the design and implementation of an end-to-end Supply Chain Analytics platform using Microsoft Fabric and Power BI. The solution follows the Medallion Architecture (Bronze, Silver, Gold) to ingest, transform, model, and visualize supply chain data for business decision-making.

The objective is to transform raw operational data into meaningful insights related to inventory management, order fulfillment, supplier performance, and delivery efficiency.

---

## Business Problem

Supply chain organizations generate large volumes of data from multiple sources such as orders, customers, products, suppliers, inventory, and delivery systems. Without a centralized analytics platform, it becomes difficult to:

* Monitor operational performance
* Identify delivery delays
* Track inventory levels
* Analyze supplier efficiency
* Generate actionable business insights

This project addresses these challenges using Microsoft Fabric's unified analytics platform.

---

## Solution Architecture

### Microsoft Fabric Components

* Lakehouse
* Data Factory
* Spark Notebooks
* Pipelines
* Semantic Model
* Power BI

### Architecture Flow

Data Sources
→ Bronze Layer (Raw Data)
→ Silver Layer (Cleaned & Transformed Data)
→ Gold Layer (Business-Ready Data Model)
→ Fabric Pipelines
→ Semantic Model
→ Power BI Dashboards

---

## Data Sources

The project utilizes multiple supply chain datasets including:

* Orders
* Customers
* Products
* Suppliers
* Inventory
* Deliveries
* Regions

---

# Medallion Architecture

## Bronze Layer

Purpose: Store raw source data without modification.

### Activities

* Data ingestion
* Raw data storage
* Historical preservation

### Output Tables

* bronze_orders
* bronze_customers
* bronze_products
* bronze_inventory
* bronze_deliveries

---

## Silver Layer

Purpose: Clean and standardize raw data.

### Transformations Performed

* Remove duplicates
* Handle null values
* Standardize formats
* Rename columns
* Data type conversions
* Business rule validation

### Output Tables

* silver_orders
* silver_customers
* silver_products
* silver_inventory
* silver_deliveries

---

## Gold Layer

Purpose: Create business-ready analytical models.

### Fact Tables

#### fact_orders

Contains:

* Order Information
* Revenue
* Quantity
* Customer and Product references

#### fact_inventory

Contains:

* Current stock levels
* Inventory metrics

#### fact_delivery_performance

Contains:

* Delivery dates
* Delivery status
* Delay information
* Performance metrics

### Dimension Tables

#### dim_customer

Customer details and region information.

#### dim_product

Product information and attributes.

#### dim_supplier

Supplier details and performance attributes.

#### dim_date

Date hierarchy supporting:

* Day
* Month
* Quarter
* Year

---

# Data Engineering Process

## Data Ingestion

Source files are loaded into the Fabric Lakehouse.

## Data Transformation

Spark Notebooks perform:

* Data cleansing
* Data validation
* Business transformations

## Data Modeling

Star Schema model created using:

### Fact Tables

* fact_orders
* fact_inventory
* fact_delivery_performance

### Dimension Tables

* dim_customer
* dim_product
* dim_supplier
* dim_date

---

# Pipeline Orchestration

Microsoft Fabric Pipelines automate the ETL process.

Pipeline Execution Flow:

1. Data Ingestion
2. Silver Layer Processing
3. Gold Layer Processing
4. Validation
5. Reporting Layer Refresh

Benefits:

* Automated execution
* Reduced manual effort
* Improved reliability
* Scalable architecture

---

# Power BI Reporting

## Dashboard 1 – Executive Overview

### KPIs

* Total Revenue
* Total Orders
* Total Customers
* Inventory Count

### Visuals

* Revenue by Region
* Monthly Revenue Trend
* Product Category Analysis

---

## Dashboard 2 – Supply Chain Operations

### Analysis Areas

* Inventory Monitoring
* Supplier Performance
* Product Distribution
* Regional Analysis

---

## Dashboard 3 – Delivery Performance

### Analysis Areas

* Delivery Trends
* Delivery Status Distribution
* Regional Delivery Performance
* On-Time Delivery Tracking

---

# DAX Measures

Examples:

### Revenue

```DAX
Total Revenue = SUM(fact_orders[Revenue])
```

### Orders

```DAX
Total Orders = COUNT(fact_orders[Order_ID])
```

### Stock Quantity

```DAX
Total Stock = SUM(fact_inventory[Stock])
```

### Delivery Performance

```DAX
On Time Delivery % =
DIVIDE(
    [On Time Deliveries],
    [Total Deliveries]
)
```

---

# Technologies Used

| Technology       | Purpose                    |
| ---------------- | -------------------------- |
| Microsoft Fabric | Unified Analytics Platform |
| Lakehouse        | Data Storage               |
| Spark Notebooks  | Data Transformation        |
| Data Factory     | Data Ingestion             |
| Fabric Pipelines | Workflow Automation        |
| Power BI         | Reporting & Visualization  |
| DAX              | Business Calculations      |
| SQL              | Data Querying              |

---

# Key Deliverables

* End-to-End Data Pipeline
* Medallion Architecture Implementation
* Automated ETL Process
* Star Schema Data Model
* Power BI Dashboards
* DAX KPI Calculations
* Business Performance Insights

---

# Business Impact

The solution enables:

* Improved supply chain visibility
* Better inventory management
* Faster decision-making
* Delivery performance monitoring
* Supplier performance analysis
* Scalable analytics architecture

---

# Future Enhancements

* Demand Forecasting
* Inventory Optimization
* Supplier Risk Scoring
* Predictive Analytics
* Real-Time Monitoring
* AI-Powered Insights

---

# Project Outcome

Successfully designed and implemented an end-to-end Supply Chain Analytics solution using Microsoft Fabric, leveraging Medallion Architecture, automated pipelines, semantic modeling, and Power BI dashboards to transform raw operational data into actionable business insights.
