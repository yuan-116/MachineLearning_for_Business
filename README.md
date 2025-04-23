# Machine Learning for Business
BUA 751: Machine Learning for Business assignments demonstrating the machine learning skills I acquired at Syracuse University.

# 🏠 Final Project - Energy Efficiency – Machine Learning on Cooling Load
**Author:** ChihHao Luca Yuan  
**Date:** April 2025  

This project applies various machine learning algorithms to predict and classify **Cooling Load**—a crucial factor in building energy efficiency. The dataset comprises building features such as compactness, surface area, and glazing.

---

### 📊 Dataset
Attributes include:
- Relative Compactness, Surface Area, Wall Area, Roof Area, Overall Height, Orientation, Glazing Area, Glazing Area Distribution  
- Targets:  
  - **Cooling Load** (continuous)  
  - **Cooling Category** (A–D, converted to binary for classification)

---

### 🧽 Workflow

#### 1️⃣ Exploratory Data Analysis (EDA)
- **Correlation Analysis** using scatter plots to display relationships between features and Cooling Load.
- **Linear Regression** to assess variable significance (p-values) and multicollinearity (**VIF**).

#### 2️⃣ Model Development

| Model           | Target Variable         | Performance              | Best? |
|----------------|-------------------------|--------------------------|--------|
| Perceptron     | Cooling_cat (A/B vs C/D) | ~84% (best epoch)        |        |
| SVM            | Cooling_cat              | **78.35%**               |        |
| Neural Network | Cooling_Load (regression)| **0.9812 correlation**   | ✔️     |
| KNN (k=51)     | Cooling_cat              | **75.32%**               |        |
| Naive Bayes    | Cooling_cat              | 51.52%                   |        |
| Decision Tree  | Cooling_bi (binary)      | **98.27%**               |        |
| Random Forest  | Cooling_bi               | **99.13%**               | ✔️     |
| XGBoost        | Cooling_bi               | **97.84%**               |        |

---

### 🛠️ Feature Engineering
- Normalized numerical inputs for regression  
- Dummy variables for categorical data  
- Categorical target encoding for classification and binary classification tasks



---



# 🏠 Assignment 4: Pakistan House Price Sales_Analysis
An end-to-end data analytics and machine learning project analyzing house prices in Pakistan. This study explores the impact of property type, city, and house features on housing prices using various predictive modeling techniques.

[📂Files and Presentation](https://github.com/yuan-116/MachineLearning_for_Business/tree/main/Pakistan_House_Price%20_Sales_Analysis)

---

### 📊 Dataset Overview

Key variables:
- Property Type
- City
- Bedrooms
- Bathrooms
- Area (in Marla)
- Price

---

### 🧭 Workflow

#### 1️⃣ Exploratory Data Analysis (EDA)
- Created visualizations to explore price distributions:
  - **By property type**
  - **By city**
- Generated descriptive statistics:
  - **By property type**
  - **By city**

#### 2️⃣ Correlation & Multicollinearity
- Strongest correlation found between **bathrooms and bedrooms** (r = 0.85)
- VIF values for all variables < 10 → no serious multicollinearity

---

#### 3️⃣ Modeling Techniques

##### 🔹 Linear Regression
- Predicts price using property type, city, bedrooms, bathrooms, and area
- Example prediction:
  - Lahore, 3 bedrooms, 2 baths, 10 Marla → **Predicted Price: $12,266,817**

##### 🔹 SVM (Support Vector Machine)
- Target: `pricequartile` (A: Highest, D: Lowest)
- Accuracy: **0.6638**

##### 🔹 Neural Network
- Target: Price
- 5 hidden nodes
- Correlation: **0.84**

##### 🔹 K-Nearest Neighbors (KNN)
- Target: `pricequartile`
- Handled tie issue using `FNN` package
- Accuracy: **0.6837** ✅ (Best accuracy among classification models)

##### 🔹 Naïve Bayes
- Target: `pricequartile`
- Accuracy: **0.5361**

---

#### 📊 Model Comparison

| Model           | Target         | Metric      | Result    |
|----------------|----------------|-------------|-----------|
| SVM            | Price Quartile | Accuracy    | 0.6638    |
| Neural Network | Price          | Correlation | 0.84      |
| KNN            | Price Quartile | Accuracy    | **0.6837** |
| Naïve Bayes    | Price Quartile | Accuracy    | 0.5361    |

---

### 🛠 Tools & Techniques
- R Studio(dplyr, corrplot, car, fastDummies, e1071, caret, neuralnet, class, FNN, gmodels)
- Machine Learning Models: Linear Regression, SVM, Neural Networks, KNN, Naïve Bayes
- VIF Analysis, Correlation Matrix, Dummy Encoding

---

# 🍷 Assignment 3: Wine Quality Analysis

A regression-focused machine learning project using **Linear Regression** and **Neural Networks** to predict wine quality based on physicochemical tests.

[📂Files and Presentation](https://github.com/yuan-116/MachineLearning_for_Business/tree/main/Wine_Quality_Analysis)

### 📊 Dataset
The dataset contains various physicochemical properties of wine such as:
- Alcohol
- Chlorides
- Density
- Fixed Acidity
- Volatile Acidity
- pH
- Sulphates
- Residual Sugar
- Free Sulfur Dioxide
- Total Sulfur Dioxide

Target variable: **Quality** (numeric score)

---

### 🧭 Workflow

#### 1️⃣ Exploratory Data Analysis (EDA)
##### Correlation Analysis
- Plotted wine quality against each feature to observe trends.
- Found strong pairwise correlations:
  - **Residual Sugar & Density** (0.8388)
  - **Density & Alcohol** (-0.7806)

- Most impactful on quality:
  - **Alcohol** (0.4354)
  - **Density** (-0.3055)


---
#
#### 2️⃣ Linear Regression

##### Full Model:
- Used all variables
- Identified **8 significant variables**

##### Variance Inflation Analysis(AIF) Analysis:
- **Density (VIF=28.21)** and **Residual Sugar (VIF=12.62)** showed high multicollinearity

##### Refined Model:
- Used only the 8 significant variables
- Positive impact: Alcohol, Fixed Acidity, pH, Residual Sugar, Sulphates, Free SO₂
- Negative impact: Density, Volatile Acidity

---

#### 3️⃣ Neural Networks

| Model | Input Variables | Hidden Nodes | Accuracy |
|-------|------------------|--------------|----------|
| Model 1 | All | 1 | 0.5081 |
| Model 2 | All | 2 | 0.5390 |
| Model 3 | All | 3 | 0.5482 |
| Model 4 | All | 4 | 0.5636 |
| Model 5 | All | 5 | **0.5728** ✅ |
| Model 6 | Significant Only | 1 | 0.5099 |
| Model 7 | Significant Only | 2 | 0.5405 |
| Model 8 | Significant Only | 3 | 0.5431 |
| Model 9 | Significant Only | 4 | 0.5631 |
| Model 10 | Significant Only | 5 | 0.5580 |

---

### 🛠 Tools & Techniques
- R Studio( dplyr, psych, corrplot, ggplot2, car, neuralnet)
- Machine Learning Model: Neural Networks (Multilayer Perceptron)
- Correlation, Linear Regression, VIF for multicollinearity diagnostics


---

# 🩺 Assignment 2: Indian Liver Patient Analysis


A machine learning classification project using **Logistic Regression** and **Neural Networks** to analyze and predict liver disease based on patient attributes.

[📂Files and Presentation](https://github.com/yuan-116/MachineLearning_for_Business/tree/main/Indian_Liver_Patient_Analysis)


### 📊 Dataset
This analysis focuses on Indian Liver Patient records with features such as:
- Age
- Total Bilirubin, Direct Bilirubin
- Alkaline Phosphotase
- Alamine and Aspartate Aminotransferase
- Albumin, Total Proteins, Albumin/Globulin Ratio
- Gender

Target variable: **Disease (1 = Liver Disease, 0 = No Disease)**

---

### 🧭 Workflow

#### 1️⃣ Exploratory Data Analysis (EDA)
##### Correlation Analysis
- Visualized the relationship between each continuous variable and disease status
- Highlighted two strong pairwise relationships:
  - **Direct Bilirubin vs. Total Bilirubin**
  - **Aspartate vs. Alamine Aminotransferase**
  - Performed Pearson correlation across all variables
  - **Direct Bilirubin** showed the strongest correlation with disease status (0.2463)

---

#### 2️⃣ Logistic Regression (Logit)
- Identified variables with significant predictive power:
  - **Positive impact**: Age, Alamine Aminotransferase, Total Proteins
  - **Negative impact**: Albumin

---

#### 3️⃣ Neural Networks (Binary Classification)

| Model | Input Variables | Hidden Nodes | Accuracy |
|-------|------------------|--------------|----------|
| Model 1 | All | 1 | 0.7011 |
| Model 2 | All | 2 | 0.7011 |
| Model 3 | All | 3 | 0.7069 |
| Model 4 | Significant only | 1 | 0.7011 |
| Model 5 | Significant only | 2 | 0.7011 |
| Model 6 | Significant only | 3 | **0.7414** ✅ |

- Using only statistically significant variables increased model efficiency and performance
---

### 🛠 Tools & Techniques
- R Studio (neuralnet, caret)
- Machine Learning Models: Neural Networks (binary output)
- Correlation Analysis, Logit Regression

  ---
# 🫀 Assignment 1: Medical Analysis -- Heart Failure
A machine learning classification project using Perceptron and Support Vector Machine (SVM) to predict heart failure events based on patient clinical records.

[📂Files and Presentation](https://github.com/yuan-116/MachineLearning_for_Business/tree/main/Medical_Analysis_HeartFailure)

### 📊 Dataset
This project analyzes a heart failure dataset including features such as:
- Age
- Serum Creatinine
- Serum Sodium
- Ejection Fraction
- Creatinine Phosphokinase
- Smoking, Diabetes, etc.

Target variable: **DEATH_EVENT (0 = Alive, 1 = Death)**

---

### 🧭 Workflow

#### 1️⃣ Exploratory Data Analysis (EDA)
##### Correlation Analysis:
- Visualized relationship between `DEATH_EVENT` and continuous variables
- Plotted pairwise relationships with color-coded death events
---

#### 2️⃣ Perceptron Models

| Model | Features Used | Accuracy |
|-------|----------------|----------|
| Model 1 | Ejection Fraction, Age | 0.633 |
| Model 2 | Ejection Fraction, Serum Creatinine | 0.644 |
| Model 3 | Ejection Fraction, Serum Creatinine, Age | 0.667 |
| Model 4 | Ejection Fraction, Serum Creatinine, Serum Sodium, Age | **0.711** ✅

---

#### 3️⃣ Support Vector Machines (SVM)

| Model | Features Used | Accuracy |
|-------|----------------|----------|
| Model 1 | Age, Smoking | 0.689 |
| Model 2 | Diabetes, Creatinine Phosphokinase | 0.678 |
| Model 3 | Age, Smoking, Diabetes, CPK | **0.700** ✅ |
| Model 4 | Age, Smoking, Diabetes, Sex, High Blood Pressure, Ejection Fraction | 0.689 |

- SVM Results were interpreted visually to analyze:
  - Effects of **smoking** and **diabetes**
  - Risk comparison between patient profiles (e.g., smoker vs non-smoker, with/without high blood pressure)
 
  ---
🛠 Tools & Techniques

- R Studio (dplyr, ggplot2, e1071)

 - Machine Learning Models: Perceptron, SVM

- Accuracy Evaluation






