# 📊 Customer Profitability & Churn Analysis (SQL + Python + Power BI)

## 📌 Project Overview
This project aims to identify **key drivers of low profitability** and understand how **customer behavior impacts customer lifetime value (CLV) and churn risk**.

The analysis focuses on evaluating whether factors such as **discount usage, purchase behavior, and customer engagement** are associated with low profit contribution.

---

## ❗ Business Question
**What factors are associated with low profitability?**  
(e.g., high discount usage, low spending behavior, or customer structure)

---

## 🧠 Hypothesis
- Customers with **high discount sensitivity** contribute lower profitability
- Low profitability may be driven by **low spending per transaction (basket size)**
- Customer behavior (frequency, recency) impacts **CLV and churn risk**

---

## 🗂️ Data & Approach

### Data Preparation
- Joined customer profile and behavioral data into an **Analytical Base Table (ABT)**
- Filtered invalid records (e.g., missing `avg_spend`, invalid dates)

### Data Quality Checks (Python - Pandas)
- Ensured `customer_id` uniqueness
- Validated no negative values in:
  - `recency_days`, `frequency`, `monetary`, `avg_spend`
- Checked logical consistency:
  - `last_order_date ≥ first_order_date`
- Handled data issues:
  - Removed ~2.55% null `avg_spend`
  - Excluded records with invalid or missing dates

---

## 🔍 Analytical Approach

- Performed **customer segmentation** based on:
  - Discount sensitivity
  - Average spend
  - Frequency / Recency / Tenure
- Created derived features such as:
  - CLV proxy
  - Frequency segments
  - Behavioral segments (promo vs non-promo)
- Analyzed relationships between:
  - Discount behavior vs CLV
  - Spend vs CLV
  - Frequency vs profitability
  - Recency vs churn risk

---

## 🔑 Key Insights

### 1. Discount is NOT the main driver of low profitability
- Customers with high CLV are often **low discount-sensitive**
- Discount usage alone does not significantly increase customer value

---

### 2. Basket size (avg_spend) is the key driver
- Higher **average spend → significantly higher CLV**
- Low-profit customers tend to **spend less per transaction**, not necessarily overuse discounts

---

### 3. Frequency supports value, but is not the root cause
- High-frequency customers tend to have higher spend
- However, low-profit customers already purchase at similar frequency  
→ The issue is **low spend per order**

---

### 4. Low Activity segment is the main profitability risk
- Contributes the **lowest CLV**
- High likelihood of churn with weak repeat behavior

---

### 5. Power Users have high value but are under-leveraged
- High CLV per customer
- But not enough contribution at total level  
→ Opportunity to scale impact

---

### 6. Recency is the strongest predictor of churn

- **Churn risk spikes after 90 days inactivity (38–42%)**
- 61–90 days is a **critical early warning window**
- Risk begins before customers reach 90+ days

---

## 🚀 Recommendations

### 1. Increase Basket Size (Core Strategy)
- Use promotions that encourage **higher spend per order**
  - e.g., spend threshold, bundle deals, step-up offers
- Focus on value perception, not just discounts

---

### 2. Reduce Over-reliance on Discounts
- Avoid blanket discount strategies
- Target discounts only where they improve **margin or behavior**

---

### 3. Activate Low Activity Customers
- Design campaigns to **increase purchase frequency and engagement**
- Improve onboarding and early customer experience

---

### 4. Scale Power Users
- Increase frequency and spend through:
  - Exclusive campaigns
  - Early access / loyalty benefits

---

### 5. Implement Churn Prevention System
- Set **early warning trigger at 60–75 days**
- Launch targeted retention campaigns before 90 days
  - Personalized reminders
  - Incentive-based reactivation

---

## 🛠️ Tools Used
- SQL (Data Extraction & Transformation)
- Python (Pandas for Data Cleaning & Analysis)
- Power BI (Visualization & Dashboard)

---

## 📌 Conclusion
Low profitability is **not primarily driven by discount usage**,  
but by **customer spending behavior and engagement structure**.

Improving **basket size, customer activity, and early retention**  
will have a significantly higher impact on long-term profitability than increasing discounts.
