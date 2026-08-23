# Patient-Health-Analytics-Predictive-Modeling-with-Python

## 📌 Project Overview

This project explores a medical dataset containing **6,000 patient records and 52 variables**. The dataset contains information about patient demographics, lifestyle, clinical measurements, hospital admissions, medications, healthcare costs, patient satisfaction, and health outcomes. 

The main goal of this project was to use **Python for exploratory data analysis, visualization, statistical analysis, and machine learning** to uncover meaningful patterns within the healthcare data and explore whether patient outcomes and healthcare costs could be predicted.

---

## 🎯 Objectives

The project focused on answering several questions:

* Which hospital departments have the longest average patient stay?
* How does estimated annual healthcare cost differ by insurance type?
* How are BMI, glucose and HbA1c related across different age groups?
* What relationship exists between physical activity, diet quality and blood pressure?
* How are stress levels distributed across different lifestyle groups?
* Can patient 90-day high-risk status be predicted using machine learning?
* Can estimated annual healthcare costs be predicted using patient information?

---

## 🗂️ Dataset

The dataset contains **6,000 records and 52 columns**.

Some of the key variables include:

### Patient Information

* Patient ID
* Admission ID
* Age
* Sex
* Marital Status
* Residence Type
* Insurance Type

### Clinical Information

* BMI
* Blood Pressure
* Heart Rate
* Glucose
* HbA1c
* Total Cholesterol
* HDL
* LDL
* Triglycerides
* Creatinine
* eGFR
* Hemoglobin
* WBC
* Diabetes Status

### Lifestyle Information

* Smoking Status
* Physical Activity
* Diet Quality
* Exercise Minutes
* Daily Water Intake
* Stress Level
* Sleep Hours

### Hospital & Treatment Information

* Department
* Diagnosis Group
* Previous Admissions
* ER Visits
* Medication Count
* Length of Stay
* Medication Class
* Care Plan

### Patient Outcomes

* Complication During Stay
* 30-Day Readmission
* In-Hospital Mortality
* 30-Day Follow-up
* Medication Adherence
* Patient Satisfaction
* High-Risk 90-Day Status

### Financial Information

* Estimated Annual Healthcare Cost

---

## 🛠️ Tools & Technologies

The following tools and libraries were used:

* **Python**
* **Pandas** — data manipulation and analysis
* **NumPy** — numerical operations
* **Matplotlib** — data visualization
* **Seaborn** — statistical visualization
* **Scikit-learn** — machine learning
* **Jupyter Notebook** — analysis environment

---

# 🔍 Exploratory Data Analysis

## 1. Data Cleaning & Exploration

The dataset was first inspected to understand its structure, data types, dimensions and missing values.

Most variables were complete. The main missing-data issue was found in the `Medication_Class` column, which contained **986 missing values**. These values were later assigned to an `"Unassigned"` category during machine-learning preprocessing. 

---

## 2. Average Length of Stay by Department

The average length of stay was calculated for each hospital department.

| Department       | Average Length of Stay |
| ---------------- | ---------------------: |
| Emergency        |              3.80 days |
| Cardiology       |              3.77 days |
| General Medicine |              3.75 days |
| Endocrinology    |              3.62 days |
| Outpatient       |              3.62 days |

**Key finding:** Emergency had the highest average length of stay at **3.80 days**. 

---

## 3. Average Annual Cost by Insurance Type

The estimated annual healthcare cost was compared across insurance types.

| Insurance Type | Average Annual Cost |
| -------------- | ------------------: |
| NHIS           |           $1,500.04 |
| Private        |           $1,488.22 |
| Employer       |           $1,478.29 |
| Self-Pay       |           $1,471.58 |

**Key finding:** NHIS had the highest average estimated annual cost, while Self-Pay had the lowest. 

---

## 4. Age Group Correlation Analysis

Patients were divided into four age groups:

* `<30`
* `30–50`
* `51–70`
* `>70`

The relationships between **BMI, glucose and HbA1c** were then examined.

The strongest relationship was between glucose and HbA1c:

| Age Group | Glucose vs HbA1c Correlation |
| --------- | ---------------------------: |
| <30       |                        0.731 |
| 30–50     |                        0.759 |
| 51–70     |                        0.807 |
| >70       |                        0.819 |

**Key finding:** The correlation between glucose and HbA1c became stronger across the older age groups in this dataset. 

---

# 🥗 Lifestyle Analysis

The project also explored the relationship between **physical activity, diet quality, blood pressure and stress**.

The highest average systolic blood pressure was recorded among patients with **low physical activity and poor diet**, at **137.81 mmHg**.

The lowest average systolic blood pressure was recorded among patients with **low physical activity and good diet**, at **135.21 mmHg**. 

Moderate stress was the most common stress category across the lifestyle groups analysed. For example, patients with moderate physical activity and poor diet recorded **58.2% moderate stress**. 

---

# 📊 Data Visualizations

Several visualizations were created to communicate the findings:

### Distribution Analysis

* Annual healthcare cost by department
* Age distribution
* BMI distribution
* Glucose distribution

### Relationship Analysis

* Clinical metrics correlation heatmap
* BMI vs HbA1c by diabetes status

### Category Analysis

* 30-day readmission by medication adherence
* Patient satisfaction by care plan

These visualizations helped make relationships and distributions within the dataset easier to interpret. 

---

# 🤖 Machine Learning

Two Random Forest models were developed.

## 1. High-Risk 90-Day Prediction

A **Random Forest Classifier** was used to predict whether a patient would be classified as high-risk within 90 days.

The dataset was split into:

* **80% training data**
* **20% testing data**

The model used **100 estimators**. 

### Model Performance

**ROC-AUC: 0.998**

The model achieved a very high ROC-AUC score on the test set, indicating excellent discrimination between high-risk and non-high-risk patients within this dataset. 

Because the score is unusually high, further validation would be important before considering the model for real-world clinical use.

---

## 2. Healthcare Cost Prediction

A **Random Forest Regressor** was also developed to predict estimated annual healthcare costs.

The model was evaluated using:

* **R² Score**
* **RMSE (Root Mean Squared Error)**

The analysis code calculates these metrics, but the recorded Markdown output does not contain the final R² and RMSE values. Therefore, no performance value is reported here. 

---

# 💡 Key Insights

Some of the main findings from the project were:

* The dataset contained **6,000 patient records and 52 variables**.
* Emergency had the highest average length of stay at **3.80 days**.
* NHIS had the highest average estimated annual healthcare cost at **$1,500.04**.
* Glucose and HbA1c showed a strong positive correlation across all age groups.
* The glucose–HbA1c relationship was strongest among patients over 70, with a correlation of **0.819**.
* Low physical activity combined with poor diet was associated with the highest average systolic blood pressure in the lifestyle analysis.
* Moderate stress was the most common stress category across the lifestyle groups.
* The Random Forest high-risk classifier achieved a **0.998 ROC-AUC** on the test data.

---

# 📁 Project Structure

```text
Medical-Data-Analysis/
│
├── medical_prediction_dataset.csv
├── Medical_Analysis.ipynb
├── README.md
│
└── visualizations/
    ├── annual_cost_by_department.png
    ├── clinical_correlation_heatmap.png
    ├── bmi_vs_hba1c.png
    └── readmission_analysis.png
```

# ⚠️ Important Note

This project is intended for **educational and portfolio purposes**.

The dataset is used for data analysis and machine-learning practice and should not be treated as real clinical data. The machine-learning results should not be interpreted as a clinical diagnostic or treatment tool.

In particular, the very high ROC-AUC obtained for the 90-day risk model should be investigated further for potential data leakage and validated using independent data before any real-world application.

---

# 📚 What I Learned

Working on this project helped me strengthen my understanding of:

* Data cleaning
* Exploratory Data Analysis
* GroupBy and aggregation
* Correlation analysis
* Data visualization
* Handling missing values
* Feature encoding
* Train/test splitting
* Random Forest classification
* Random Forest regression
* Model evaluation
* Interpreting healthcare data

More importantly, it reminded me that **data analysis is not just about writing code or producing charts. It's about asking meaningful questions and understanding what the results are actually telling you.**

---

## 👩🏽‍💻 Author

[Simiat Ahmed](https://www.linkedin.com/in/simiat-ahmed-bbbb58146/)

 Python | SQL | Excel | Power BI | Healthcare & Data Analytics

---
