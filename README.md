
---

# 💳 Credit Card Fraud Detection using Unsupervised Learning

This project focuses on detecting fraudulent credit card transactions using **unsupervised anomaly detection techniques**, particularly useful in highly imbalanced datasets. The dataset used comes from a real-world anonymized credit card transactions dataset containing both fraudulent and legitimate transactions.

---

## 📊 Dataset

The dataset used (`creditcard.csv`) contains 284,807 transactions, out of which only 492 are fraudulent. Due to confidentiality, the features have been anonymized using PCA transformations (`V1` to `V28`). Additional features include:

* `Time`: Time elapsed since the first transaction.
* `Amount`: Transaction amount.
* `Class`: Target label (`0` = legitimate, `1` = fraud).

---

## 🛠️ Key Components

### 🔍 Data Exploration & Visualization

* Class imbalance visualized via bar plots.
* Temporal patterns observed by converting `Time` into hourly bins.
* Distribution plots to understand how feature values differ between fraud and normal transactions.

### 📐 Dimensionality Reduction

* Performed PCA on `Time` and `Amount` to create two new features: `V29` and `V30`.

### 📊 Feature Significance

* Z-test used to identify statistically significant features that differ between fraud and normal transactions.
* Selected 23 key features for modeling.

---

## 🚀 Anomaly Detection Models

### 1. **Isolation Forest**

* ✅ Normal Detection Accuracy: **95.78%**
* ⚠️ Fraud Detection Accuracy: **86.38%**

### 2. **Local Outlier Factor (LOF)**

* ✅ Normal Detection Accuracy: **98.75%**
* ⚠️ Fraud Detection Accuracy: **23.58%**

### 3. **One-Class SVM**

* Performed a grid search on hyperparameters (`nu`, `gamma`) to optimize detection.
* **Best Model**: `nu=0.1`, `gamma=0.1`

  * ✅ Normal Accuracy: **90.00%**
  * ⚠️ Fraud Accuracy: **90.24%**

---

## 🧪 Evaluation Metrics

The models were evaluated based on:

* **Accuracy** of predicting normal and fraud cases separately.

---

## 📦 Libraries Used

* `pandas`, `numpy`
* `matplotlib`, `seaborn`
* `scikit-learn` (PCA, IsolationForest, LocalOutlierFactor, OneClassSVM)
* `warnings`, `os`, `itertools`

---

## 📁 File Structure

```
.
├── creditcard.csv           # Dataset
├── model.ipynb              # Main analysis notebook
├── README.md                # Project documentation
└── .git/                    # Git tracking directory
```

---

## 📈 Key Insights

* Unsupervised learning can perform remarkably well in fraud detection with proper preprocessing and tuning.
* One-Class SVM outperformed other methods with balanced accuracy on both normal and fraud classes.

---

## ✅ Future Improvements

* Implement ensemble strategies to combine multiple anomaly detectors.
* Evaluate with precision/recall/F1-score for comprehensive insights.
* Use autoencoders or deep anomaly detection methods for comparison.

---

## 📬 Contact

Feel free to reach out or fork this project to build upon it. Contributions welcome!

---

