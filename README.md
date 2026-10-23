# Tesla Stock Market Performance Analysis

### Exploratory Data Analysis (EDA) & Unsupervised Learning

## 📌 Project Overview

This project explores Tesla's historical stock market data using Python, Exploratory Data Analysis (EDA), feature engineering, time-series analysis, and unsupervised machine learning.

The objective is to identify historical market periods with similar combinations of stock price levels, daily price movements, trading ranges, percentage changes, volatility, and trading volume.

Three clustering algorithms—K-Means, Gaussian Mixture Model (GMM), and DBSCAN—are applied and evaluated to understand different patterns in historical stock market behavior.

## 🎯 Project Objectives

* Understand the structure and characteristics of historical Tesla stock data.
* Perform data quality checks and prepare the dataset for analysis.
* Explore stock price distributions, trends, and trading volume.
* Engineer features to capture daily price movements and volatility.
* Analyze long-term trends, rolling statistics, and seasonal decomposition.
* Apply unsupervised learning to identify historical market segments.
* Compare clustering approaches using Silhouette Scores.
* Validate differences in closing prices across K-Means clusters using ANOVA.

## 📊 Dataset Description

The dataset contains daily Tesla stock market observations from **June 30, 2010, to September 19, 2022**.

| Attribute                     | Details |
| ----------------------------- | ------- |
| Company                       | Tesla   |
| Total observations            | 3,077   |
| Original columns              | 7       |
| Data frequency                | Daily   |
| Missing values in raw dataset | 0       |
| Duplicate rows                | 0       |

### Original Features

* `Date` — Trading date
* `Open` — Opening stock price
* `High` — Highest stock price during the trading day
* `Low` — Lowest stock price during the trading day
* `Close` — Closing stock price
* `Adj Close` — Adjusted closing price
* `Volume` — Number of shares traded

## 🛠️ Tools & Technologies

* **Python** — Data analysis and modeling
* **Pandas** — Data manipulation and preparation
* **NumPy** — Numerical computations
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Scikit-learn** — Feature scaling and clustering
* **Jupyter Notebook** — Analysis environment

## 🔍 Project Workflow

### 1. Data Understanding & Cleaning

* Inspected dataset dimensions, column types, and data quality.
* Converted the date column to datetime format.
* Sorted observations chronologically.
* Checked for missing values, duplicates, and invalid dates.

### 2. Exploratory Data Analysis

* Examined distributions of stock prices and trading volume.
* Analyzed skewness and potential outliers.
* Visualized Tesla's historical closing-price trend.
* Used rolling statistics to explore changes in price variability.
* Applied seasonal decomposition to examine trend, seasonal, and residual components.

### 3. Feature Engineering

Created additional features to represent short-term market behavior:

* **Price Change:** Difference between the current and previous closing prices.
* **Price Range:** Difference between daily high and low prices.
* **Percentage Change:** Relative daily price movement.
* **Volatility:** Rolling standard deviation of percentage changes over 30 days.

The engineered features were prepared for clustering after removing rows with expected missing values.

### 4. Feature Scaling

Applied `StandardScaler` to standardize the selected numerical features before clustering.

Scaling helps prevent variables with larger numerical magnitudes from dominating distance-based clustering methods.

### 5. Unsupervised Learning

Three clustering algorithms were evaluated:

* **K-Means:** Grouped observations into clusters and selected the number of clusters using Silhouette Scores.
* **Gaussian Mixture Model (GMM):** Explored probabilistic clustering using Gaussian mixture components.
* **DBSCAN:** Identified density-based clusters and observations classified as noise.

### 6. Model Evaluation & Statistical Validation

* Compared clustering results using Silhouette Scores.
* Examined cluster characteristics and their interpretations.
* Used one-way ANOVA to test whether mean closing prices differed across K-Means clusters.

## 📈 Key Findings

The project report documents the following results:

| Metric                           |     Result |
| -------------------------------- | ---------: |
| Raw dataset observations         |      3,077 |
| Observations used for clustering |      3,047 |
| Selected K-Means clusters        |          2 |
| K-Means Silhouette Score         |      0.501 |
| GMM Silhouette Score             |      0.465 |
| DBSCAN Silhouette Score          |      0.576 |
| DBSCAN noise observations        | 86 (2.82%) |
| ANOVA F-statistic                | 12,947.665 |
| ANOVA p-value                    |    < 0.001 |

**Interpretation:**

* Tesla's historical closing prices show substantial changes in price levels over the analysis period.
* The price and volume distributions are positively skewed.
* K-Means with two clusters achieved a Silhouette Score of 0.501 on the selected feature set.
* DBSCAN identified 86 observations as noise.
* The ANOVA result provides evidence that mean closing prices differ across the K-Means clusters.

**Evaluation note:** The DBSCAN Silhouette Score was calculated after excluding noise observations, so it is not directly comparable with the other models' scores without considering this difference.

## 📂 Repository Contents

The repository contains the following project materials:

* Python Jupyter Notebook
* Tesla stock analysis report
* Project presentation

Refer to the repository file list for the exact filenames.

## 🚀 How to Run the Project

1. Clone or download this repository.

2. Install Python and Jupyter Notebook.

3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

4. Open Jupyter Notebook.

5. Open the Tesla stock analysis `.ipynb` file.

6. Ensure that the dataset is available at the file path referenced in the notebook.

7. Run the notebook cells in sequence.

**Note:** The dataset file must be available separately if it is not included in this repository.

## ⚠️ Limitations

* This project analyzes historical data and does not predict future stock prices.
* Clustering results depend on feature selection, scaling, and algorithm parameters.
* Historical patterns do not guarantee future market behavior.
* Seasonal decomposition is exploratory and does not establish persistent seasonality.
* The Silhouette Scores of different algorithms should be interpreted in light of their different clustering and noise-handling behavior.

## 👤 Author

**Prince Kumar Singh**

Data Analytics | Python | SQL | Power BI | Excel

## 🔗 GitHub

Explore the notebook, report, and presentation in this repository.

---

*This project demonstrates the application of exploratory data analysis, feature engineering, unsupervised learning, and statistical validation to historical stock market data.*
