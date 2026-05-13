# Measure Dictionary

This file shows the main DAX measures created for the Power BI report.

The measures are organized in a dedicated `_Measures` table and grouped into display folders.

## 01 Sales

| Measure | Business meaning |
|---|---|
| `Total_revenue` | Total product revenue from order items, excluding freight. |
| `Total_freight` | Total freight value from order items. |
| `Total_orders` | Number of distinct orders in the 2017 dataset. |
| `Active_customers` | Number of distinct customers with orders in 2017. |
| `Active_sellers` | Number of distinct sellers with order items in 2017. |
| `Products_sold` | Number of distinct products sold in 2017. |
| `Total_order_items` | Number of order item rows. |
| `Avg_order_value` | Average revenue per order. |
| `Avg_item_price` | Average product price per order item. |
| `Avg_freight_per_order` | Average freight value per order. |
| `Avg_items_per_order` | Average number of order items per order. |

## 02 Order Status

| Measure | Business meaning |
|---|---|
| `Delivered_orders` | Number of distinct orders with delivered status. |
| `Cancelled_orders` | Number of distinct orders with canceled status. |
| `Other_status_orders` | Orders with statuses other than delivered or canceled. |
| `Delivered_orders_%` | Delivered orders as a percentage of total orders. |
| `Cancelled_orders_%` | Canceled orders as a percentage of total orders. |

## 03 Delivery

| Measure | Business meaning |
|---|---|
| `Avg_delivery_days` | Average number of days between order purchase and customer delivery. |
| `On_time_orders` | Delivered orders where the customer delivery date was on or before the estimated delivery date. |
| `Late_orders` | Delivered orders where the customer delivery date was after the estimated delivery date. |
| `Not_delivered_orders` | Orders without customer delivery date and not classified as delivered with missing delivery date. |
| `On_time_delivery_%` | On-time orders as a percentage of classified delivered orders. |
| `Late_delivery_%` | Late orders as a percentage of classified delivered orders. |
| `Avg_delivery_delay_days` | Average difference between actual delivery date and estimated delivery date. Negative values mean early delivery, positive values mean late delivery. |

## 04 Reviews

| Measure | Business meaning |
|---|---|
| `Total_reviews` | Number of distinct customer reviews. |
| `Avg_review_score` | Average customer review score. |
| `Positive_reviews` | Reviews with score 4 or 5. |
| `Neutral_reviews` | Reviews with score 3. |
| `Negative_reviews` | Reviews with score 1 or 2. |
| `Positive_review_%` | Positive reviews as a percentage of all reviews. |
| `Negative_review_%` | Negative reviews as a percentage of all reviews. |
| `Reviews_with_answer` | Reviews with an answer timestamp/date. |
| `Reviews_without_answer` | Reviews without an answer timestamp/date. |
| `Avg_review_answer_days` | Average number of days between review creation and review answer. |

## 05 Payments

| Measure | Business meaning |
|---|---|
| `Paid_orders` | Number of distinct orders with payment information. |
| `Total_payment_value` | Total payment value from the payments table. |
| `Total_payment_transactions` | Number of payment transaction rows. |
| `Avg_payment_value` | Average payment value per payment transaction. |
| `Avg_installments` | Average number of payment installments. |
| `Card_payment_orders` | Number of distinct orders paid by credit card or debit card. |
| `Boleto_orders` | Number of distinct orders paid by boleto. |
| `Voucher_orders` | Number of distinct orders paid by voucher. |
| `Card_payment_orders_%` | Card payment orders as a percentage of paid orders. |
| `Boleto_orders_%` | Boleto orders as a percentage of paid orders. |
| `Voucher_orders_%` | Voucher orders as a percentage of paid orders. |
| `One_installment_orders` | Number of paid orders with one installment. |
| `Multi_installment_orders` | Number of paid orders with more than one installment. |
| `Multi_installment_orders_%` | Multi-installment orders as a percentage of paid orders. |

## Previous period comparison measures

Several KPI cards include comparison against the previous selected period.

The report uses month and quarter slicers, so the previous period logic works as follows:

- if one month is selected, the comparison is against the previous month;
- if one quarter is selected, the comparison is against the previous quarter;
- if January or Q1 is selected, there is no previous period in the 2017 report scope;
- if no valid comparison exists, the card displays `No comparison`.

Examples of previous period comparison measures include:

| Measure | Business meaning |
|---|---|
| `Total_revenue_previous_period` | Total revenue for the previous selected month or quarter. |
| `Total_revenue_change_%` | Percentage change in revenue compared with the previous period. |
| `Total_revenue_change` | Text label displayed on the KPI card. |
| `Total_orders_previous_period` | Total orders for the previous selected month or quarter. |
| `Total_orders_change_%` | Percentage change in orders compared with the previous period. |
| `Total_orders_change` | Text label displayed on the KPI card. |
| `Active_customers_previous_period` | Active customers for the previous selected month or quarter. |
| `Active_Customers_change_%` | Percentage change in active customers compared with the previous period. |
| `Active_customers_change` | Text label displayed on the KPI card. |
| `Avg_review_score_previous_period` | Average review score for the previous selected month or quarter. |
| `Avg_review_score_change_%` | Percentage change in average review score compared with the previous period. |
| `Avg_review_score_change` | Text label displayed on the KPI card. |
| `On_time_delivery_%_previous_period` | On-time delivery percentage for the previous selected month or quarter. |
| `On_time_delivery_%_change_%` | Percentage change in on-time delivery percentage compared with the previous period. |
| `On_time_delivery_%_change` | Text label displayed on the KPI card. |
| `Avg_order_value_previous_period` | Average order value for the previous selected month or quarter. |
| `Avg_order_value_change` | Text label displayed on the KPI card. |
| `Products_sold_previous_period` | Products sold for the previous selected month or quarter. |
| `Products_sold_change_%` | Percentage change in products sold compared with the previous period. |
| `Products_sold_change` | Text label displayed on the KPI card. |
| `Avg_items_per_order_previous_period` | Average items per order for the previous selected month or quarter. |
| `Avg_items_per_order_change_%` | Percentage change in average items per order compared with the previous period. |
| `Avg_items_per_order_change` | Text label displayed on the KPI card. |
| `Avg_item_price_previous_period` | Average item price for the previous selected month or quarter. |
| `Avg_item_price_change_%` | Percentage change in average item price compared with the previous period. |
| `Avg_item_price_change` | Text label displayed on the KPI card. |
| `Avg_freight_per_order_previous_period` | Average freight per order for the previous selected month or quarter. |
| `Avg_freight_per_order_change_%` | Percentage change in average freight per order compared with the previous period. |
| `Avg_freight_per_order_change` | Text label displayed on the KPI card. |

## Notes

The report focuses on 2017 only. Previous period comparisons are therefore based on months or quarters within 2017, not previous-year comparisons.

The comparison labels are designed for KPI cards and display a text value such as:

`12.5% vs previous period`

or:

`No comparison`