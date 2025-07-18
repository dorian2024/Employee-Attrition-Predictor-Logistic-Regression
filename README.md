# Employee Attrition Prediction Using Logistic Regression

**Week 2 Project – Machine Learning Internship**  

This project focuses on predicting employee attrition using a Logistic Regression model. The objective is to identify whether an employee is likely to leave the organization, based on various HR-related features.

---

## Why Logistic Regression?

Since the problem is a **binary classification** task (Attrition: Yes/No), Logistic Regression is a natural choice. It is:
- Simple and interpretable
- Fast to train
- Well-suited for binary outcomes due to its use of the **sigmoid function**, allowing easy threshold-based decision making.

---

## Project Workflow

### 1. Data Understanding & Cleaning
- Data was loaded using `pandas`.
- Initial inspection (`.info()`, `.head()`) revealed:
  - No missing values
  - Categorical features were already encoded
- Duplicate rows were removed using `drop_duplicates()`.

### 2. Exploratory Data Analysis (EDA)
- Visualizations included histograms, boxplots, countplots, and heatmaps.
- These helped in understanding feature distributions and relationships with the target variable.
- Dropped uninformative or constant columns:
  - `'EmployeeCount'`, `'StandardHours'`, `'Over18'`

### 3. Data Preprocessing
- **Categorical Encoding**:
  - **Ordinal features**: Label Encoding
  - **Nominal features**: One-Hot Encoding
- **Feature Scaling**:
  - Used `StandardScaler` instead of MinMaxScaler, as logistic regression performs better when features are centered around zero with unit variance.

### 4. Model Development & Evaluation
- **Model 1**: Basic logistic regression with default parameters and fixed iteration count.
  - Result: Biased toward "No Attrition" due to class imbalance.
- **Model 2**: Logistic regression with **class weighting** to address imbalance.
  - Result: Improved prediction for "Yes Attrition", though at the cost of reduced precision and overall accuracy.

> **Observation**:  
> - Model 1 had higher precision overall but struggled with minority class ("Yes").  
> - Model 2 balanced predictions better but reduced precision and slightly lowered accuracy.

### 5. Conclusion & Recommendations
- Achieved an overall **accuracy of ~75%**.
- Future improvements may include:
  - **Model experimentation**: Try decision trees, ensemble methods, etc.
  - **Better sampling**: Use SMOTE or iterative stratified splitting to handle class imbalance.
  - **Feature selection**: Evaluate feature importance or use dimensionality reduction techniques.

---

## Files in This Repository

- `employee_attrition.csv` – Dataset used for training and evaluation
- `logistic_regression_attrition.ipynb` – Jupyter Notebook with complete analysis and model development
- `README.md` – Project documentation

---

## 🛠 Technologies Used

- Python 3.x
- Jupyter Notebook
- pandas, numpy
- seaborn, matplotlib
- scikit-learn

---

## License

This project is developed as part of an internship and is shared for educational purposes.

