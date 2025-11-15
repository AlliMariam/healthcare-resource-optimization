# healthcare-resource-optimization
Predictive analytics for NHS A&E demand forecasting and resource optimization using Python
# NHS A&E Healthcare Analytics & Demand Forecasting

Predictive analytics system for NHS hospital resource optimization using 10 years of real A&E data.

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Latest-green.svg)
![Scikit-learn](https://img.shields.io/badge/ScikitLearn-Latest-orange.svg)

## 📊 Project Overview

This project analyzes **10 years of NHS England A&E data** (June 2015 - September 2025) to forecast demand and optimize resource allocation. Built as part of my MSc Data Science studies, it demonstrates practical application of predictive modeling to healthcare operations.

**Key Achievement:** Built a predictive model with **85% accuracy** forecasting emergency admissions 6 months ahead, identifying that **winter admissions are 20-25% higher** than summer baseline.

## 🎯 Business Problem

NHS hospitals face capacity challenges, particularly during winter months. This project aims to:
- Predict future A&E demand to enable proactive capacity planning
- Quantify seasonal patterns (winter pressure)
- Identify performance against the NHS 4-hour target
- Provide actionable insights for resource allocation

## 📈 Key Findings

- **Winter Pressure Quantified:** Winter months (Dec-Feb) show 20-25% higher admissions vs summer
- **Predictable Patterns:** Previous month's admissions and seasonal indicators are strongest predictors
- **Breach Rate Analysis:** National average breach rate of 20-25% (target: <5%)
- **Forecast Accuracy:** Model achieves MAE of ~8,000 admissions (5% error rate)

## 🛠️ Technologies Used

- **Python 3.9+**: Core analysis and modeling
  - `pandas`, `numpy`: Data manipulation
  - `scikit-learn`: Machine learning (Random Forest)
  - `matplotlib`, `seaborn`: Visualization
- **Jupyter Notebook**: Interactive development
- **Git**: Version control

## 📂 Project Structure
```
├── notebooks/
│   ├── 01_data_loading.ipynb          # Data import and initial exploration
│   ├── 02_data_cleaning.ipynb         # Data preprocessing
│   ├── 03_exploratory_analysis.ipynb  # EDA and insights
│   ├── 04_feature_engineering.ipynb   # Creating predictive features
│   └── 05_modeling.ipynb              # Model training and evaluation
├── data/
│   ├── nhs_ae_data_clean.csv         # Processed NHS data
│   └── README.md                      # Data source documentation
├── visualizations/
│   └── nhs_ae_overview.png           # Key charts
├── README.md                          # This file
└── requirements.txt                   # Python dependencies
```

## 🚀 How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Run Analysis
```bash
# Clone repository
git clone https://github.com/YOUR_USERNAME/nhs-healthcare-analytics.git
cd nhs-healthcare-analytics

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

Then open and run notebooks in order (01 → 05).

## 📊 Data Source

**Dataset:** NHS England Monthly A&E Attendances and Emergency Admissions  
**Source:** [NHS England Statistical Work Areas](https://www.england.nhs.uk/statistics/statistical-work-areas/ae-waiting-times-and-activity/)  
**Period:** June 2015 - September 2025 (120+ months)  
**Coverage:** National-level aggregated data

### Key Variables
- Total A&E Attendances
- Emergency Admissions  
- Patients waiting >4 hours (breaches)
- Patients waiting >12 hours (trolley waits)

🔍 Methodology

1. Data Preprocessing
- Filtered to June 2015 onwards (when actual monthly data began)
- Handled missing values and outliers
- Created breach rate and admission rate percentages

2. Feature Engineering
- **Lag features:** Previous 1 and 3 months' admissions
- **Rolling averages:** 3-month and 6-month moving averages
- **Trend indicators:** Difference between short and long-term averages
- **Seasonal features:** Month, quarter, season, winter pressure flag

3. Model Development
- **Algorithm:** Random Forest Regressor
- **Train/Test Split:** 80/20 chronological (time series)
- **Validation:** MAE, RMSE, R² metrics
- **Feature Selection:** Based on feature importance analysis

4. Model Performance
- **R² Score:** 0.85 (85% variance explained)
- **MAE:** ~8,000 admissions (5% of mean)
- **RMSE:** ~10,000 admissions
- **Top Features:** Previous month admissions, 3-month average, seasonal indicators

