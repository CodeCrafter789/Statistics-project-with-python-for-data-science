# Statistics-project-with-python-for-data-science
You are a Data Scientist with a housing agency in Boston MA, you have been given access to a previous dataset on housing prices derived from the U.S. Census Service to present insights to higher management. 

# 🏠 Boston Housing Data Analysis

This project performs **descriptive analysis**, **visualization**, and **statistical testing** on the Boston Housing dataset. The goal is to understand the relationships between housing features and the median home value (`MEDV`), while applying real-world data science tools and techniques.

## 📁 Dataset Description

The dataset includes information on various attributes of housing in Boston suburbs.  

**Variables:**
- `CRIM`: per capita crime rate by town
- `ZN`: proportion of residential land zoned for lots over 25,000 sq.ft.
- `INDUS`: proportion of non-retail business acres per town
- `CHAS`: Charles River dummy variable (1 = bounds river; 0 = does not)
- `NOX`: nitric oxides concentration (parts per 10 million)
- `RM`: average number of rooms per dwelling
- `AGE`: proportion of owner-occupied units built prior to 1940
- `DIS`: weighted distances to five Boston employment centres
- `RAD`: accessibility to radial highways
- `TAX`: full-value property-tax rate per $10,000
- `PTRATIO`: pupil-teacher ratio by town
- `LSTAT`: % lower status of the population
- `MEDV`: median value of owner-occupied homes in $1000s

---

## 📊 Task 1: Visualizations

1. **Boxplot for Median Home Values (`MEDV`)**
   - Shows right-skewed distribution
   - Several high-value outliers, capped at \$50,000

2. **Bar Plot for Charles River Variable (`CHAS`)**
   - Most homes are not near the Charles River (CHAS = 0)

3. **Boxplot: `MEDV` vs Discretized `AGE`**
   - `AGE` grouped as:
     - `<=35` (New)
     - `36–70` (Mid-age)
     - `70+` (Old)
   - Newer homes tend to have higher median values

4. **Scatter Plot: `NOX` vs `INDUS`**
   - Strong positive correlation
   - More industrial areas → higher pollution

5. **Histogram of `PTRATIO`**
   - Most towns have PTRATIO between 17–20

---

## 🔬 Task 2: Statistical Testing (α = 0.05)

### 1. T-Test: Does proximity to the Charles River affect `MEDV`?

- **H₀**: No difference in `MEDV` for CHAS=0 and CHAS=1  
- **t = -3.11**, **p = 0.0036**
- ✅ **Reject H₀**: River proximity **significantly affects** home value.

---

### 2. ANOVA: Does house age affect `MEDV`?

- **Groups**: `<=35`, `36–70`, `70+`  
- **F = 36.41**, **p < 0.0001**
- ✅ **Reject H₀**: Home age group **significantly affects** `MEDV`.

---

### 3. Pearson Correlation: `NOX` vs `INDUS`

- **r = 0.76**, **p < 0.0001**
- ✅ Strong **positive correlation** between industrialization and pollution.

---

### 4. Linear Regression: `DIS` → `MEDV`

\[
\text{MEDV} = 18.39 + 1.09 \cdot \text{DIS}
\]

- Coefficient for `DIS` is **+1.09**
- **p < 0.0001**
- ✅ Distance to employment centers **positively affects** home value.

---

## ⚠️ Ethical Note
The `Boston Housing Dataset` is deprecated due to ethical concerns (e.g., race-based features in original data source). This analysis is for **academic learning only**. Consider using modern datasets like:
- `fetch_california_housing`
- `Ames Housing Dataset`

---

## 🛠️ Tools Used
- Python 3.8+
- Pandas
- Seaborn / Matplotlib
- Scipy
- Statsmodels
- Scikit-learn (for dataset only)

---

## 📂 How to Run
```bash
pip install pandas numpy seaborn matplotlib scipy statsmodels scikit-learn
python your_script.py
