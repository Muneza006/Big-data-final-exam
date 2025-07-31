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


<img width="733" height="486" alt="image" src="https://github.com/user-attachments/assets/8667c8ee-4609-4564-9560-e61a77b15006" />

![Dataset Preview](https://github.com/user-attachments/assets/703bbc36-0824-4d8e-a0e0-ab89e223059e)


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

pandas

seaborn

matplotlib

scikit-learn

👊 Innovation Highlights

. Engineered Risk_Level indicator using combined thresholds.

. Applied KMeans clustering to group countries based on multiple NCD factors.

. Designed a multi-layered Power BI Dashboard for insightful storytelling.
