<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00f2fe&height=200&section=header&text=Project%2004:%20Predictive%20House%20Pricing&fontSize=40&animation=fadeIn&fontAlignY=38&desc=Oasis%20Infobyte%20Data%20Science%20Internship&descAlignY=60&descAlign=50" alt="Project 4 Banner" />
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Algorithm-Linear_Regression-013243?style=for-the-badge&logo=scikit-learn" alt="Regression" />
  <img src="https://img.shields.io/badge/Mathematics-Statistical_Diagnostics-D00000?style=for-the-badge" alt="Stats" />
  <img src="https://img.shields.io/badge/Python-Data_Science-F7931E?style=for-the-badge&logo=python" alt="Python" />
</div>

<br/>

## 🎯 Project Objective
The objective of this project is to architect a supervised Machine Learning model capable of forecasting real-estate prices based on 13 distinct property attributes (e.g., area, bedrooms, geographic factors, and furnishing status). 

Beyond just model fitting, this project focuses heavily on **Advanced Statistical Diagnostics**, analyzing regression residuals, testing for heteroscedasticity, and utilizing mathematical transformations to optimize predictive accuracy.

---

## ⚙️ Feature Engineering & Encoding
The `Housing.csv` dataset contained a mix of continuous and categorical text variables. To make the data computationally viable for linear regression, I engineered a preprocessing pipeline:
*   **One-Hot Encoding (`pd.get_dummies`)**: Transformed all binary categorical strings (e.g., `mainroad`, `guestroom`, `airconditioning`) and nominal strings (`furnishingstatus`) into deterministic `0` and `1` integer matrices.
*   The final mathematical matrix contained **13 independent features** plotted against the `price` target variable.

---

## 🧮 Mathematical Modeling (Linear Regression)
Utilized `scikit-learn` to fit a multiple linear regression hyperplane across an 80/20 train-test split. 

**Core Hyperplane Coefficients Calculated:**
*   **Base Intercept**: `260,032.36`
*   **Bathrooms**: `+ 1,094,444.79` *(Highest positive impact on price)*
*   **Air Conditioning**: `+ 791,426.74`
*   **Unfurnished**: `- 413,645.06` *(Highest negative impact on price)*

**Baseline Model Performance:**
*   **R-Squared ($R^2$)**: `0.65` (Model successfully explains 65% of the variance in housing prices).
*   **Root Mean Squared Error (RMSE)**: `1,324,506.96`

---

## 🔬 Advanced Statistical Diagnostics

To ensure the mathematical validity of the regression model, I performed a deep diagnostic analysis on the model's residuals and variance.

### 1. Heteroscedasticity & Log Transformation
*   **The Problem**: Initial scatter plots of `Actual vs. Predicted` prices revealed a classic funnel shape—error variance increased at higher price points (Heteroscedasticity). High-priced homes were consistently being under-predicted.
*   **The Mathematical Solution**: Applied a **Logarithmic Transformation** (`np.log1p`) to both the actual and predicted targets. 
*   **The Result**: The log transformation mathematically compressed the extreme values, forcing the residuals into a highly homoscedastic (uniform) distribution and significantly tightening the regression confidence interval.

### 2. Residual Density & IQR Outlier Detection
*   Calculated the **Interquartile Range (IQR)** of the regression residuals to establish absolute mathematical boundaries for predictive failure.
*   Generated a Residual Density Plot overlaid with the `lower_bound` and `upper_bound` IQR markers. The plot confirmed that the residuals followed a near-perfect normal distribution, satisfying a critical assumption of Ordinary Least Squares (OLS) regression.

### 3. Feature Correlation Mapping
*   Engineered a high-definition Pearson Correlation Heatmap. 
*   Confirmed that continuous features like `area` shared a near 1.0 positive correlation with `price`, while categorical features like `furnishingstatus_unfurnished` provided necessary negative correlation weights to balance the model.

---

## 🛠️ Tools & Libraries Used
*   **Machine Learning**: `scikit-learn` (`LinearRegression`, `train_test_split`, `mean_squared_error`, `r2_score`).
*   **Statistical Math**: `scipy.stats.skew`, `numpy.log1p`, `math.sqrt`.
*   **Data Manipulation**: `pandas`, `numpy`.
*   **Diagnostics Visualization**: `matplotlib`, `seaborn` (Regplots, Boxplots, Heatmaps).

<br>
<div align="center">
  <i>Part of the Oasis Infobyte Internship Portfolio by Md Huzaifa Ansari</i>
</div>
