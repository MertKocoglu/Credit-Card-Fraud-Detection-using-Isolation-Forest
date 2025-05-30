
---

# 🕵️‍♂️ Credit Card Fraud Detection Using Unsupervised Learning

This project focuses on detecting fraudulent credit card transactions using **unsupervised machine learning** techniques. Specifically, it applies **Isolation Forest** and **Local Outlier Factor (LOF)** to identify anomalies without relying on labeled training data.

## 📁 Dataset

Source: [`creditcard.csv`](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

* Contains 284,807 transactions
* 30 features (V1–V28 are PCA-transformed), along with `Time`, `Amount`, and `Class` (target variable)
* Target `Class`:

  * `0`: Legitimate transaction
  * `1`: Fraudulent transaction

## 🔍 Project Overview

### 1. **Data Exploration & Visualization**

* Examined class distribution (highly imbalanced: only 0.17% fraud)
* Plotted transaction frequency by hour
* Compared feature distributions between fraudulent and normal transactions

### 2. **Feature Engineering**

* Transformed `Time` and `Amount` using PCA to generate `V29` and `V30`
* Applied Z-test to identify statistically significant features
* Selected significant features for modeling

### 3. **Modeling**

#### Isolation Forest

* **Accuracy for detecting normal transactions:** 95.78%
* **Accuracy for detecting fraud transactions:** 86.38%

#### Local Outlier Factor (LOF)

* **Accuracy for detecting normal transactions:** 98.75%
* **Accuracy for detecting fraud transactions:** 23.58%

## 🛠 Libraries Used

* `pandas`, `numpy`, `matplotlib`, `seaborn`
* `sklearn`: PCA, IsolationForest, LocalOutlierFactor

## 📈 Results

* **Isolation Forest** outperformed LOF in detecting fraudulent transactions.
* Due to class imbalance, unsupervised learning offered a valuable approach without requiring labeled training data.

## 🚀 How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/credit-card-fraud-unsupervised.git
   cd credit-card-fraud-unsupervised
   ```

2. Install required packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook:

   ```bash
   jupyter notebook
   ```

## 📌 Notes

* This project uses **unsupervised learning** due to the rarity of fraud cases in the dataset.
* Z-test helped select features with statistically significant differences between fraud and normal transactions.

## 🧠 Developer Notes

This project demonstrates the potential of unsupervised learning methods in detecting anomalies in highly imbalanced datasets. Future improvements could involve deep learning methods such as autoencoders or deep SVDD for even better performance.

---

