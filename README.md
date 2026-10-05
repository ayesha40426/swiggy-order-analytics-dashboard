# swiggy-order-analytics-dashboard
Interactive Swiggy Order Analytics Dashboard built using Excel to analyze revenue, orders, customer behavior, restaurant performance, delivery time, cancellations, discounts, and payment trends.

## 📌 Project Summary

The **Swiggy Order Analytics Dashboard** is an Excel-based data analytics project that analyzes **8,000 food delivery orders** across customers, restaurants, cities, cuisines, payment methods, and order statuses.

The project follows a complete data analytics workflow including **data cleaning, data preparation, data modeling, calculated fields, KPI analysis, and dashboard visualization**.

The dashboard was designed to monitor key business metrics such as **total revenue, total orders, average order value, delivery performance, cancellation rate, restaurant performance, customer behavior, and payment trends**.

The analysis helps identify revenue trends, top-performing restaurants and cuisines, city-wise performance, customer segments, discount impact, and cancellation patterns.

---

## 🗂️ Dataset & Column Names

The dataset consists of three main tables: **Orders, Customers, and Restaurants**.

### 🧾 Orders Table

**Type:** Fact Table  
**Records:** 8,000

| Column Name | Description |
|---|---|
| `OrderID` | Unique identifier for each order |
| `CustomerID` | Unique identifier of the customer |
| `RestaurantID` | Unique identifier of the restaurant |
| `OrderDate` | Date on which the order was placed |
| `OrderTime` | Time at which the order was placed |
| `DeliveryTimeMin` | Delivery time in minutes |
| `ItemsCount` | Number of items in the order |
| `OrderValue` | Original value of the order |
| `DiscountAmount` | Discount applied to the order |
| `DeliveryFee` | Delivery fee charged |
| `PaymentMethod` | Payment method used for the order |
| `OrderStatus` | Status of the order such as Delivered, Cancelled, or Returned |

---

### 👤 Customers Table

**Type:** Dimension Table  
**Records:** 600

| Column Name | Description |
|---|---|
| `CustomerID` | Unique identifier of the customer |
| `CustomerName` | Name of the customer |
| `Gender` | Gender of the customer |
| `Age` | Age of the customer |
| `City` | Customer's city |
| `SignupDate` | Date the customer registered |

---

### 🍽️ Restaurants Table

**Type:** Dimension Table  
**Records:** 250

| Column Name | Description |
|---|---|
| `RestaurantID` | Unique identifier of the restaurant |
| `RestaurantName` | Name of the restaurant |
| `City` | Restaurant location |
| `Cuisine` | Type of cuisine offered |
| `Rating` | Restaurant rating |
| `CostForTwo` | Approximate cost for two people |
| `FoodType` | Type/category of food |

---

## 🔗 Data Model

The project uses a **star-schema data model**.

```text
                 Customers
                     │
                     │ CustomerID
                     ▼
                  Orders
                     ▲
                     │ RestaurantID
                     │
                Restaurants
```

The `Orders` table acts as the central fact table and is connected to the `Customers` and `Restaurants` dimension tables.

---

## 📊 Key Metrics

The dashboard tracks the following major KPIs:

- **Total Revenue:** ₹73.0L
- **Total Orders:** 8,000
- **Average Order Value:** ₹912
- **Cancellation Rate:** 17.0%
- Average Delivery Time
- Active Restaurants
- Repeat Customers
- Month-over-Month Revenue Growth

---

## 💡 Key Insights

### 💰 Revenue & Orders

- The dashboard recorded **₹73.0L in total revenue** from **8,000 orders**.
- The average order value was approximately **₹912**.
- Monthly revenue analysis shows fluctuations in performance throughout the analyzed period.
- **September 2026 recorded the lowest monthly revenue** in the displayed period, while **August 2026 recorded the highest**. 

### 🍽️ Restaurant Performance

- Restaurant-level revenue analysis helps identify the highest revenue-generating restaurants.
- **Green Corner** had the highest displayed net revenue among the restaurants shown in the dashboard.
- Restaurant performance can be compared using revenue, ratings, and average order value.

### 💳 Payment Methods

- Orders were distributed across multiple payment methods including **UPI, Credit Card, Debit Card, Cash on Delivery, Wallet, and Net Banking**.
- Payment-method analysis helps understand customer payment preferences.

### 🚫 Order Status

- The overall **cancellation rate was 17%**.
- Order status analysis allows comparison of **Delivered, Cancelled, and Returned** orders across different cuisines.
- This can help identify cuisines or categories where operational issues may require further investigation.

### 🏙️ City & Customer Analysis

- City-level analysis can be used to compare order volume and revenue across locations.
- Customer analysis allows segmentation by **age group, gender, and city**.
- These segments can help understand differences in ordering behavior.

### 💸 Discount Analysis

- The dashboard includes **Discount Amount** and **Discount %** to evaluate the relationship between discounts and order value.
- This can help assess whether discount strategies are associated with higher ordering activity.

### ⭐ Restaurant Ratings

- The dashboard compares **restaurant ratings against average order value**.
- This provides a way to explore whether higher-rated restaurants also generate higher-value orders.

---

## 🧹 Data Cleaning Performed

The dataset was prepared by:

- Removing duplicate `OrderID` records
- Correcting data types
- Cleaning customer and restaurant names
- Standardizing city names
- Handling missing delivery-time and rating values
- Removing invalid orders where `OrderValue ≤ 0`
- Combining `OrderDate` and `OrderTime`
- Validating CustomerID and RestaurantID relationships

---

## 🧮 Derived Fields

Additional analytical fields were created, including:

- **Net Revenue**
- **Order Month**
- **Delivery Speed**
- **Discount %**
- **Age Group**
- **Day Type**

These fields allow deeper analysis and filtering within the dashboard.
