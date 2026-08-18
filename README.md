# Smartphone Battery Health Prediction

A machine learning project that predicts a smartphone's battery health percentage and recommends whether the user should continue using the device, replace the battery, or purchase a new phone based on usage patterns and charging behaviour.

---

## Project Overview

Smartphone batteries naturally degrade over time due to charging habits, temperature, device age, and usage intensity. This project develops both **regression** and **classification** machine learning models to help users understand the condition of their battery and make informed maintenance decisions.

The project consists of two prediction tasks:

- **Regression:** Predict the current battery health percentage.
- **Classification:** Recommend an appropriate action:
  - Keep Using
  - Replace Battery
  - Change Phone

---

## Dataset

The project uses two datasets:

- **Features Dataset**
  - Device age
  - Battery capacity
  - Average screen-on hours
  - Charging cycles
  - Battery temperature
  - Fast charging usage
  - Overnight charging frequency
  - Gaming hours
  - Video streaming hours
  - Background application usage
  - Signal strength
  - Charging habit score
  - Usage intensity score
  - Thermal stress index

- **Target Dataset**
  - Current battery health (%)
  - Recommended action

The datasets are merged using the **Device_ID** field before preprocessing.

---

## Project Workflow

### 1. Data Exploration

Initial exploratory analysis includes:

- Dataset overview
- Missing value detection
- Duplicate checking
- Target distribution
- Feature distributions
- Correlation analysis
- Battery health visualization
- Recommended action analysis

---

### 2. Feature Engineering

Several additional features were created to better represent battery degradation:

| Engineered Feature | Description |
|--------------------|-------------|
| Battery Stress Score | Combined charging frequency, thermal stress and fast charging usage |
| Total Usage Hours | Weekly estimate of total device usage |
| Age Capacity Ratio | Relationship between device age and battery capacity |
| Charging Intensity | Combined charging cycle and overnight charging behaviour |
| Temperature Stress | Combined battery temperature and thermal stress |

---

### 3. Data Preprocessing

The preprocessing pipeline includes:

- Encoding categorical variables
- Feature engineering
- Feature selection
- Train-test split
- Standardisation using `StandardScaler`

A total of **19 features** are used for model training.

---

## Machine Learning Models

### Regression Models

Used to predict battery health percentage.

- Linear Regression
- Random Forest Regressor

Evaluation metrics:

- R² Score
- RMSE
- MAE

---

### Classification Models

Used to recommend battery maintenance actions.

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting
- Support Vector Machine (Linear Kernel)

Evaluation metric:

- Classification Accuracy

Additional evaluation includes:

- Confusion Matrix
- Classification Report
- Feature Importance (tree-based models)

---

## Key Findings

The analysis shows that battery health is strongly influenced by:

- Device age
- Thermal stress
- Charging habits
- Fast charging frequency
- Overnight charging frequency
- Gaming and streaming usage

Heavy usage combined with high operating temperatures accelerates battery degradation.

---

## User Recommendations

Based on the trained models, recommended practices include:

- Limit fast charging whenever possible
- Reduce overnight charging frequency
- Avoid excessive heat during gaming or intensive applications
- Maintain healthy charging habits
- Monitor battery health regularly

General decision guidelines:

| Battery Health | Recommendation |
|---------------|----------------|
| > 75% | Keep Using |
| 45% – 75% | Replace Battery |
| < 45% | Consider Changing Phone |

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## Repository Structure

```
Smartphone-Battery-Health-Prediction/
│
├── Mobile_battery_predictor.ipynb
├── smartphone_battery_features.csv
├── smartphone_battery_targets.csv
└── README.md
```
