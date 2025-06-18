#  Bar Inventory Forecasting & Par Level Recommendation System

## Project Overview

A growing hotel chain is facing **frequent stockouts of popular bar items** and **overstocking of slow-moving inventory**. These inefficiencies are leading to increased operational costs and poor guest experiences.

This project provides a **demand forecasting and inventory recommendation system** that helps managers:
- Predict future weekly consumption using **time series modeling (ARIMA)**
- Determine optimal **par levels** and **safety stock** to avoid under/overstocking
- Gain actionable insights through **visual analytics** and **inventory simulations**

---

##  Business Objectives

- 📈 **Forecast item-level weekly consumption** for each brand at each bar
- 🧯 **Calculate safety stock** based on recent demand volatility
- 📦 **Recommend par levels** to meet peak demand while maintaining buffer
- 📊 Provide **monthly summaries** and **visualizations** to assist in planning
- 💼 Enable hotel managers to make smarter, data-driven purchasing decisions

---

##  Methodology

### 1. Data Preprocessing
- Handled date conversion, missing values
- Resampled consumption data at weekly and monthly levels
- Grouped by each `Bar Name` and `Brand Name` combination

### 2. Time Series Forecasting
- Used **ARIMA (AutoRegressive Integrated Moving Average)** models to forecast next 4 weeks of demand
- Modelled each `(Bar, Brand)` pair individually

### 3. Inventory Recommendation
- Calculated **Safety Stock**:
  \[
  \text{Safety Stock} = Z \times \sigma \quad (Z = 1.65 \text{ for 95% confidence})
  \]
- **Par Level**:
  \[
  \text{Par Level} = \text{Max Forecast} + \text{Safety Stock}
  \]

### 4. Reporting and Visualization
- Weekly Forecast Report
- Monthly Consumption Summary
- Suggested Par Levels
- Visuals for:
  - Top 5 Brands by Consumption
  - Weekly Forecast Trend
  - Safety Stock vs Forecast
  - Monthly Heatmap

---

## 📦 Key Outputs

###  Weekly Forecast (Sample)

| Bar Name        | Brand Name | Forecast Week | Forecast Consumption (ml) |
|----------------|------------|----------------|----------------------------|
| Anderson's Bar | Absolut    | 2024-01-07      | 222.17                     |
| ...            | ...        | ...            | ...                        |

### 📆 Monthly Summary (Sample)

| Bar Name        | Brand Name   | Month   | Total Consumption (ml) |
|----------------|--------------|---------|--------------------------|
| Thomas's Bar   | Yellow Tail  | 2023-11 | 3214.70                  |
| ...            | ...          | ...     | ...                      |

### 📦 Suggested Par Level with Safety Stock

| Bar Name        | Brand Name   | Suggested Par Level (ml) | Safety Stock (ml) | Max Forecast (ml) |
|----------------|--------------|---------------------------|-------------------|-------------------|
| Anderson's Bar | Bacardi      | 2004.96                   | 1246.37           | 758.59            |
| ...            | ...          | ...                       | ...               | ...               |

---

## 📊 Visualizations

- **Top 5 Brands by Monthly Consumption**
- **Weekly Forecast Line Plot**
- **Safety Stock vs Max Forecast Bar Chart**
- **Suggested Par Levels per Bar**
- **Monthly Heatmap of Brand Consumption**

---

## 🧪 How It Works

1. Load and clean inventory data
2. Loop through each `(Bar Name, Brand Name)` pair
3. Forecast 4 weeks of demand using ARIMA
4. Compute safety stock and par levels
5. Aggregate monthly summaries
6. Visualize trends, outliers, and recommendations
7. Display all outputs in an interactive notebook

---

## 🧾 Assumptions

- **Lead time** is assumed to be 1 week
- ARIMA parameters are fixed as `(1,1,1)` for simplicity
- Weekly demand with fewer than 12 data points is ignored
- Only the last 4 weeks are used for demand volatility (σ) estimation
- Outliers and extreme spikes are not explicitly handled

---

## 🛠 Technologies Used

- 🐍 Python 3.10+
- 📊 pandas, numpy, seaborn, matplotlib
- 🔁 statsmodels (ARIMA)
- 🧮 Time series resampling (`resample('W')`, `resample('M')`)

---

## 📁 Files

| File                          | Description                              |
|-------------------------------|------------------------------------------|
| `bar_inventory_forecast.ipynb`| Full forecasting and analysis notebook   |
| `Consumption Dataset.csv`     | Provided historical inventory data       |
| `README.md`                   | Project summary and documentation        |

---

## ✅ Future Enhancements

- Auto ARIMA model selection
- Holiday/event impact modeling
- Dashboard with Streamlit or Dash
- Alert system for predicted stockouts
- Integration with real-time inventory tracking systems

---

## 👤 Author

**Mohammed Harshath SS**  
📧 harshath142@gmail.com  
📍 Coimbatore, India  
🔗 [Portfolio](https://harshath143.github.io/)

---

## 🏁 Conclusion

This system enables smarter forecasting, better stocking, and reduced wastage across bar operations. It’s a powerful step toward **data-driven inventory management** in the hospitality industry.

