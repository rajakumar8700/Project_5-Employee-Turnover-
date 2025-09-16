# Employee Turnover

This project predicts **employee turnover** (whether an employee will leave the company) using machine learning on HR data.  
It analyzes employee satisfaction, workload, promotions, and other factors to identify patterns behind attrition.  

---

## Important Libraries Used
- `pandas` – Data processing and manipulation  
- `numpy` – Numerical operations  
- `matplotlib` – Data visualization  
- `seaborn` – Statistical visualization  
- `scikit-learn` – Machine learning (classification models, evaluation metrics)  

---

## Dataset
- **Dataset:** `HR_comma_sep.csv`  
- **Key Columns:**
  - `satisfaction_level`: Employee satisfaction score  
  - `last_evaluation`: Last performance evaluation score  
  - `number_project`: Number of projects assigned  
  - `average_montly_hours`: Average monthly working hours  
  - `time_spend_company`: Number of years spent in the company  
  - `Work_accident`: Whether the employee had a work accident (1 = Yes, 0 = No)  
  - `promotion_last_5years`: Whether the employee was promoted in the last 5 years (1 = Yes, 0 = No)  
  - `Department`: Department of the employee  
  - `salary`: Salary level (low, medium, high)  
  - `left`: Target variable (1 = employee left, 0 = stayed)  

---

## Methodology
1. **Data Cleaning & Preprocessing**  
   - Checked for missing values and inconsistencies.  
   - Encoded categorical variables (`Department`, `salary`).  

2. **Exploratory Data Analysis (EDA)**  
   - Analyzed satisfaction, workload, and tenure.  
   - Visualized turnover trends by salary, promotion, and departments.  

3. **Modeling**  
   - Applied classification algorithms (e.g., Logistic Regression, Decision Trees, Random Forest).  
   - Evaluated models using accuracy, precision, recall, and F1-score.  

---

## Model Performance
Three models were tested to predict employee turnover:

- **Logistic Regression**  
  - Precision: 0.9096  
  - Recall: 0.7109  
  - F1-score: 0.9229  
  - Sacrifices recall (misses ~29% of true leavers).  

- **Random Forest Classifier**  
  - Precision: 0.9096  
  - Recall: 0.9788  
  - F1-score: 0.9229  
  - Best overall model, with the highest recall and balanced metrics.  

- **Gradient Boosting Classifier**  
  - Precision: 0.9096  
  - Recall: 0.9365  
  - F1-score: 0.9229  
  - Good middle ground, slightly below Random Forest.  

### Conclusion
- **Random Forest is the best-performing model**, capturing almost all employees likely to leave while maintaining high precision.  
- **Gradient Boosting** also performs well, slightly less accurate but still reliable.  
- **Logistic Regression**, while interpretable, underperforms in recall, making it less suitable for attrition prediction.  

---

## Key Insights

- Employees with **low satisfaction levels** are far more likely to leave.  
- **Very high or very low working hours** increase turnover risk.  
- Lack of **promotion opportunities** strongly correlates with attrition.  
- **Salary** plays an important role: employees with **low salaries** are more likely to leave compared to medium or high.  
- Departments show varied turnover rates, with some (like sales & support) having higher attrition.  

### Project Distribution
- Employees with **2 projects** show very high attrition (likely due to underutilization).  
- Employees with **3–4 projects** are the most stable and engaged.  
- Employees with **6–7 projects** show high attrition again (likely due to burnout).
  <img width="885" height="688" alt="Screenshot 2025-09-16 163903" src="https://github.com/user-attachments/assets/86faf9f0-f363-4a72-a4ce-f51d7a8f6ec7" />


### Clustering Insights (Satisfaction vs Evaluation)
- **Cluster 0 (Low Satisfaction, Moderate Evaluation)** → Dissatisfied and undervalued employees, highly likely to leave.  
- **Cluster 1 (High Satisfaction, High Evaluation)** → Loyal and engaged employees, least likely to leave.  
- **Cluster 2 (Low Satisfaction, High Evaluation)** → High-performing but dissatisfied employees, **critical risk group** prone to attrition due to burnout or lack of recognition.  
<img width="1051" height="556" alt="Screenshot 2025-09-16 164024" src="https://github.com/user-attachments/assets/4e8b801b-9a7e-49d8-bd78-84a10f95c50d" />

---
