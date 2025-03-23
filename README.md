 Dataset Overview
Source: UCI Energy Efficiency Dataset (ID: 242)

Size: 768 instances, 8 features, 2 target variables (Heating Load Y₁, Cooling Load Y₂).

Features: Includes Relative Compactness (X₁), Surface Area (X₂), Overall Height (X₅), etc.

Data Characteristics: Multivariate, no missing values, mix of continuous & integer features.

🎯 Objective
To predict building heating and cooling loads using architectural features, enhancing energy efficiency modeling.

🔍 Exploratory Data Analysis (EDA)
Feature Scales:

Some features (e.g., X₂: 500-800) have larger ranges than others (X₁: 0-1), requiring normalization.

Correlation Analysis:

Certain features were highly correlated (e.g., X₂ & X₃ due to area overlap), affecting model stability.

Visualization Insights:

Observed trends indicating a possible polynomial relationship between features & target variables.

⚙️ Data Preprocessing
✅ Normalization

Applied MinMaxScaler to bring features to a comparable range, improving gradient descent stability.

✅ Skewness Check

No significant skewness detected in independent features, so no transformation was needed.

✅ Feature Selection (Correlation Handling)

Recursive Feature Elimination (RFE) and Ridge/Lasso Regression were applied to reduce multicollinearity, but they did not improve model performance over the base model.

🔢 Polynomial Relationship
Pearson & Spearman Correlation, along with Residual Analysis, suggested a non-linear relationship.

Solution: Applied a degree-2 polynomial transformation → Significant improvement in performance compared to the base model.

📊 Model Evaluation & Overfitting Check
✅ Metrics Used

R² Score: Measures overall fit.

Adjusted R²: Accounts for feature count to detect overfitting.

✅ Findings

After polynomial transformation, the model showed a significant jump in R², validating the choice of a polynomial approach.
