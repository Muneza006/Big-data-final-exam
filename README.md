🌟 Project Credits

Student: Muneza Pascal

ID: 26630

Course: INSY 8413 | Introduction to Big Data Analytics

FINAL- EXAM CAPSTONE PROJECT

Instructor: Eric Maniraguha




**WHO Non-Communicable Diseases (NCD) Risk Projection Project 🌍📊**


 Welcome to the WHO NCD Risk Projection project repository! This project leverages Python for data cleaning & modeling, and Power BI for interactive visualization, to analyze and communicate the global burden of 
 Non-Communicable Diseases (NCDs) such as Diabetes, Obesity, Tobacco Use, Hypertension, and Alcohol Consumption across various countries and years.


 🌿 Sector Focus

Health Sector ⚕️
Analyzing global NCD indicators to support preventive health strategies and visualize risk factors per country.



🔎 Problem Statement

Can we predict and visualize countries with higher NCD risk by analyzing Diabetes, Obesity, Tobacco Usage, Hypertension, and Alcohol Consumption indicators?

📁 Project Structure

WHO-NCD-Risk-Projection/
├── data/
│   ├── raw/                     
│   └── processed/
│       └── NCD_Risk_Predictions.csv  
├── notebooks/# Data Cleaning & EDA
│   ├── 02_model_training.ipynb        
│   └── 03_model_evaluation.ipynb       
├── powerbi_dashboard/
│   └── NCD_Risk_Dashboard.pbix         
├── reports/
│   └── WHO_NCD_Risk_Project_Presentation.pptx  
├── images/                               
├── README.md
└── requirements.txt    

📅 Dataset Attributes

This dataset integrates multiple health risk indicators that contribute to Non-Communicable Diseases (NCDs) across various countries and years

**Country**: The name of the country where the health data was recorded. Each row represents a data point for a specific country.

**Year**:	The calendar year corresponding to the record. This allows tracking health trends over time for each country.

**Diabetes (%)**:	Represents the percentage of the country's population diagnosed with diabetes. A key indicator in assessing metabolic health risks.

**Obesity (%)**:	The percentage of the population classified as obese, based on BMI ≥ 30. Obesity is a major contributor to NCD prevalence globally.

**Tobacco Use (%)**: 	Indicates the proportion of individuals who actively use tobacco products (smoking, chewing, etc.), which is a significant NCD risk factor.

**Hypertension (%)**:	The percentage of adults suffering from high blood pressure (Systolic BP ≥ 140 mmHg or Diastolic BP ≥ 90 mmHg). It reflects cardiovascular health risks.

**Alcohol Consumption (Liters)**:	Average liters of pure alcohol consumed per adult (15+ years old) in a year. High alcohol consumption correlates with liver diseases and other NCDs.

**Risk_Level**:	A binary indicator derived through rule-based thresholds: 1 = High NCD Risk, 0 = Low NCD Risk. This column classifies the overall risk profile.

🗾️ Dataset Preview (Python df.head())




![Dataset Preview](https://github.com/user-attachments/assets/bdb0e769-b3bf-4c14-8661-d55db557640c)

📖 Data Cleaning & Exploratory Data Analysis (EDA)

Performed using Pandas, Seaborn, and Matplotlib.

Tasks Performed:

Handled missing values and standardized formats

Generated descriptive statistics

Visualized correlations & distributions





🤖 Clustering Model - KMeans

Applied KMeans Clustering to categorize countries into NCD risk clusters based on:

. Diabetes (%)

. Obesity (%)

. Hypertension (%)

 ![Kmeans Obesity vs Diabetes](https://github.com/user-attachments/assets/17d975ad-0b2e-4e87-86a3-98e3bf2bd1b0)


📊 Model Evaluation

. Evaluated using Silhouette Score for clustering quality.

. Visualized cluster distribution.

 ![Cluster Distribution](https://github.com/user-attachments/assets/67cf68cc-ac97-4511-9739-c340c3b6b2dd)



💻 Power BI Dashboard

Designed an interactive dashboard featuring:

Line Chart: NCD trends over years 

Bar Chart: Country comparison for Tobacco Use

Pie Chart: Risk Level distribution

Map Visualization: Global Diabetes prevalence

![NCD_Risk_Dashboard pbix](https://github.com/user-attachments/assets/17141788-a099-47c8-a53b-5b72e10259ed)

🛠️ Installation & Requirements

Key Libraries:

**pandas**: For data cleaning, transformation, and manipulation (DataFrames)

**numpy**:	Numerical operations, handling arrays efficiently

**seaborn**: Statistical data visualization (heatmaps, distributions)

**matplotlib**: General-purpose plotting (line charts, bar plots, scatter plots)

**scikit-learn**: For KMeans clustering and model evaluation (silhouette score)

System Requirements

Python: Version	Python 3.9+ recommended

**IDE/Tool**:	Jupyter Notebook / VS Code

**Power BI	Desktop**: version for dashboard design

