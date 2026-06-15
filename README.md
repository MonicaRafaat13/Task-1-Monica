# PJM Hourly Energy Consumption Analysis 
An end-to-end Data Science project focused on analyzing, cleaning, and visualizing hourly energy consumption data from the PJM Interconnection power grid. 

## Project Overview
This project explores the power consumption patterns across various regions and electricity companies within the PJM grid. The goal is to clean the dataset by handling massive missing values, perform Exploratory Data Analysis (EDA), and uncover seasonal and hourly trends in energy demand using data visualization.

---

## Table of Contents
1. [Setup & Libraries](#1-setup--libraries)
2. [Data Collection & Understanding](#2-data-collection--understanding)
3. [Data Cleaning & Preprocessing](#3-data-cleaning--preprocessing)
4. [Exploratory Data Analysis (EDA)](#4-exploratory-data-analysis-eda)
5. [Data Visualization](#5-data-visualization)
6. [Key Insights](#6-key-insights)

---

## 1. Setup & Libraries
The project is built using Python inside a Google Colab environment. The following core data science libraries were used:
* **NumPy:** For numerical operations.
* **Pandas:** For data manipulation, handling time-series, and cleaning.
* **Matplotlib & Seaborn:** For creating statistical and clear data visualizations.

---

## 2. Data Collection & Understanding
* **Dataset:** `pjm_hourly_est.csv` (Hourly energy consumption in Megawatts - MW).
* The dataset was loaded from Google Drive using the `pathlib` library to manage directory paths.
* Initial data understanding was done using `.head()`, `.info()`, and `.describe()` to check shapes, types, and summary statistics.

---

## 3. Data Cleaning & Preprocessing
To ensure data quality, the following steps were taken:
* **Feature Dropping:** Columns with an extremely high percentage of missing values (`COMED`, `DEOK`, `EKPC`, `FE`, `NI`) were dropped to prevent misleading analysis. The total load column (`PJM_Load`) was also excluded to focus strictly on regional/company comparisons.
* **Handling Missing Values:** Missing values for the main regions (`AEP`, `DAYTON`, `DOM`, `DUQ`, `PJME`, `PJMW`) were handled using the **Forward Fill (`ffill`)** method, which is scientifically optimal for time-series data.
* **Time-Series Parsing:** The `Datetime` column was converted to a proper datetime format, set as the dataframe index, and used to extract temporal features: **Hour, Day of Week, Month, and Year**.

---

## 4. Exploratory Data Analysis (EDA)
During the EDA phase, we discovered:
* The average consumption across all sub-regions to identify the highest and lowest consuming companies.
* The correlation between different regions to see if external factors (like weather or seasons) affect them simultaneously.
* The statistical distribution and spread of energy consumption across the power grid.

---

## 5. Data Visualization
We created several plots to communicate the findings effectively:
1. **Bar Plot:** Comparing the mean energy consumption across regions.
2. **Heatmap:** Displaying the correlation matrix between the power companies.
3. **Line Plots:** Shifting through hourly trends (0-23 hours) and seasonal patterns (Jan-Dec) to locate peak consumption hours.
4. **Boxplot:** Visualizing data distribution and spotting potential outliers.

---

## 6. Key Insights
* Energy consumption exhibits a strong **diurnal (hourly) pattern**, peaking during specific hours of the day (e.g., late afternoon/evening).
* A clear **seasonal trend** is visible, where energy demand spikes during summer months (due to air conditioning) and winter months (due to heating).
* There is a high correlation between certain regions, indicating that regional weather patterns heavily influence the entire PJM grid simultaneously.

---

## How to Run the Project
1. Clone this repository or download the `Untitled0.ipynb` file.
2. Upload the notebook to [Google Colab](https://colab.research.google.com/).
3. Ensure your dataset is placed in your Google Drive under the path: `/MyDrive/decodelabs/project1/data/pjm_hourly_est.csv`.
4. Run the cells sequentially!

---
**Developed by:** [Monica Rafaat Adeb/ MonicaRafaat13]
