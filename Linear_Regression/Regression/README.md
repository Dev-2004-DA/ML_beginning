🏠 House Price Prediction – Regression Model Comparison
📌 Project Overview

This project focuses on predicting house prices using the King County housing dataset.
Multiple regression models were implemented, evaluated, and compared to understand:
The impact of regularization
The effect of polynomial features
Whether dimensionality reduction (PCA) improves generalization

How model complexity affects bias–variance tradeoff
The goal was not to blindly maximize R², but to diagnose model behavior using proper ML principles.

📂 Dataset
Source: kc_house_data.csv
Observations: 21,613 houses
Target variable: price
Initial features: 21 columns (numerical + date)

Feature preprocessing decisions:
Dropped non-informative / leakage-prone features:
id
zipcod
lat, long
Removed weak or redundant categorical indicators:
waterfront, view
Converted date to datetime and excluded from modeling
Final feature set focused on structural house attributes

⚙️ Preprocessing Pipeline
All models were built using scikit-learn Pipelines to prevent data leakage.
Common preprocessing steps:
StandardScaler for feature normalization
Polynomial feature expansion (degree = 2) where applicable
PowerTransformer for variance stabilization (in advanced pipeline)
PCA to reduce multicollinearity and dimensionality

🧠 Models Implemented
The following regression models were trained and evaluated:
1. Linear Regression (Baseline)
2. Linear Regression + Ridge
3. Linear Regression + Lasso
4. Linear Regression + ElasticNet
5. Polynomial Regression (degree = 2) + Linear Regression
6. Polynomial Regression + ElasticNet
7. Polynomial Regression + PCA + Linear Regression

Additional- used for loop to check best hyperparameter for  respective model's accuracy

Each model was evaluated on:
Training R²
Test R²
MAE
RMSE

📊 Model Performance Summary
  Model	                Train R²	  Test R²
Linear Regression	        62.41	    59.99
LR + Ridge	              62.41	    59.99
LR + Lasso	              62.41	    60.05
LR + ElasticNet	          62.28	    60.52
Polynomial + LR	          72.82	    63.63
Polynomial + ElasticNet	  69.81	    64.91
Polynomial + PCA + LR	    70.41	    65.61

✅ Final Model Selection

Best-performing model (based on test performance and generalization):
🏆 Polynomial + PCA + Linear Regression
Reasons:
Highest test R² (65.61%)
Lower RMSE compared to other models
Reduced overfitting compared to raw polynomial regression

PCA helped mitigate multicollinearity introduced by polynomial features

🔍 Key Observations & Learnings
1. Linear models plateau early
Training R² ≈ 62% across all linear variants
Indicates bias limitation, not overfitting

3. Polynomial features improve fit
Significant jump in training R²
But raw polynomial regression shows overfitting

3. Regularization + PCA improves generalization
ElasticNet reduces overfitting
PCA stabilizes polynomial expansion
Best bias–variance balance achieved here

⚠️ Important Caveat (Read This)

Model comparison is based on a single train–test split.
This means:
Results are indicative, not definitive
True performance should be validated using:
K-Fold Cross-Validation
Learning curves
Residual diagnostics (already partially explored)

Next logical step:
Replace single split evaluation with cross-validated metrics.

🛠️ Tech Stack

Python 3
NumPy
Pandas
Seaborn & Matplotlib
scikit-learn

📌 Conclusion (Honest)

This project demonstrates correct modeling workflow:
Baseline first
Incremental complexity
Regularization before brute force
