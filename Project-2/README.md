<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00f2fe&height=200&section=header&text=Project%2002:%20Customer%20Segmentation&fontSize=40&animation=fadeIn&fontAlignY=38&desc=Oasis%20Infobyte%20Data%20Science%20Internship&descAlignY=60&descAlign=50" alt="Project 2 Banner" />
</div>

<div align="center">
  <img src="https://img.shields.io/badge/Algorithm-K--Means_Clustering-013243?style=for-the-badge&logo=scikit-learn" alt="K-Means" />
  <img src="https://img.shields.io/badge/Analysis-Exploratory_Data_Analysis-D00000?style=for-the-badge" alt="EDA" />
  <img src="https://img.shields.io/badge/Python-Data_Science-F7931E?style=for-the-badge&logo=python" alt="Python" />
</div>

<br/>

## 🎯 Project Objective
The primary goal of this project is to apply unsupervised machine learning algorithms (**K-Means Clustering**) to segment retail customers based on their purchasing behavior, demographics, and income levels. By identifying distinct customer profiles, businesses can develop highly targeted marketing strategies and optimize resource allocation.

---

## 📊 Dataset Overview
The analysis was performed on the `ifood_df.csv` dataset, which contains **2,205 entries** and **39 distinct features** related to customer behavior.

*   **Data Integrity**: `0%` NaN / Null values (Highly pristine dataset).
*   **Average Customer Age**: ~51 Years
*   **Average Customer Income**: Rs. 51,622
*   **Highest Demographics**: Married (854 individuals) & College Graduates (1,113 individuals).
*   **Customer Satisfaction Score**: `99.1%` (Only 0.90% filed complaints).

---

## 🧠 Clustering Methodologies (K-Means)

To extract actionable business intelligence, the data was standardized using `StandardScaler` and clustered across three distinct multi-dimensional relationships:

### 1. Wealth Across the Years (Age vs. Income)
Customers were mathematically segmented into **3 distinct clusters**:
*   🟢 **Highest Income & Slightly Older** (Premium Target Demographic)
*   🔴 **Lowest Income & Youngest** (Budget-conscious Demographic)
*   🔵 **Medium Income & Oldest** (Stable/Retirement Demographic)

### 2. Demographic Clustering (Age vs. Marital Status)
Analyzed the distribution of marital statuses across varying age brackets to identify lifecycle purchasing trends.

### 3. Education & Earning Potential (Education vs. Income)
Determined that customers holding a **Ph.D.** yield the highest average income, directly correlating educational attainment with purchasing power.

---

## 💡 Key Business Insights & Recommendations

Based on the algorithm's output and exploratory data analysis:

1.  **Primary Target Audience**: The typical customer is close to retirement (~51 years old), holds a college degree, is married, and has a highly stable income. Marketing campaigns should heavily target this specific demographic.
2.  **High Customer Retention**: With less than `1%` of customers filing complaints, the current product/service quality is exceptional. The business should focus on upselling existing customers rather than purely focusing on damage control.
3.  **Financial Health**: The total revenue raised across the dataset was **Rs. 1,240,896**, indicating a highly profitable customer base with strong purchasing behavior.

---

## 🛠️ Tools & Libraries Used

*   `pandas` & `numpy`: Data manipulation, aggregation, and statistical calculations.
*   `scikit-learn`: Implementation of `StandardScaler` and the `KMeans` algorithm.
*   `matplotlib` & `seaborn`: High-definition data visualization and cluster plotting.

<br>
<div align="center">
  <i>Part of the Oasis Infobyte Internship Portfolio by Md Huzaifa Ansari</i>
</div>
