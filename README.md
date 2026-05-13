# Olist E-commerce Power BI Dashboard

This is a Power BI portfolio project based on the public Brazilian E-Commerce Public Dataset by Olist.

The report analyzes e-commerce performance for the full calendar year 2017, focusing on revenue, orders, customers, product categories, delivery performance, payment methods, and sales trends.

## Project purpose

The goal of this project was to create business-focused Power BI dashboard that shows skills in:

- working with multiple related tables,
- building a fact/dimension data model (star schema),
- preparing and cleaning data in Power Query,
- creating DAX measures,
- designing interactive dashboard pages,
- using slicers for quarter and month analysis,
- presenting KPIs in a clear visual format.

## Dataset

Dataset source: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

The original dataset contains Brazilian e-commerce marketplace data from 2016 to 2018, including orders, customers, products, sellers, payments, delivery information, and customer reviews.

Because 2016 and 2018 contain partial-year data, this report focuses only on orders purchased in 2017.

## Report scope

The Power BI report includes only 2017 data.

The model was filtered so that the report includes:

- orders purchased in 2017,
- order items connected to 2017 orders,
- payments connected to 2017 orders,
- reviews connected to 2017 orders,
- customers connected to 2017 orders,
- products sold in 2017,
- sellers active in 2017.

Monetary values are displayed in USD.

## Report pages

The report contains two pages:

### 1. Executive Overview

This page provides a high-level overview of 2017 e-commerce performance.

It includes:

- total revenue,
- total orders,
- active customers,
- average review score,
- on-time delivery percentage,
- average order value,
- revenue by month,
- revenue by quarter,
- orders by status,
- orders by payment type,
- top product categories by revenue,
- top customer states by revenue.

### 2. Sales Analysis

This page provides a more detailed view of sales and operational performance.

It includes:

- total revenue,
- total orders,
- products sold,
- average items per order,
- average item price,
- average freight per order,
- active customers by month,
- revenue by payment type,
- orders by delivery status,
- top customers by revenue.

## Data model

The model uses a fact/dimension structure (star schema).

Main fact tables:

- `Fact_Orders`
- `Fact_OrderItems`
- `Fact_Payments`
- `Fact_Reviews`

Main dimension tables:

- `Dim_Date`
- `Dim_Customers`
- `Dim_Products`
- `Dim_Sellers`

A dedicated `_Measures` table is used to organize DAX measures.

## Data preparation

Main Power Query steps included:

- setting correct data types,
- creating date-only columns from timestamp fields,
- creating delivery duration and delivery delay fields,
- creating delivery status categories,
- cleaning text fields,
- replacing technical errors where appropriate,
- adding basic data quality flags,
- filtering the model to 2017 orders only,
- keeping only related records from order items, payments, reviews, customers, products, and sellers.

## Data quality checks

Basic quality checks were performed during data preparation.

The following relationship checks returned no unmatched rows:

- order items without matching orders,
- payments without matching orders,
- reviews without matching orders,
- order items without matching products,
- order items without matching sellers,
- orders without matching customers.

Delivered orders with missing customer delivery dates were not removed. They were handled as a separate delivery status category:

`Delivered - missing delivery date`

## Key DAX measures

Examples of measures created for the report:

- `Total_revenue`
- `Total_orders`
- `Active_customers`
- `Products_sold`
- `Avg_order_value`
- `Avg_item_price`
- `Avg_freight_per_order`
- `Delivered_orders_%`
- `Cancelled_orders_%`
- `On_time_delivery_%`
- `Late_delivery_%`
- `Avg_review_score`
- `Total_payment_value`

## How to view the report

1. Download the `.pbix` file from this repository.
2. Open it in Power BI Desktop.
3. Use the Overview and Sales pages to explore the dashboard.
4. Use the quarter and month slicers to filter the 2017 data.

The `.pbix` file contains imported data, so the report can be viewed and interacted with directly after opening it in Power BI Desktop.

Refreshing the data may require downloading the original Olist dataset from Kaggle and updating the local file paths in Power Query.

## Tools used

- Power BI Desktop
- Power Query
- DAX
- GitHub
