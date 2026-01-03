🏠 House Price Prediction — Regression Model Exploration
📌 Project Overview

This project explores regression-based machine learning approaches for predicting house prices using the King County housing dataset.
The focus is not on achieving the highest possible R², but on understanding model behavior, bias–variance tradeoff, and the effect of feature engineering and regularization on generalization.

Multiple regression models were implemented, compared, and diagnosed using principled ML techniques.

📂 Dataset

Source: kc_house_data.csv
Observations: 21,613 houses
Target variable: price
Initial features: 21 (numerical + date)

Preprocessing decisions

Dropped identifiers and location-based leakage-prone features:
id, zipcode, lat, long
Removed weak or redundant indicators:
waterfront, view
Converted date to datetime and excluded from modeling
Retained structural house attributes (size, condition, age, etc.)

⚙️ Modeling Pipeline

All models were built using scikit-learn Pipelines to ensure reproducibility and prevent data leakage.
Common steps across pipelines:
StandardScaler for feature normalization
Polynomial feature expansion (degree = 2) where applicable
Regularization (Ridge, Lasso, ElasticNet)
PowerTransformer and PCA in advanced pipelines to address variance instability and multicollinearity

🧠 Models Explored

The following models were evaluated:
Linear Regression (baseline)
Linear Regression + Ridge
Linear Regression + Lasso
Linear Regression + ElasticNet
Polynomial Regression (degree = 2) + Linear Regression
Polynomial Regression + ElasticNet
Polynomial Regression + PCA + Linear Regression
Hyperparameters (e.g., regularization strength) were explored using controlled loops to observe their effect on training and test performance.

📊 Evaluation Strategy

Models were evaluated using:

R²
MAE
RMSE

Evaluation was performed using:

Train–test split (80/20)

5-fold cross-validation for robustness

Cross-validation results (final pipeline):
Mean CV R² ≈ 0.69
Standard deviation ≈ 0.013
This indicates stable generalization across folds.

🔍 Diagnostics & Observations
Bias–Variance Behavior

Linear models plateaued at ~62% training R², indicating bias limitation
Polynomial features improved training fit but increased variance
Regularization reduced overfitting but had limited impact on bias
PCA reduced redundancy introduced by polynomial expansion and improved stability

Residual Analysis

Residuals are centered around zero with no strong curvature
Variance increases with predicted price (heteroscedasticity), which is typical for housing data
No major systematic structure remains unmodeled
These diagnostics suggest the models are reasonably specified, though uncertainty naturally increases for high-priced houses.

📌 Key Takeaways

Increasing model complexity improves fit but must be controlled to avoid variance inflation
Polynomial features are useful but introduce multicollinearity
PCA can help stabilize expanded feature spaces when used judiciously
Model comparison should prioritize generalization stability, not single-split performance
No single model is claimed to be “the best”; results are context-dependent and reflect tradeoffs between bias, variance, and interpretability.

🛠️ Tech Stack

Python
NumPy, Pandas
Matplotlib, Seaborn
scikit-learn

⚠️ Notes & Limitations

Results depend on the chosen feature set and preprocessing decisions
Housing prices exhibit heteroscedasticity, limiting achievable accuracy
Further improvements could include:
Target transformation (e.g., log-price)
Tree-based or ensemble models
Spatial feature engineering

📌 Conclusion

This project demonstrates a structured machine learning workflow:
Baseline modeling
Incremental complexity
Regularization and dimensionality reduction
Cross-validation and diagnostic analysis

The emphasis is on model reasoning and evaluation, not on declaring a universally optimal model.
