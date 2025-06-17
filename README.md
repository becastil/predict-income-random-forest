
```markdown
# 🧠 Predict Income with Random Forest

This machine learning project uses UCI Census data to predict whether a person earns more than \$50,000 per year. We apply a **Random Forest Classifier** and explore feature importance, preprocessing, and model comparison.

---

## 📂 Dataset

The dataset is from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/adult). It includes demographic and economic information for over 32,000 individuals, with features such as:

- Age
- Work class
- Education level
- Marital status
- Occupation
- Capital gain/loss
- Hours worked per week
- Native country
- Gender
- Income label (`<=50K` or `>50K`)

---

## ⚙️ Project Workflow (Step-by-Step)

### 1. Load the Dataset
- Read `income.csv` using `pd.read_csv()`
- Handle spacing issues with `delimiter=", "` or `.applymap(str.strip)`

### 2. Explore the Data
- Use `.head()` and `.iloc[0]` to inspect structure
- Confirm the **label column** is `"income"`

### 3. Format the Data
- Extract `"income"` column as `labels`
- Select relevant features:
  - `"age"`, `"capital-gain"`, `"capital-loss"`, `"hours-per-week"`

### 4. Transform Categorical Columns
- Convert `"sex"` to `"sex-int"`:
  - `Male → 0`, `Female → 1`
- Convert `"native-country"` to `"country-int"`:
  - `United-States → 0`, all others → `1`

### 5. Split the Data
- Use `train_test_split()` to create:
  - `train_data`, `test_data`
  - `train_labels`, `test_labels`

### 6. Train the Model
- Initialize with:  
  `forest = RandomForestClassifier(random_state=1)`
- Train with:  
  `forest.fit(train_data, train_labels)`

### 7. Evaluate Accuracy
- Test with:  
  `forest.score(test_data, test_labels)`
- Example result:  
  `Random Forest Accuracy: 82.25%`

### 8. Interpret the Model
- Use `forest.feature_importances_` to understand which features matter most
- Example importance ranking:
```

age: 0.3135
capital-gain: 0.2927
hours-per-week: 0.2031
capital-loss: 0.1175
sex-int: 0.0644
country-int: 0.0089

````

### 9. Compare with a Decision Tree
- Train a `DecisionTreeClassifier` and compare accuracy
- Example result:  
`Decision Tree Accuracy: 82.26%`

---

## 📊 Key Insights

- `age`, `capital-gain`, and `hours-per-week` are strong predictors of income
- Simplifying `"native-country"` into a binary flag had minimal impact
- Random Forest and Decision Tree performed similarly on this dataset

---

## 📁 Files Included

- `predict_income_random_forest.ipynb` — full notebook with code and outputs
- `income.csv` — cleaned version of the dataset
- `README.md` — project overview and instructions

---

## 🚀 Getting Started

### Requirements
- Python 3.8+
- pandas
- scikit-learn
- Jupyter Notebook

### To Run Locally:

```bash
git clone https://github.com/becastil/predict-income-random-forest.git
cd predict-income-random-forest
jupyter notebook predict_income_random_forest.ipynb
````

---

## 🙌 Acknowledgments

* Dataset: UCI Machine Learning Repository
* Project inspired by Codecademy's “Build a Machine Learning Model” track

```

---


