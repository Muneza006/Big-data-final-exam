[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Analysis-yellow.svg)](https://powerbi.microsoft.com)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green.svg)](https://pandas.pydata.org)

# WHO Non-Communicable Diseases (NCD) Risk Projection Project 🌍📊

Welcome to the **WHO NCD Risk Projection** project repository! This project leverages **Python** for data cleaning & modeling, and **Power BI** for interactive visualization, to analyze and communicate the global burden of **Non-Communicable Diseases (NCDs)** such as **Diabetes**, **Obesity**, **Tobacco Use**, **Hypertension**, and **Alcohol Consumption** across various countries and years.

---

## 🌿 Sector Focus

**Health Sector** ⚕️
Analyzing global NCD indicators to support preventive health strategies and visualize risk factors per country.

## 🔎 Problem Statement

"Can we predict and visualize countries with higher NCD risk by analyzing Diabetes, Obesity, Tobacco Usage, Hypertension, and Alcohol Consumption indicators?"

---

## 📁 Project Structure

```bash
WHO-NCD-Risk-Projection/
├── data/
│   ├── raw/                      # (Raw Data Files, large files excluded from GitHub)
│   └── processed/
│       └── NCD_Risk_Predictions.csv  # Cleaned dataset
├── notebooks/
│   ├── 01_data_cleaning_and_eda.ipynb  # Data Cleaning & EDA
│   ├── 02_model_training.ipynb         # Clustering Model
│   └── 03_model_evaluation.ipynb       # Evaluation Visuals
├── powerbi_dashboard/
│   └── NCD_Risk_Dashboard.pbix         # Power BI Dashboard File
├── reports/
│   └── WHO_NCD_Risk_Project_Presentation.pptx  # Presentation Slides
├── images/                                # Screenshots for documentation
├── README.md
└── requirements.txt                   # Python libraries used
```

---

## 🗕️ Dataset Attributes

| Column                       | Description                                    |
| ---------------------------- | ---------------------------------------------- |
| Country                      | Name of the country                            |
| Year                         | The year corresponding to the record           |
| Diabetes (%)                 | % of population with diabetes                  |
| Obesity (%)                  | % of population classified as obese            |
| Tobacco Use (%)              | % of population using tobacco                  |
| Hypertension (%)             | % of adults with high blood pressure           |
| Alcohol Consumption (Liters) | Average liters of alcohol consumed per capita  |
| Risk\_Level                  | Binary indicator (0 = Low Risk, 1 = High Risk) |

### 🗽️ Dataset Preview (Python `df.head()`)

> *(Insert Screenshot Here: **`images/df_head.png`**)*

---

## 📖 Data Cleaning & Exploratory Data Analysis (EDA)

Performed using **Pandas**, **Seaborn**, and **Matplotlib**.

### Tasks Performed:

* Handled missing values and standardized formats
* Generated descriptive statistics
* Visualized correlations & distributions

### Visual Outputs:

> 📊 Correlation Heatmap (Insert Screenshot: `images/heatmap.png`)
> 🌍 Diabetes Distribution Plot (Insert Screenshot: `images/diabetes_dist.png`)

### 📃 Sample Code for EDA Preview

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load Dataset
df = pd.read_csv('data/processed/NCD_Risk_Predictions.csv')

# Descriptive Statistics
print(df.describe())

# Correlation Heatmap
plt.figure(figsize=(10,6))
sns.heatmap(df.drop('Country', axis=1).corr(), annot=True, cmap='coolwarm')
plt.title("Correlation Heatmap of NCD Indicators")
plt.show()
```

---

## 🤖 Feature Engineering - Enhanced Columns

Implemented additional analytical features to enhance temporal insights and cluster identification.

### Sample Python Code for Feature Engineering

```python
# Extract temporal features
df['pickup_hour'] = df['Year'] % 24  # Simulating time feature for context
df['month'] = (df['Year'] % 12) + 1

# Season categorization
def get_season(month):
    if month in [12, 1, 2]:
        return 'Winter'
    elif month in [3, 4, 5]:
        return 'Spring'
    elif month in [6, 7, 8]:
        return 'Summer'
    else:
        return 'Fall'

df['season'] = df['month'].apply(get_season)

# Peak/Off-Peak Indicator
df['peak_indicator'] = df['pickup_hour'].apply(lambda x: 'Peak' if x in [7,8,17,18] else 'Off-Peak')

# Time of Booking Bucket
def time_of_booking(hour):
    if hour < 6:
        return 'Late Night'
    elif hour < 12:
        return 'Morning'
    elif hour < 17:
        return 'Afternoon'
    elif hour < 21:
        return 'Evening'
    else:
        return 'Night'

df['Time_of_Booking'] = df['pickup_hour'].apply(time_of_booking)

# Save Enhanced Dataset
df.to_csv('data/processed/NCD_Risk_Predictions_Enhanced.csv', index=False)
```

---

## 🤖 Clustering Model - KMeans

Applied **KMeans Clustering** to categorize countries into NCD risk clusters based on:

* Diabetes (%)
* Obesity (%)
* Hypertension (%)

### Visual Outputs:

> 🔸 KMeans Scatter Plot (Obesity vs Diabetes)
> *(Insert Screenshot: **`images/kmeans_scatter.png`**)*

### Python Code Sample

```python
from sklearn.cluster import KMeans

features = df[['Diabetes (%)', 'Obesity (%)', 'Hypertension (%)']]
kmeans = KMeans(n_clusters=3, random_state=42)
df['Cluster'] = kmeans.fit_predict(features)

# Plot Clusters
plt.scatter(df['Obesity (%)'], df['Diabetes (%)'], c=df['Cluster'], cmap='viridis')
plt.xlabel('Obesity (%)')
plt.ylabel('Diabetes (%)')
plt.title('KMeans Clustering - NCD Risk Segmentation')
plt.show()
```

---

## 📊 Model Evaluation

* Evaluated using **Silhouette Score** for clustering quality.
* Visualized cluster distribution.

### Outputs:

> 🔹 Cluster Distribution Pie Chart
> 📊 Pairplot for Cluster Insights
> *(Insert Screenshots: **`images/cluster_pie.png`**, **`images/pairplot.png`**)*

### Sample Python Code

```python
from sklearn.metrics import silhouette_score

score = silhouette_score(features, df['Cluster'])
print(f'Silhouette Score: {score}')
```

---

## 💻 Power BI Dashboard

Designed an interactive dashboard featuring:

* **Line Chart**: NCD trends over years
* **Bar Chart**: Country comparison for Tobacco Use
* **Pie Chart**: Risk Level distribution
* **Map Visualization**: Global Diabetes prevalence

### DAX Snippet Example

```dax
Time_of_Booking = 
SWITCH(
    TRUE(),
    HOUR([pickup_datetime]) < 6, "Late Night",
    HOUR([pickup_datetime]) < 12, "Morning", 
    HOUR([pickup_datetime]) < 17, "Afternoon",
    HOUR([pickup_datetime]) < 21, "Evening",
    "Night"
)
```

### Screenshot:

> 👁️ *(Insert Full Power BI Dashboard Screenshot: **`images/powerbi_dashboard.png`**)*

---

## 🛠️ Installation & Requirements

```bash
pip install -r requirements.txt
```

### Key Libraries:

* pandas
* seaborn
* matplotlib
* scikit-learn

---

## 👊 Innovation Highlights

* Engineered **Risk\_Level** indicator using combined thresholds.
* Applied KMeans clustering to group countries based on multiple NCD factors.
* Designed a multi-layered **Power BI Dashboard** for insightful storytelling.

---

## 🌟 Project Credits

* **Student**: \[Your Name]
* **Course**: INSY 8413 | Introduction to Big Data Analytics
* **Instructor**: Eric Maniraguha

---

## 🔗 Repository Guidelines

* Screenshots are placed in `/images/` folder.
* Notebooks are organized sequentially under `/notebooks/`.
* Power BI dashboard in `/powerbi_dashboard/`.
* Data files in `/data/processed/`.

---

## 🌟 License

MIT License - Free to use for educational purposes.

---

📢 **Remember:** Always maintain Academic Integrity. Make sure you understand every line of code and every visual you create!

---

# 🎉 Thank You & Happy Analyzing! 🎉
