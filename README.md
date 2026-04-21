# 🚖 NYC Taxi Data Cleaning & Exploratory Data Analysis (EDA)

## 📌 Project Overview
This project performs end-to-end data cleaning, validation, and exploratory data analysis on the **NYC TLC Yellow Taxi Trip Dataset (January 2024)** containing approximately **3 million records**.

The goal is to transform raw, messy real-world data into a clean, structured dataset and extract meaningful business insights using Python.

---

## 📊 Dataset Information
- **Source:** NYC Taxi & Limousine Commission (TLC)
- **File:** Yellow Taxi Trip Data (Jan 2024)
- **Size:** ~3 million rows
- **Type:** Real-world transportation dataset
- **Format:** Parquet

---

## 🧹 Data Cleaning Steps

The following preprocessing steps were applied:

### 1. Handling Missing Values
- Imputed `passenger_count` using median
- Filled `RatecodeID` using mode
- Replaced missing `Airport_fee` and `congestion_surcharge` with 0
- Filled `store_and_fwd_flag` using mode

### 2. Data Validation
- Removed trips with negative fare amounts
- Removed invalid trips (e.g., zero distance with non-zero fare)
- Removed invalid passenger counts

### 3. Outlier Treatment
- Applied IQR-based capping for:
  - `fare_amount`
  - `trip_distance`

### 4. Feature Engineering
- Extracted:
  - `trip_duration` (in minutes)
  - `pickup_hour` for time-based analysis

---

## 📈 Exploratory Data Analysis (EDA)

Key analyses performed:

- Distribution of fare amounts and trip distances
- Peak demand hours for taxi usage
- Relationship between fare amount and tip amount
- Trip patterns across time of day
- Data quality and anomaly detection

---

## 🔍 Key Insights

- 🚕 Most taxi rides occur during **rush hours (8–10 AM and 5–7 PM)** indicating commuter-driven demand.
- 💰 Fare distribution is highly skewed with a small number of high-value airport/long-distance trips.
- 💳 Tip amounts show a weak positive correlation with fare values.
- ⚠️ Significant data quality issues were found in missing categorical fields and unrealistic trip records.

---

## 🛠️ Tech Stack

- Python 🐍
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- PyArrow

---

## 📁 Project Structure
nyc-taxi-data-cleaning-eda/
│
├── nyc_taxi_eda.ipynb # Main analysis notebook
├── nyc_taxi_eda.html # Exported report (viewable in browser)
├── README.md # Project documentation