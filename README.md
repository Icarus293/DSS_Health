# 🥗 DSS Health — Dietary Decision Support System

A web application that recommends personalized diet plans using Machine Learning.

## Overview

Users input personal metrics (age, gender, height, weight, activity level) and the system returns a tailored nutrition plan including daily calorie targets, macronutrient breakdown, and a recommended diet type.

## How It Works

1. User submits health information via web form
2. System calculates BMI, BMR, and TDEE using standard nutrition formulas
3. Random Forest model predicts optimal Calories, Protein, Fat, and Carbs
4. DSS logic maps predictions to a diet type (Keto, Vegan, Balanced, Mediterranean, etc.)
5. Results are displayed with food recommendations

## Tech Stack

- **Backend:** Python, Flask
- **ML Model:** Scikit-learn (Random Forest Regressor — R² = 0.93, MAE = 25.69)
- **Data:** [Life Style Dataset](https://www.kaggle.com/datasets/jockeroika/life-style-data/data) — 20,000 records, 54 features
- **Frontend:** HTML, CSS, JavaScript

## Model Performance

| Model | R² Score | MAE |
|---|---|---|
| Linear Regression | 0.24 | 38.81 |
| **Random Forest** ✅ | **0.93** | **25.69** |

## Run Locally

```bash
git clone https://github.com/Icarus293/DSS_Health.git
cd DSS_Health
pip install flask scikit-learn pandas numpy
python train_model.py  # generates nutrition_model.pkl
python app.py          # http://localhost:5000
```

> Dataset must be downloaded separately from [Kaggle](https://www.kaggle.com/datasets/jockeroika/life-style-data/data) and placed in the project root before training.
