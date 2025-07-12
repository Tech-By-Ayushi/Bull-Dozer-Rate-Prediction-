# 🚜 Bull-Dozer-Rate-Prediction

---

**Predicting the future sale price of heavy equipment with ML & scikit-learn**

---


## 🧠 Overview

Welcome to the **Bluebook for Bulldozers** machine learning project!
This notebook demonstrates how to build a predictive model that estimates the **sale price of used bulldozers** using historical auction data.

> **Problem Statement**:
> *Can we accurately predict the future sale price of a bulldozer based on its features and historical sales data?*

---

## 📦 Dataset

The data comes from the [Kaggle Bluebook for Bulldozers competition](https://www.kaggle.com/competitions/bluebook-for-bulldozers).
It includes various features about bulldozers such as sale date, model, usage hours, manufacturer, and more.

### 📁 Files Used:

| File                | Description                                           |
| ------------------- | ----------------------------------------------------- |
| `Train.csv`         | Data up to 2011 (used for training)                   |
| `Valid.csv`         | Jan–Apr 2012 (used for public leaderboard validation) |
| `Test.csv`          | May–Nov 2012 (final evaluation; hidden during comp)   |
| `TrainAndValid.csv` | Combined training and validation set (used here)      |

---

## 🛠️ Tech Stack

* **Python 3.8+**
* **Pandas, NumPy** – data manipulation
* **scikit-learn** – modeling and evaluation
* **Matplotlib, Seaborn** – visualizations
* **Jupyter Notebook** – interactive development

---

## 📊 Model Performance

We trained a `RandomForestRegressor` on a subset of the data (`max_samples=10,000`) and achieved the following results:

| Metric       | Training | Validation |
| ------------ | -------- | ---------- |
| **MAE**      | 5,561.30 | 7,177.26   |
| **RMSLE**    | 0.2577   | 0.2936     |
| **R² Score** | 0.8607   | 0.8320     |

> ✅ **Conclusion**: The model generalizes well with limited overfitting. Further improvement is possible with tuning and feature engineering.

---

## 🔧 Hyperparameter Tuning

We used **RandomizedSearchCV** to explore the hyperparameter space efficiently:

```python
params = {
  'n_estimators': [100, 200, 500],
  'max_depth': [None, 10, 30],
  'min_samples_split': [2, 5, 10],
  'min_samples_leaf': [1, 2, 4],
  'max_features': ['auto', 'sqrt']
}
```

This helped optimize model performance while keeping training times reasonable.

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/bulldozer-price-prediction.git
cd bulldozer-price-prediction
```

### 2️⃣ Install Requirements

```bash
pip install -r requirements.txt
```

### 3️⃣ Download the Data

* Get the dataset from [Kaggle](https://www.kaggle.com/competitions/bluebook-for-bulldozers).
* Place the `TrainAndValid.csv` inside a folder named `bluebook-for-bulldozers/`.

### 4️⃣ Run the Notebook

```bash
jupyter notebook
```

Open `bulldozer-price-prediction.ipynb` and follow the steps!

---
