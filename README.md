[README (1).md](https://github.com/user-attachments/files/31525002/README.1.md)
# Zomato Restaurant Data Analysis – SQL & Python EDA

## Project Overview

This project analyzes the **Zomato restaurant dataset** to understand restaurant pricing, customer engagement, ratings, online delivery adoption, cuisine preferences, and city-level market patterns.

The project combines **SQL analysis and Python Exploratory Data Analysis (EDA)** to convert restaurant data into meaningful business insights and recommendations.

### Key Skills Demonstrated
- SQL
- Python
- Pandas
- Data cleaning and validation
- Exploratory Data Analysis (EDA)
- Aggregation and filtering
- CTEs and window functions
- KPI analysis
- Restaurant segmentation
- Business insights and recommendations

---

## Business Objective

The project answers practical business questions such as:

- Which restaurants are the most expensive?
- Which restaurants provide strong value for money?
- Which cities have the highest online-delivery adoption?
- Which cities have the largest restaurant presence?
- Which cuisines receive the most customer engagement?
- How do ratings, votes, pricing and delivery availability differ across restaurants and cities?
- Which markets may offer opportunities for online-delivery expansion?

The objective is to demonstrate how **data analysis can support business decision-making**.

---

## Dataset Overview

The dataset contains:

- **9,551 restaurant records**
- **18 columns**
- **15 countries**
- **141 cities**
- **12 currencies**

Important fields include:

| Column | Description |
|---|---|
| `RestaurantID` | Restaurant identifier |
| `RestaurantName` | Restaurant name |
| `CountryCode` | Country code |
| `CountryName` | Country |
| `City` | City |
| `Address` | Restaurant address |
| `Locality` | Restaurant locality |
| `LocalityVerbose` | Detailed locality |
| `Cuisines` | Cuisine type(s) |
| `Currency` | Currency used for cost |
| `Has_Table_booking` | Whether table booking is available |
| `Has_Online_delivery` | Whether online delivery is available |
| `Is_delivering_now` | Current delivery availability |
| `Switch_to_order_menu` | Order-menu availability |
| `Price_range` | Restaurant price category |
| `Votes` | Customer votes |
| `Average_Cost_for_two` | Average dining cost for two |
| `Rating` | Restaurant rating |

---

# Project Structure

```text
Zomato-Data-Analysis/
│
├── Zomato.xlsx
├── Zomato_Market Analysis & Business Question using SQL.ipynb
└── README.md
```

> Update the notebook filenames if your final files use different names.

---

# Part 1 – SQL Case Study

The SQL analysis focuses on practical restaurant and market questions.

### Q1. Most Expensive Restaurants
Identify the top 10 restaurants based on average cost for two people, along with city and price range.

### Q2. Data Quality – Rating and Votes
Identify restaurants with zero ratings, zero votes or missing values in these fields.

### Q3. Indian Restaurants Without Online Delivery
Identify Indian restaurants serving Indian cuisine that do not offer online delivery.

### Q4. High-Performing and Budget-Friendly Restaurants
Identify restaurants satisfying:
- Rating >= 4.5
- Votes > 500
- Average cost for two < 800

### Q5. Online Delivery Adoption by City
Identify cities with at least 10 restaurants and rank them by the percentage of restaurants offering online delivery.

### Q6. Delivery Without Table Booking
Identify the top cities with the highest number of restaurants offering delivery without table booking.

### Q7. Most Popular Cuisine by City
Identify the cuisine with the highest total customer votes in each city and determine the highest-voted city-cuisine combination.

### Q8. City-Level Dining Cost
Identify cities where average dining cost is higher than the overall average and determine the city with the lowest average cost.

---

# Part 2 – Python Exploratory Data Analysis

The Python continuation adds analysis beyond the original SQL questions.

## Data Quality Analysis

The notebook checks:
- Missing values
- Zero ratings
- Zero votes
- Duplicate records
- Low-engagement restaurants
- Potential outliers

### Key Finding
There are **no duplicate rows** in the dataset.

There are also **no missing or zero ratings** based on the current dataset.

However, **1,094 restaurants have zero votes**, indicating no recorded customer voting activity.

The analysis also identifies **2,148 restaurants with Rating <= 1.0 and Votes <= 3**, representing a group with very low recorded ratings and customer engagement.

---

# Key EDA Findings

### 1. India Dominates the Dataset

India represents approximately **90.59% of all restaurant records**.

**Business implication:** Overall dataset-level conclusions are strongly influenced by the Indian restaurant market, so international comparisons should be interpreted carefully.

### 2. Customer Engagement is Highly Skewed

The dataset has approximately:
- Mean votes: **157**
- Median votes: **31**
- Maximum votes: **10,934**

**Business implication:** A relatively small group of restaurants receives much higher customer engagement than most restaurants.

### 3. Zero-Vote Restaurants

**1,094 restaurants have zero votes.**

**Business implication:** These restaurants may require stronger visibility or customer-engagement strategies.

### 4. Low-Engagement Restaurants

**2,148 restaurants have Rating <= 1.0 and Votes <= 3.**

**Business implication:** These restaurants should be treated separately when evaluating performance because the ratings are supported by very limited customer engagement.

### 5. Mixed Currencies Affect Cost Analysis

`Average_Cost_for_two` is reported in different currencies across countries.

**Business implication:** Direct international cost comparisons can be misleading. Cost analysis should be performed within the same currency/country or after converting values to a common currency.

### 6. Average Cost Contains Extreme Values

The large difference between the mean and median `Average_Cost_for_two` indicates significant high-cost observations.

**Business implication:** Median or country-level cost analysis can be more meaningful than the overall average.

### 7. Restaurant Ratings

Ratings range from **1.0 to 4.9**, with a median of approximately **3.2**.

**Business implication:** There is considerable variation in customer perception of restaurant quality.

---

# Advanced Analysis

## Restaurant Segmentation

Restaurants are grouped into project-defined categories such as:

- High Value Performer
- Strong Performer
- Average Performer
- Needs Attention

The segmentation considers:
- Rating
- Votes
- Average cost

> These are analytical categories created for this project and are not official Zomato classifications.

---

# Business Recommendations

### 1. Prioritize High-Opportunity Markets
Cities with strong restaurant supply and customer engagement but comparatively lower online-delivery adoption can be considered potential expansion markets.

### 2. Promote Value-for-Money Restaurants
Restaurants with high ratings, strong engagement and affordable pricing can be highlighted through value-focused recommendations and promotions.

### 3. Personalize Cuisine Discovery
City-level cuisine popularity can be used to improve restaurant discovery and personalized recommendations.

### 4. Differentiate Premium and Value Markets
Higher-cost markets can focus on premium dining experiences and reservations, while value-oriented markets can focus on affordability and delivery.

### 5. Increase Customer Engagement
Restaurants with very low votes may benefit from stronger visibility and customer-engagement initiatives.

### 6. Monitor Online Delivery Adoption
Delivery adoption should be tracked by city and price range to identify markets where digital ordering can be expanded.

### 7. Improve Data Quality Monitoring
Low-engagement records and extreme cost values should be reviewed before calculating business KPIs.

---

# Tools & Technologies

### SQL
`SELECT` `WHERE` `GROUP BY` `HAVING` `ORDER BY` `CASE WHEN` `CTE` `Window Functions` `Aggregate Functions` `Subqueries`

### Python
`Python` `Pandas` `SQLite` `Matplotlib` `Jupyter Notebook`

---

# Analytical Workflow

```text
Raw Dataset
     ↓
Data Understanding
     ↓
Data Quality Checks
     ↓
SQL Analysis
     ↓
Python EDA
     ↓
KPI Analysis
     ↓
Restaurant Segmentation
     ↓
Market Opportunity Analysis
     ↓
Business Insights
     ↓
Business Recommendations
```

---

# Limitations

- The dataset is a snapshot and does not provide historical trends.
- The dataset is heavily concentrated in India.
- `Average_Cost_for_two` uses multiple currencies.
- Votes represent recorded engagement and should not automatically be treated as unique customers or orders.
- Correlation indicates association and does not establish causation.
- The Market Opportunity Score is a project-defined analytical framework.
- Real business decisions would require additional data such as orders, GMV, customer retention, delivery time and restaurant acquisition cost.

---

# Conclusion

This project demonstrates how **SQL and Python can be used together to analyze a restaurant marketplace and translate data into business decisions**.

The analysis progresses from:

**Data Quality → Restaurant Performance → Customer Engagement → Pricing → Delivery Adoption → City Markets → Segmentation → Business Opportunities**

The project is designed to demonstrate not only technical querying and Python skills, but also the ability to **interpret results and communicate business recommendations**.

---

## Author

**Vijay Kumar**

Data Analytics Portfolio Project

`SQL` `Python` `Pandas` `EDA` `Data Analysis` `Business Analytics` `Restaurant Analytics`
