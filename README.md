# 🚗 Uber Data Analysis

Exploratory data analysis of a personal Uber ride history dataset uncovering patterns in **when**, **why**, and **how far** rides were taken over a year, 
using Python.

## 📌 Overview

This project cleans and analyzes a raw Uber ride log (`UberDataset.csv`) to answer questions like:

- Are rides mostly for Business or Personal use?
- What's the most common purpose for booking a ride?
- What time of day / day of week / month sees the most rides?
- How far do rides typically go?
- Which locations are the most frequent pickup and drop-off points?

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** & **NumPy** — data cleaning and manipulation
- **Matplotlib** & **Seaborn** — data visualization
- **Jupyter Notebook**

## 📊 Dataset

The dataset contains 1,156 raw ride records with the following columns:

| Column | Description |
|---|---|
| `START_DATE` | Date & time the ride started |
| `END_DATE` | Date & time the ride ended |
| `CATEGORY` | Business or Personal |
| `START` | Pickup location |
| `STOP` | Drop-off location |
| `MILES` | Distance traveled |
| `PURPOSE` | Reason for the ride (many missing values) |

## 🧹 Data Cleaning & Feature Engineering

- Filled missing `PURPOSE` values with `"NOT"`
- Converted `START_DATE` / `END_DATE` to proper datetime format
- Removed an invalid trailing "Totals" summary row and other incomplete rows
- Engineered new features: `DATE`, `TIME`, `DAY_NIGHT` (Morning/Afternoon/Evening/Night), `MONTH_OF_THE_RIDE`, `DAY_OF_THE_RIDE`

## 📈 Key Insights

- Ride volume is concentrated on **weekdays**, consistent with work-related travel.
- Most rides are **short trips (under 10 miles)**, with a few long-distance outliers.
- A small set of locations account for a disproportionate share of pickups and drop-offs.
- Nearly **44% of rides have no recorded purpose**, limiting deeper "why" analysis.


## 🔮 Future Improvements

- Investigate the high rate of missing `PURPOSE` values
- Replace deprecated `sns.distplot()` with `sns.histplot()`
- Add fare/cost data to connect distance and time patterns to spending
- Build an interactive dashboard (Plotly/Streamlit) on top of the cleaned dataset
