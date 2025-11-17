# 📊 Google Play Store Apps — Data Cleaning & Exploratory Data Analysis (EDA)

This project focuses on cleaning and analyzing the **Google Play Store apps dataset** to understand patterns in app categories, installs, ratings, pricing, and user behavior.

All analysis and code are available in the notebook:  
👉 **`playstore-analysis.ipynb`**

---

# 🧹 1. Data Cleaning (What Was Done)

The raw dataset contained missing values, inconsistencies, special characters, and incorrect data types. Below is the exact cleaning process followed:

### 🔹 Initial Inspection
- Reviewed dataset structure using `head()`, `info()` and missing value summary.
- Identified that many numeric features were incorrectly stored as **object/string types**.

### 🔹 Handling Missing Values
- Missing values detected in: Rating, Type, Android Version, Current Version.
- These were documented and preserved or cleaned depending on analysis needs.

### 🔹 Cleaning Individual Columns
#### ✔ **Reviews**
- Found non-numeric values (e.g., `"3.0M"`).
- Removed invalid row and converted Reviews to integer.

#### ✔ **Size**
- Values like `"8.0M"`, `"19k"`, and `"Varies with device"`.
- Replaced `"Varies with device"` with `NaN`.
- Standardized sizes to numeric MB/KB format.

#### ✔ **Installs**
- Contained symbols like `"+"` and commas (`"1,000+"`).
- Removed special characters and converted to integer.

#### ✔ **Price**
- Contained `$` symbol.
- Cleaned and converted to float.

#### ✔ **Last Updated**
- Converted to proper datetime.
- Extracted **Day**, **Month**, and **Year** from the date.

### 🔹 Removing Duplicates
- Found **1,181 duplicate app names**.
- Removed all duplicate entries, keeping only the first occurrence.

### 🔹 Final Feature Classification
- **Numerical Columns:** Rating, Reviews, Size, Installs, Price, Day, Month, Year  
- **Categorical Columns:** Category, Type, Content Rating, Genres  

---

# 🔍 2. Exploratory Data Analysis (EDA)

The goal of the EDA was to understand:

- App category distribution  
- How ratings are distributed  
- Whether higher installs relate to higher ratings  
- Free vs Paid app characteristics  
- Correlation between numeric features  

The visuals below summarize the EDA process.

---

# 📸 3. Visualizations

### 1️⃣ Dataset Overview
![Dataset Overview](images/1-data-overview.png)

---

### 2️⃣ Missing Values Heatmap
![Missing Heatmap](images/2-missing-heatmap.png)

---

### 3️⃣ Category Distribution
![Category Distribution](images/3-category-count.png)
**Insight:** Family, Games, and Tools categories dominate the Play Store.

---

### 4️⃣ Ratings Distribution
![Ratings Distribution](images/4-ratings-distribution.png)
**Insight:** Most apps have ratings between **4.0–4.5**, showing a left-skewed distribution.

---

### 5️⃣ Installs vs Rating
![Installs vs Rating](images/5-installs-vs-rating.png)
**Insight:** Apps with higher installs tend to have better ratings.

---

### 6️⃣ Correlation Heatmap
![Correlation Heatmap](images/6-correlation-heatmap.png)
**Insight:** Installs and Reviews show strong correlation; Price has minimal correlation with Rating.

---

# 🧠 4. Key Insights (Summary)

- **Family is the largest category (~18%)**, followed by Games (~11%).  
- **Free apps dominate the store (>90%).**  
- **Apps with high installs generally have higher ratings.**  
- **Paid apps tend to have slightly higher median ratings than free apps.**  
- **Size does not strongly influence rating.**  
- **Reviews and Installs are strongly correlated.**

---

# ▶️ How to View the Project

1. Download or clone the repository  
2. Open the file:  
   **`playstore-analysis.ipynb`**  
3. Run it in Jupyter Notebook / Jupyter Lab / VS Code

All code, analysis, and visualizations are available inside the notebook.

---

# 📦 Dataset Source
Public dataset used for this project:  
https://raw.githubusercontent.com/krishnaik06/playstore-Dataset/main/googleplaystore.csv

---
