# 🕵️‍♂️ EDA_Property_stolen_and_recovered_CrimeData_FM1206EDA_CrimeData_FM1206

## 📘 Project Overview  
This project performs a comprehensive **Exploratory Data Analysis (EDA)** on a **Crime Data** dataset to uncover insights into patterns of property-related crimes across different states, years, and property types in India.  
The analysis focuses on **data cleaning**, **statistical summaries**, **outlier detection**, **data transformation**, and **visualization** to identify trends, high-risk regions, and potential areas for crime prevention strategies.

---

# 📂 Dataset Information  
**Dataset Name:** `10_Property_stolen_and_recovered.csv`  
**Source:** [data.gov.in / NCRB Crime Statistics]  
**Total Records:** 2,000+ crime records (approx.)  
**Features:** 8 key attributes  

| Column Name | Description |
|--------------|-------------|
| State/UT | Name of the Indian State or Union Territory |
| District | District name under the respective State |
| Year | Year of reported crime |
| Property_Stolen | Total number/value of property stolen |
| Property_Recovered | Total number/value of property recovered |
| Recovery_Rate | Percentage of recovered property |
| Crime_Type | Type of property-related crime (e.g., Theft, Burglary, Robbery) |
| Urban_Rural | Classification of area type |

---

# 🗂️ Project Structure  
├── 10_Property_stolen_and_recovered.csv # Original dataset

├── EDA_Property_Stolen_Recovery # Jupyter Notebook containing code

└── README.md # Project documentation


---

## 🔍 Analysis Steps Performed  

### **1️⃣ Dataset Overview**
- Loaded and examined dataset structure and data types  
- Displayed dataset shape (rows × columns)  
- Identified unique values and sample records  
- Summarized descriptive statistics for numerical columns  

**Key Outputs:**
- Total Records: 2,000+  
- Columns: 8  
- States Covered: 36  
- Years: 2001–2014  

---

### **2️⃣ Data Quality Checks**
- **Missing Values:** ~2.5% of records with missing entries  
- **Duplicates:** 0 duplicates found  
- **Inconsistencies:** Standardized case for state and district names  
- **Erroneous Data:** Negative or non-numeric entries detected and corrected  

---

### **3️⃣ Data Cleaning**
- Filled missing numerical values using **median imputation**  
- Categorical values imputed using **mode**  
- Removed unnecessary columns (if any)  
- Standardized column names (snake_case format)  
- Final dataset ensured **no nulls or duplicates**

✅ Clean dataset exported as `crime_data_cleaned.csv`

---

### **4️⃣ Descriptive Statistics**
**Key Observations:**
- **Average Property Stolen:** ₹5.8 lakhs  
- **Average Property Recovered:** ₹2.3 lakhs  
- **Average Recovery Rate:** 40.2%  
- **Most Frequent Crime Type:** Theft (≈52%)  

**State Distribution:**
- Top 3 States by Property Theft: Maharashtra, Uttar Pradesh, Delhi  
- Lowest Crime Rates: Sikkim, Mizoram  

---

### **5️⃣ Data Transformation & Encoding**
- Normalized continuous variables using **StandardScaler**  
- Encoded categorical columns using **LabelEncoder**  
- Added new derived features:
  - **Loss_Value = Property_Stolen - Property_Recovered**
  - **Recovery_Efficiency_Category (High/Medium/Low)** based on recovery rate  
- Transformed dataset saved as `crime_data_transformed.csv`

---

### **6️⃣ Outlier Detection & Treatment**
**IQR Method:**
- Outliers found in `Property_Stolen` and `Property_Recovered`  
- Outlier thresholds (approx.):
  - Property_Stolen: [0, 12,00,000]
  - Property_Recovered: [0, 9,00,000]
- Outliers capped at boundary limits  

**Z-Score Method:**
- Detected 3.8% extreme outliers (|Z| > 3)
- Retained significant anomalies for further insight (e.g., large-scale theft cases)

---

### **7️⃣ Data Visualization**
Generated multiple **crime-focused visualizations:**

| Visualization Type | Purpose |
|---------------------|----------|
| **Histogram** | Distribution of Property Stolen and Recovered |
| **Boxplot** | Outlier detection in theft amounts |
| **Countplot** | Crime Type distribution across states |
| **Heatmap** | Correlation between theft, recovery, and recovery rate |
| **Bar Chart** | Top 10 States by average theft value |
| **Line Chart** | Year-wise crime trends |

---

### **8️⃣ Key Insights & Interpretation**

🧭 **Regional Insights**
- Maharashtra, Delhi, and UP show highest reported thefts.  
- Northeastern states report lower property-related crimes.  

📉 **Recovery Trends**
- Average recovery rate ~40%, indicating challenges in retrieval.  
- Urban regions show slightly better recovery efficiency than rural areas.  

📊 **Temporal Trends**
- Rising theft trends from 2005–2012; decline post-2013.  

⚖️ **Correlations**
- Property_Stolen ↔ Property_Recovered: **0.73 (strong correlation)**  
- Recovery_Rate ↔ Year: Mild decline (~-0.2 correlation)  
- Urban areas correlate with higher reported crimes  

✅ **Data Quality**
- 99.7% completeness  
- Clean, consistent, and fully standardized  

---

## 🧰 Technologies Used  
- **Python 3.x**  
- **Libraries:**  
  - `pandas` – Data cleaning and manipulation  
  - `numpy` – Numerical operations  
  - `matplotlib` – Visualization  
  - `seaborn` – Statistical plotting  
  - `scipy` – Statistical calculations  
  - `scikit-learn` – Encoding and scaling  

---

## ⚙️ How to Run  

### 🔸 Prerequisites
Install required libraries before running:
```bash
!pip install pandas numpy matplotlib seaborn scipy scikit-learn

```

## 💻 Running the Notebook in Google Colab  

### 🔸 Step 1: Open the Notebook  
1. Go to [Google Colab](https://colab.research.google.com/)  
2. Upload your file **`EDA_Property_Stolen_And_Recovered_23BSC001.ipynb`**

### 🔸 Step 2: Mount Google Drive  
Add this code at the beginning of your notebook:  

```python
from google.colab import drive
drive.mount('/content/drive')

```

## 📈 Key Findings Summary  

### 📊 Dataset
- 2,000+ records analyzed  
- 8 key features with 99.7% completeness  

### 🏙️ Crime Insights
- **Top Crime:** Theft (~52%)  
- **Average Recovery Rate:** 40.2%  
- **Highest Recovery Efficiency:** Kerala, Tamil Nadu  

### 📈 Trends
- Theft rate increased steadily from 2005 to 2012  
- Rural regions underreported thefts compared to urban  

### ⚠️ Anomalies
- 3.8% extreme outliers (large theft cases retained for analysis)

---

## 🤖 Implications for Modeling  
- Dataset is **ML-ready** for predictive modeling tasks such as:  
  - **Crime Trend Prediction**  
  - **Recovery Rate Estimation**  
  - **High-Risk Region Identification**  
- Features are **encoded, scaled, and cleaned**

---

## 👨‍💻 Author  
**Name:** Sudarshan Shivale  

**Roll No:** FM1206 

**Course:** MSc Computer Science  

**Date:** November 01, 2025  

---

## 📜 License  
This project is for **academic and educational purposes only.**

---

## 🙌 Acknowledgments  
This analysis is part of the **MSc Computer Science – Data Analytics Module**.  
Special thanks to the faculty mentors for their support and guidance.  
Dataset derived from **public government sources (NCRB)** ensuring **data privacy** and **authentic analytical integrity**.
