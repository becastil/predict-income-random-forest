

## 🧠 Project: Predict Income with Random Forest

Using UCI Census data to predict whether a person earns more than \$50K/year

---

## 📁 How This Project Works — Step by Step

### **1. Load the dataset**

* Read `income.csv` into a Pandas DataFrame using `pd.read_csv()`
* Clean spacing issues using `str.strip()` or `delimiter=", "`

### **2. Explore the data**

* Use `.head()` and `.iloc[0]` to inspect columns and row format
* Identify `"income"` as the **target label**

### **3. Format the data**

* Separate labels into a variable called `labels`
* Choose relevant features:

  * `"age"`, `"capital-gain"`, `"capital-loss"`, `"hours-per-week"`
  * Plus optional: `"sex"`, `"native-country"` (after transforming)

### **4. Preprocess string columns**

* Convert `"sex"` to `"sex-int"` → `0` for Male, `1` for Female
* Convert `"native-country"` to `"country-int"` → `0` for US, `1` for all others

### **5. Split the data**

* Use `train_test_split()` to split `data` and `labels` into:

  * `train_data`, `test_data`, `train_labels`, `test_labels`

### **6. Train a Random Forest model**

* Create model with:
  `forest = RandomForestClassifier(random_state=1)`
* Fit the model with:
  `forest.fit(train_data, train_labels)`

### **7. Evaluate accuracy**

* Score the model:
  `forest.score(test_data, test_labels)`

### **8. Explore further**

* Add more features (`sex-int`, `country-int`, `education-num`)
* Use `forest.feature_importances_` to interpret model
* Compare with `DecisionTreeClassifier` performance

