# Mastering the Data Science Foundations – Student Alex Bataniuc

This repository contains the full project for the **Mastering the Data Science Foundations** module.  
The goal of the project is to explore, clean, model, and interpret student engagement data from Tomorrow University to predict which students will become highly engaged by mid-semester.
## 📂 Project Structure

```
Mastering the Data Science Foundations/
│
├── data/
│   ├── student_data.db
│   ├── cleaned_student_data.csv
│
├── notebooks/
│   ├── Step_1.ipynb
│   ├── Step_2.ipynb
│   ├── Step_3.ipynb
│   ├── Step_4.ipynb
│
├── requirements.txt
└── README.md
```
## 🚀 How to Run the Project
### 1. Access

GitHub: https://github.com/bug2200/Mastering-the-Data-Science-Foundations.git

### 2. Open the notebooks

All project notebooks are inside the `notebooks/` folder:

- `Step_1.ipynb` – Exploratory Data Analysis  
- `Step_2.ipynb` – Cleaning & Feature Engineering  
- `Step_3.ipynb` – Baseline Modeling  
- `Step_4.ipynb` – Model Tuning & Interpretation

### 3. Dataset paths are already configured

All notebooks automatically load data from:  
../data/student_data.db  
../data/cleaned_student_data.csv

### 4. Requirements

The project uses standard Python data science libraries.  
All dependencies are listed in the `requirements.txt` file.

Here is the full list used in this project:  
pandas  
numpy  
matplotlib  
seaborn  
scikit-learn   
jupyter

To install everything at once:  
`pip install -r requirements.txt`
---
## 📘 Dataset Description
The project uses anonymized student engagement data provided by Tomorrow University.  
The dataset includes the first 4 weeks of behavioral activity after enrollment.

### Files
- **`student_data.db`** – original SQLite database containing all raw student records.
- **`cleaned_student_data.csv`** – the fully preprocessed dataset generated in Step 2 (ready for modeling).

### Features
The dataset contains the following variables:

- **sex** – gender identity (categorical)
- **birthdate** – date of birth (string format)
- **age** – student age (numeric)
- **country** – country of residence
- **logged in** – hours logged into the learning app during the first 4 weeks
- **lessons** – number of completed lessons
- **assignments** – number of submitted assignments
- **posts** – number of discussion posts
- **mentoring** – whether the student signed up for the mentoring program (Yes/No)
- **orientation** – participation in the in-person orientation event (0/1)
- **score** – engagement score (target variable)
---
## 📊 Analysis Summary

The project follows a complete data science workflow, split across four structured notebooks:

### **Step 1 – Exploratory Data Analysis (EDA)**
- Examined distributions, missing values, and potential outliers  
- Explored relationships between behavioural features and engagement score  
- Identified initial patterns supporting the project hypothesis  

### **Step 2 – Data Cleaning & Feature Engineering**
- Imputed missing values using context-aware methods  
- Handled inconsistent entries and removed structurally invalid values  
- Created new features (total activity)  
- Standardized numerical features and encoded categorical variables  

### **Step 3 – Baseline Modeling**
- Selected regression as the appropriate model type  
- Trained Linear Regression, KNN, and Random Forest  
- Evaluated performance using MSE, RMSE, and R²  
- Identified Linear Regression as the strongest baseline performer  

### **Step 4 – Model Tuning & Interpretation**
- Tuned Random Forest using GridSearchCV  
- Compared tuned vs baseline models  
- Created interpretability visualisations (RMSE vs R² bubble chart, feature importance)  
- Confirmed that Linear Regression remains the best-performing model  

## Final Model Selection

After evaluating all baseline models and testing a tuned version of Random Forest, the final selected model for predicting student engagement is:
 **🏆 Linear Regression**

### ✔ Why Linear Regression was selected
- It achieved the **lowest RMSE** and **highest R²** among all tested models.
- It generalised better than both Random Forest and KNN.
- Random Forest tuning did **not** improve performance and slightly worsened test-set accuracy.
- The underlying relationships in the dataset appear mostly **linear**, making Linear Regression the most appropriate and interpretable choice.
- The model provides strong predictive performance while remaining simple, transparent, and easy to communicate to stakeholders.

### ✔ What this means for the data
Early behavioural activity, especially lessons, assignments, and logged-in hours - shows a clear linear relationship with engagement.  
This suggests that simple, interpretable models can successfully identify early predictors of engagement without requiring more complex non-linear algorithms.

