<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00f2fe&height=200&section=header&text=Project%2001:%20Data%20Cleaning%20Pipeline&fontSize=40&animation=fadeIn&fontAlignY=38&desc=Oasis%20Infobyte%20Data%20Science%20Internship&descAlignY=60&descAlign=50" alt="Project 1 Banner" />
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Process-Data_Cleaning_&_Wrangling-013243?style=for-the-badge&logo=pandas" alt="Data Cleaning" />
  <img src="https://img.shields.io/badge/Mathematics-Outlier_Mitigation-D00000?style=for-the-badge" alt="Outliers" />
  <img src="https://img.shields.io/badge/Python-Data_Science-F7931E?style=for-the-badge&logo=python" alt="Python" />
</div>

<br/>

## 🎯 Project Objective
Real-world data is inherently dirty. The objective of this project is to build a robust, end-to-end **Data Cleaning and Preprocessing Engine** for the `AB_NYC_2019.csv` Airbnb dataset (48,895 records). The goal is to mathematically treat missing values, fix structural anomalies, and algorithmically suppress extreme outliers without destroying the integrity of the original dataset.

---

## 🧹 The Preprocessing Pipeline

To ensure the dataset is ready for predictive modeling, the following structural transformations were executed:

### 1. Missing Value Imputation
*   **Categorical Features:** Handled missing string values (`name`, `host_name`) via strategic "Unknown" tagging to prevent data loss.
*   **Continuous Features:** Imputed missing numerical data (`reviews_per_month`) using the arithmetic **Mean**.
*   **Temporal Features:** Treated missing date/time data (`last_review`) using a combination of **Forward Fill (`ffill`)** and **Backward Fill (`bfill`)** for chronological consistency.

### 2. Structural & Data Type Formatting
*   Converted all string attributes to `lower_case` and stripped trailing whitespace to prevent duplicate categories caused by typographical errors.
*   Engineered a Regular Expression (`Regex`) pipeline to strip currency symbols (`$`) and commas (`,`) from financial columns, casting them to computationally viable `float` datatypes.

### 3. Validity Constraints
*   Programmatically dropped geo-spatial anomalies (e.g., coordinates falling outside the mathematical `-90/90` latitude and `-180/180` longitude boundaries).
*   Enforced boolean logic filters to drop impossible physics (e.g., negative prices, or `availability_365` exceeding 365 days).

---

## 🧮 Mathematical Outlier Mitigation

Prior to cleaning, the dataset suffered from extreme statistical skewness (e.g., the `price` attribute had a massive positive skew of **19.11**). 

Instead of aggressively dropping outlier rows (which causes devastating data loss), I implemented an **Interquartile Range (IQR) Clipping Algorithm**:

1.  Calculated `Q1` (25th percentile) and `Q3` (75th percentile).
2.  Determined the absolute mathematical boundaries (`Lower Bound = Q1 - 1.5 * IQR` and `Upper Bound = Q3 + 1.5 * IQR`).
3.  Utilized `pandas.clip()` to cap extreme outliers exactly at the boundary limits.

### 📉 The Impact of Outlier Capping
| Attribute | Initial Skewness | Final Skewness | Result |
| :--- | :--- | :--- | :--- |
| **Price** | `19.11` | `1.02` | **94.6% Reduction in Skewness** |
| **Minimum Nights** | `21.82` | `1.28` | **94.1% Reduction in Skewness** |
| **Host Listings** | `7.93` | `1.15` | **85.4% Reduction in Skewness** |

*Visual proof (Density Plots & Correlation Heatmaps before/after transformation) are documented inside the Jupyter Notebook.*

---

## 🛠️ Tools & Libraries Used
*   **Data Manipulation**: `pandas`, `numpy` (Core dataframe transformations).
*   **Statistical Mathematics**: `scipy.stats.skew`, `statistics`, `math` (IQR formulation).
*   **Visualization**: `seaborn`, `matplotlib` (Density plotting & Heatmaps).

<br>
<div align="center">
  <i>Part of the Oasis Infobyte Internship Portfolio by Md Huzaifa Ansari</i>
</div>
