# Hospitality-Analysis

````markdown
# 🏨 AtliQ Hospitality Analysis

An end-to-end Data Analysis project performed using Python and Pandas on AtliQ Hotels booking and revenue data. This project focuses on cleaning, transforming, analyzing, and visualizing hotel performance metrics to generate actionable business insights.

---

## 📖 Overview

The hospitality industry generates massive amounts of booking and customer data. This project analyzes AtliQ Hotels' operational data to uncover patterns in occupancy, revenue generation, booking platforms, room categories, and customer ratings.

The project demonstrates practical data analytics skills including:

- Exploratory Data Analysis (EDA)
- Data Cleaning
- Data Transformation
- Business Intelligence
- Data Visualization
- Feature Engineering

---

## 🎯 Business Objectives

This analysis aims to answer key business questions such as:

- Which room categories have the highest occupancy rates?
- Which cities generate the most revenue?
- How does occupancy vary between weekdays and weekends?
- Which booking platforms contribute the most revenue?
- What are the customer rating trends across cities?
- How can hotel management optimize occupancy and profitability?

---

## 📂 Dataset Description

### 1. dim_date.csv
Contains date-related information.

| Column | Description |
|----------|------------|
| date | Calendar Date |
| mmm yy | Month-Year |
| day_type | Weekday / Weekend |

### 2. dim_hotels.csv
Contains hotel property details.

| Column | Description |
|----------|------------|
| property_id | Hotel Identifier |
| property_name | Hotel Name |
| city | Hotel Location |
| category | Hotel Category |

### 3. dim_rooms.csv
Contains room category information.

| Column | Description |
|----------|------------|
| room_id | Room Identifier |
| room_class | Room Type |

### 4. fact_bookings.csv
Contains booking-level transaction data.

### 5. fact_aggregated_bookings.csv
Contains aggregated occupancy and capacity information.

---

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

---

## 📊 Project Workflow

### 1. Data Exploration

- Understanding dataset structure
- Checking data types
- Identifying missing values
- Exploring unique categories
- Examining booking patterns

### 2. Data Cleaning

#### Removing Invalid Guest Records

```python
df_bookings = df_bookings[df_bookings.no_guests > 0]
````

#### Handling Missing Values

Missing values in capacity were replaced using median values.

```python
df_agg_bookings['capacity'].fillna(df_agg_bookings['capacity'].median(), inplace=True)
```

#### Removing Revenue Outliers

Applied the 3-Sigma Rule to identify and remove extreme outliers.

```python
upper_limit = mean + 3 * std
```

#### Removing Invalid Capacity Records

```python
successful_bookings > capacity
```

---

### 3. Feature Engineering

Created a new metric:

#### Occupancy Percentage

```python
occupancy_pct = successful_bookings / capacity * 100
```

This metric was used throughout the analysis.

---

## 📈 Key Analyses Performed

### Occupancy Analysis

* Occupancy by Room Category
* Occupancy by City
* Occupancy by Day Type (Weekday vs Weekend)
* Occupancy Trends for June 2022

### Revenue Analysis

* Revenue by City
* Revenue by Property
* Revenue by Month
* Revenue by Booking Platform

### Customer Analysis

* Average Ratings by City
* Booking Behavior Insights

### Data Integration

* Merged booking, hotel, room, and date datasets
* Appended new August booking data using:

```python
pd.concat()
```

---

## 📊 Visualizations

The project includes visual representations of:

* Occupancy Rates
* Revenue Distribution
* Revenue by Booking Platform
* City-wise Comparisons
* Monthly Revenue Trends

Visualization libraries used:

```python
import matplotlib.pyplot as plt
```

---

## 🔍 Key Insights

* Identified top-performing room categories.
* Compared occupancy rates across cities.
* Analyzed weekend vs weekday demand.
* Measured city-wise revenue contribution.
* Evaluated booking platform effectiveness.
* Assessed customer satisfaction through ratings.

---

## 📁 Project Structure

```text
AtliQ-Hotels-Data-Analysis/
│
├── datasets/
│   ├── dim_date.csv
│   ├── dim_hotels.csv
│   ├── dim_rooms.csv
│   ├── fact_bookings.csv
│   ├── fact_aggregated_bookings.csv
│   └── new_data_august.csv
│
├── Python Analysis.ipynb
├── README.md
└── requirements.txt
```

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/yourusername/AtliQ-Hotels-Data-Analysis.git
```

### Navigate to Project Directory

```bash
cd AtliQ-Hotels-Data-Analysis
```

### Install Dependencies

```bash
pip install pandas numpy matplotlib
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Python Analysis.ipynb
```

and run all cells.

---

## 📚 Skills Demonstrated

* Data Cleaning
* Exploratory Data Analysis (EDA)
* Data Transformation
* Feature Engineering
* Statistical Analysis
* Data Visualization
* Business Analytics
* Problem Solving

---

## 🔮 Future Enhancements

* Interactive Power BI Dashboard
* Revenue Forecasting Models
* Hotel Demand Prediction
* Customer Segmentation
* KPI Dashboard Development
* Machine Learning-Based Insights

---

## 👨‍💻 Author

**Sharia Zaman**

Aspiring Data Analyst | Python | SQL | Power BI

If you found this project helpful, consider giving it a ⭐ on GitHub.

```
```
