# 🛒 E-commerce Sales Analysis

This project analyzes customer and sales data from a Brazilian e-commerce platform to provide actionable insights for a Product Manager. It explores user behavior, order statuses, product performance by day of week, retention patterns, and customer segmentation.

---

## 📚 Table of Contents

- [Goal](#-goal)
- [Objectives](#-objectives)
- [Dataset Description](#-dataset-description)
- [Tools & Technologies](#-tools--technologies)
- [How to Run](#-how-to-run)
- [Key Results](#-key-results)

---

## 🎯 Goal

Conduct a comprehensive analysis of e-commerce sales data and prepare a report tailored for product management needs.

---

## ✅ Objectives

1. Identify the number of users who made only one purchase.
2. Calculate the average number of undelivered orders per month.
3. Determine the most frequent purchase day of the week for each product.
4. Analyze the average number of weekly purchases per user, broken down by month.
5. Perform a cohort analysis to find the cohort with the highest 3rd-month retention from January to December.
6. Create an RFM segmentation of users to assess audience quality.

---

## 🗃️ Dataset Description

All datasets are loaded dynamically from **Google Drive** using public file links.

> Dataset source: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — available on Kaggle.

### 🔹 [`customers_dataset.csv`](https://drive.google.com/file/d/1ZoCOJYbg4AEt6AfC_zruJWDR697I50m2)
- `customer_id` — order-specific user ID  
- `customer_unique_id` — unique user ID (e.g. passport-like)  
- `customer_zip_code_prefix`, `customer_city`, `customer_state` — delivery location data

### 🔹 [`orders_dataset.csv`](https://drive.google.com/file/d/1P8uxPKltLurPY6IM2-7EPE4waQYiNnlE)
- `order_id` — order ID  
- `customer_id` — order-specific user ID  
- `order_status` — order stage (`delivered`, `shipped`, `canceled`, etc.)  
- Timestamps: purchase, approval, delivery estimate and actual delivery

### 🔹 [`order_items_dataset.csv`](https://drive.google.com/file/d/1wiDB3FyZr3HglR7u6U3z1scJI28dRBVf)
- `order_id`, `order_item_id`, `product_id`, `seller_id`  
- `shipping_limit_date` — deadline for shipping  
- `price`, `freight_value` — item price and shipping weight

---

## 🧰 Tools & Technologies

- Python (pandas, numpy, seaborn, matplotlib)
- Jupyter Notebook
- Google Drive public links for data access
- Cohort analysis, RFM segmentation, and groupby-based aggregations

---

## 🚀 How to Run

You can run this notebook either locally or in the cloud:

### ▶️ Option 1: Run in Google Colab (Recommended)
- Click the badge below to open in Colab  
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/v9cheslav/ecommerce_analysis/blob/main/ecommerce_analysis.ipynb)
- No setup is required. All datasets are loaded from public Google Drive links automatically.

### 💻 Option 2: Run Locally
1. Clone this repository  
   `git clone https://github.com/v9cheslav/ecommerce_analysis.git`
2. Open `ecommerce_analysis.ipynb` in Jupyter or VS Code
3. Run all cells — datasets will be fetched dynamically from public Google Drive links

No manual CSV download is required.

---

## 📊 Key Results

### 1. 🛍️ One-time Customers
- Out of 99,441 orders placed by 90,557 unique customers, approximately **91% of users made only one purchase**.
- Repeat purchases account for less than 9% of all orders, indicating a low customer retention rate.
- Possible reasons include: lack of loyalty programs, weak post-purchase communication, or a poor first-time user experience.

### 2. 🚚 Undelivered Orders
- An average of **51.42 orders are canceled each month**, with "Product unavailable" and "Post-payment cancellations" being the most frequent reasons.
- Historical data shows a shift in cancellation causes — what was relevant before 2018 is no longer dominant.
- Notable cancellation spikes occurred in **August 2018** and **February 2018**, pointing to possible systemic or seasonal issues.
- It's recommended to focus on the **most recent year of data** and analyze cancellations by **product category** to inform operational improvements.

### 3. 📅 Product Purchase Weekday Patterns
- A table with the most frequent purchase weekday for each product (`product_id`) was built (32,216 rows).
- Overall order volume significantly drops on weekends, especially on **Saturdays**, while **Mondays and Wednesdays** show peak activity.
- Without a specific business question (e.g. campaign optimization or logistics planning), item-level weekday data has limited actionable value.
- However, the observed trends could be leveraged for **targeted promotions**, **inventory timing**, or **email marketing optimization**.

### 4. 🔄 Average Weekly Purchases per User
- 98.7% of users make **only one purchase per month**, indicating low purchase frequency and episodic buying behavior.
- The average weekly purchase rate ranges narrowly from **0.226 to 0.250** for 98.7% of cases, showing highly stable customer behavior across months.
- These insights suggest opportunities for loyalty program development and provide a solid base for reliable demand forecasting.

### 5. 📈 Cohort Analysis and Third-Month Retention
- The highest third-month retention was observed in the March 2017 cohort at only **0.42%** (12 customers).
- Across all cohorts and periods, retention never exceeded **1%**, which is far below typical e-commerce benchmarks of **16–30%**.
- These results highlight significant customer retention challenges immediately after the first purchase.
- Further analysis requires additional business context (e.g., product types, acquisition channels, post-purchase experience) to accurately diagnose the causes and propose improvements.

### 6. 🧩 RFM Segmentation
- RFM scoring thresholds were defined based on purchase recency (days), frequency (number of orders), and monetary (in Brazilian real, R$).
- Customers were segmented into key groups such as **Champions**, **Big Spenders**, **At Risk**, and **Hibernating** based on their shopping behavior.
- The segmentation provides a foundation for:
  - Targeted marketing campaigns
  - Customer retention and reactivation strategies
  - Hypothesis generation for further customer behavior analysis
- RFM segmentation highlights significant opportunities to improve customer lifetime value and loyalty.

---

## 📎 Author

Made by Slava Simonov as part of portfolio projects in product analytics.