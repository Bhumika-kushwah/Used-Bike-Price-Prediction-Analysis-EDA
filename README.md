# 🏍️ Used Bike Price Prediction Analysis – EDA

## 🔍 Project Overview
This project focuses on performing Exploratory Data Analysis (EDA) on used bike resale data to identify the major factors affecting bike selling prices.

The analysis explores how brand, manufacturing year, ownership, KM driven, and showroom price influence resale value in the Indian used bike market.

---

## 📁 Dataset Information
- Source: Kaggle – BIKE_DETAILS.csv  
- Total Raw Records: 1,061 bike listings  
- Records After Cleaning: 1,055 listings  
- Features: 7 Columns  

### Dataset Columns
- name  
- selling_price  
- year  
- seller_type  
- owner  
- km_driven  
- ex_showroom_price  

### Engineered Features
- brand  
- age  
- depreciation  
- depreciation_per_year  
- km_driven_new  

- Dataset Type: Mixed (Numerical + Categorical)  
- Nature: Real-world used vehicle resale dataset  

---

## 🧹 Data Cleaning & Feature Engineering

### 🗑️ Duplicate Removal
Removed:
```python
6 duplicate rows
```

using:
```python
df.drop_duplicates()
```

### 🏷️ Brand Extraction
Created a new column:
```python
brand = name.split()[0]
```

for brand-wise analysis.

### 📦 Outlier Treatment (KM Driven)
Applied IQR-based outlier handling:
```python
Q1 = 13,500
Q3 = 43,000
IQR = 29,500
```

Outliers above:
```python
87,250 km
```

were capped using:
```python
np.where()
```

### 📉 Depreciation Features
Created:
```python
depreciation = ex_showroom_price - selling_price
```

and:
```python
depreciation_per_year
```

### 🗓️ Age Feature
Created:
```python
age = 2026 - year
```

for depreciation and resale analysis.

### 🔗 Correlation Matrix
Built correlation heatmap using:
```python
df.select_dtypes(include='number').corr()
```

---

## 📊 Exploratory Data Analysis

### 🔹 Univariate Analysis
- Selling price distribution  
- Brand frequency analysis  
- Ownership distribution  

### 🔹 Bivariate Analysis
- KM Driven vs Price  
- Brand vs Price  
- Year vs Selling Price  

### 🔹 Multivariate Analysis
- Correlation heatmap  
- Depreciation analysis  
- Ownership + KM + Brand impact on price  

---

## 📌 Key Insights

### 💰 Selling Price Distribution
- Average Price:
```python
₹59,714
```

- Median Price:
```python
₹45,000
```

- Maximum Price:
```python
₹7.6L
```

➡️ Dataset was heavily right-skewed.

### 🏷️ Brand Impact
Average resale prices:
- Harley-Davidson → ₹5.4L  
- Royal Enfield → ₹1.29L  
- Bajaj → ₹43K  

➡️ Brand strongly influences resale value.

### 📉 KM Driven vs Price
Correlation:
```python
r = -0.212
```

→ Higher KM driven reduces resale value.

### 📅 Manufacturing Year Impact
- 2020 bikes averaged ₹1.83L  
- 2010 bikes averaged ₹32K  

➡️ Newer bikes retain much higher resale value.

### 🔗 Strongest Predictor
```python
ex_showroom_price → r = 0.919
```

This was the strongest predictor of selling price.

### 👤 Ownership Analysis
- 87% bikes were 1st-owner vehicles  
- Individual sellers dominated the dataset (99.4%)  

---

## 💡 Key Learnings

- Outlier treatment is essential for skewed datasets  
- Feature engineering improves business understanding  
- High-null columns should not always be dropped blindly  
- Correlation analysis helps identify strong predictors  
- EDA reveals hidden pricing patterns in resale markets  

---

## 🛠️ Tools & Technologies Used
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Plotly  
- Scikit-learn  


Examples:
- Selling Price Distribution  
- Brand-wise Price Comparison  
- KM Driven Outlier Analysis  
- Correlation Heatmap  
- Year vs Price Trends  

---

## 🚀 How to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/bike-price-eda.git
```

### 2️⃣ Install Required Libraries
```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn
```

### 3️⃣ Run Jupyter Notebook
```bash
jupyter notebook
```

---

## 📌 Project Status
✅ Completed  
🔄 Open for feedback and improvements  

---

## 🤝 Connect With Me
I’m currently learning Data Analytics and building real-world projects.

## ⭐ If You Found This Useful
Give this repository a star ⭐ and share your feedback!
