
# 🚲 Bike Sharing Demand Prediction - Linear Regression Model

This project focuses on predicting the demand for shared bikes using a **multiple linear regression model**. The dataset includes various features such as weather conditions, temperature, season, and working days to model and predict the count of total rental bikes (`cnt`).

---

## 📁 Contents

- `Bike_Sharing_Assignment.ipynb` – Jupyter notebook containing the entire analysis and modeling steps.
- `day.csv` – Dataset with daily bike-sharing data.
- `README.md` – This file.

---

## 📌 Objective

The goal is to build a **linear regression model** to:
- Understand the relationship between various factors and bike rental counts.
- Identify the most influential variables.
- Predict future demand accurately based on historical trends.

---

## 📚 Dataset Description

The dataset `day.csv` contains the following key columns:

| Column       | Description |
|--------------|-------------|
| `dteday`     | Date |
| `season`     | Season (1:spring, 2:summer, 3:fall, 4:winter) |
| `yr`         | Year (0:2018, 1:2019) |
| `mnth`       | Month |
| `holiday`    | Whether the day is a holiday |
| `weekday`    | Day of the week |
| `workingday` | If day is neither weekend nor holiday |
| `weathersit` | Weather situation |
| `temp`       | Normalized temperature |
| `atemp`      | Normalized "feels-like" temperature |
| `hum`        | Humidity |
| `windspeed`  | Wind speed |
| `cnt`        | Total bike rentals (target variable) |

---

## 🛠️ Methodology

### 1. **Data Cleaning & Preparation**
- Dropped irrelevant columns (`instant`, `dteday`, `casual`, `registered`).
- Converted categorical variables (`season`, `mnth`, `weekday`, `weathersit`) to dummy variables using `pd.get_dummies(drop_first=True)`.
- Checked for multicollinearity using **correlation matrix** and **VIF**.

### 2. **Data Splitting**
- Dataset split into training (70%) and testing (30%) using `train_test_split`.

### 3. **Model Building**
- Built initial regression model using **`statsmodels.api.OLS`**.
- Refined the model iteratively by removing variables with high p-values.
- Finalized the model based on adjusted R-squared and significance.

### 4. **Model Evaluation**
- Predictions made on test data.
- Evaluation metrics: **R-squared**, **Adjusted R-squared**, and **Residual Analysis**.
- Plotted residuals and Q-Q plot to check assumptions of linear regression.

---

## 📊 Key Findings

- `atemp` (feeling temperature), `yr`, and `workingday` are the most influential variables.
- The final model explains **~83% of the variance** in the test data (R-squared ≈ 0.83).
- The residuals were approximately normal and randomly distributed – satisfying linear regression assumptions.

---

## ✅ Requirements

This project uses the following Python libraries:

```bash
pandas
numpy
matplotlib
seaborn
statsmodels
sklearn
```

Install them using pip:

```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn
```

---

## 📈 How to Run

1. Clone the repository or download the `.ipynb` and dataset.
2. Open the notebook in JupyterLab / Jupyter Notebook.
3. Run all cells to see the data analysis and model output.

---

## 🧠 Learnings

- Importance of feature engineering and variable encoding.
- How to check for multicollinearity using **VIF**.
- Evaluating model assumptions with **residual plots** and **Q-Q plots**.
- Using **OLS summary** to interpret coefficients and p-values.

---

## 📌 Author

Shital Nawale
