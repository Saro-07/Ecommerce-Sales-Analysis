# 📐 DAX Measures Reference Guide

This document contains all the Data Analysis Expressions (DAX) measures developed for the **Olist E-Commerce Intelligence Dashboard**.

---

### 1. Core Financial & Volume Measures

#### Total Revenue
Calculates total gross sales from delivered orders.
```dax
Total Revenue = SUM('olist_cleaned_for_dashboard'[price])


### Total Orders
Calculates unique delivered orders.
```dax
Total Orders = DISTINCTCOUNT('olist_cleaned_for_dashboard'[order_id])


### Average Order Value (AOV)
Calculates the average revenue generated per order.
```dax
Avg Order Value = DIVIDE([Total Revenue], [Total Orders], 0)


### 2. Logistics & Delivery Performance Measures

### Late Delivery Rate
Calculates the percentage of orders delivered past the estimated delivery date.
```dax
Late Delivery Rate = 
DIVIDE(
    CALCULATE(
        COUNTROWS('olist_cleaned_for_dashboard'),
        'olist_cleaned_for_dashboard'[late_delivery] = TRUE
    ),


### On-Time Delivery Rate
Calculates the percentage of on-time deliveries.
```dax
On Time Delivery Rate = 1 - [Late Delivery Rate]


### Average Delivery Days
Calculates the average duration from purchase to customer delivery.
```dax
Avg Delivery Days = AVERAGE('olist_cleaned_for_dashboard'[delivery_days])


### 3. Customer Satisfaction & Review Ratings

### Average Review Score
Calculates overall customer satisfaction score (1 to 5 stars).
```dax
Avg Review Score = AVERAGE('olist_cleaned_for_dashboard'[review_score])


### On-Time Average Rating
Measures the average rating for orders delivered on or before the estimated date.
```dax
On Time Avg Rating = 
CALCULATE(
    AVERAGE('olist_cleaned_for_dashboard'[review_score]),
    'olist_cleaned_for_dashboard'[late_delivery] = FALSE
)


### Late Delivery Average Rating
Measures the average rating for orders delivered late.
```dax
Late Delivery Avg Rating = 
CALCULATE(
    AVERAGE('olist_cleaned_for_dashboard'[review_score]),
    'olist_cleaned_for_dashboard'[late_delivery] = TRUE
)


### 4. Calculated Columns

### Delivery Status
Categorizes orders into human-readable fulfillment statuses.
```dax
Delivery_Status = 
IF(
    'olist_cleaned_for_dashboard'[late_delivery] = TRUE, 
    "Late Delivery", 
    "On-Time"
)


### Cleaned Product Category
Removes underscores from Portuguese-translated category names for clean visual presentation.
```dax
Category_Clean = 
SUBSTITUTE(
    'olist_cleaned_for_dashboard'[product_category_name_english], 
    "_", 
    " "
)



    COUNTROWS('olist_cleaned_for_dashboard'),
    0
)
