# Vendor Invoice Intelligence System

**Freight Cost Prediction & Invoice Risk Flagging**

## 📌 Table of Contents

* [Project Overview](#project-overview)
* [Business Objectives](#business-objectives)
* [Data Sources](#data-sources)
* [Exploratory Data Analysis](#eda)
* [Models Used](#models-used)
* [Evaluation Metrics](#metrics)
* [End-to-End Application](#application)
* [Project Structure](#project-structure)
* [How to Run This Project](#how-to-run-this-project)
* [Author & Contact](#author--contact)

---

<a id="project-overview"></a>

## 📌 Project Overview

This project implements an **end-to-end machine learning system** designed to support finance and procurement teams by:

1. **Predicting expected freight cost** for vendor invoices.
2. **Flagging high-risk invoices** that require manual review due to abnormal cost, freight, or operational patterns.

The project combines **SQL, Python, Machine Learning, Statistical Analysis, and Streamlit** to demonstrate a complete data-to-deployment workflow.

---

<a id="business-objectives"></a>

## 🎯 Business Objectives

### 1. Freight Cost Prediction — Regression

**Objective:**

Predict the expected freight cost for a vendor invoice using invoice-level and historical purchase information.

**Why it matters:**

* Freight is an important component of landed cost.
* Poor freight estimation can affect margin analysis and budgeting.
* Early prediction can support procurement planning and vendor negotiations.

### 2. Invoice Risk Flagging — Classification

**Objective:**

Predict whether a vendor invoice should be flagged for manual review based on abnormal cost, freight, and operational patterns.

**Why it matters:**

* Manual invoice review can be time-consuming.
* Large or unusual invoices may require additional verification.
* Automated risk detection can improve audit efficiency and operational control.

---

<a id="data-sources"></a>

## 📊 Data Sources

Data is stored in a relational **SQLite database (`Inventory.db`)** containing the following tables:

* `vendor_invoice` — Invoice-level financial and timing data
* `purchases` — Item-level purchase details
* `purchase_prices` — Reference purchase prices
* `begin_inventory` — Beginning inventory snapshots
* `end_inventory` — Ending inventory snapshots

SQL aggregation is used to transform the underlying data into invoice-level features for analysis and machine learning.

---

<a id="eda"></a>

## 🔍 Exploratory Data Analysis (EDA)

EDA focuses on business-driven questions, including:

* Do flagged invoices have higher financial exposure?
* Does freight cost increase with quantity?
* Does freight cost depend on invoice characteristics?
* Are there meaningful differences between flagged and normal invoices?

Statistical tests, including **t-tests**, are used to evaluate whether observed differences between invoice groups are statistically significant.

---

<a id="models-used"></a>

## 🤖 Models Used

### 📈 Regression — Freight Cost Prediction

The following models were evaluated:

* Linear Regression — Baseline
* Decision Tree Regressor
* Random Forest Regressor — Final Model

### 🚩 Classification — Invoice Risk Flagging

The following models were evaluated:

* Logistic Regression — Baseline
* Decision Tree Classifier
* Random Forest Classifier — Final Model

**GridSearchCV** is used for hyperparameter tuning, with **F1-score** as the optimization metric to account for class imbalance.

---

<a id="metrics"></a>

## 📈 Evaluation Metrics

### Freight Cost Prediction

The regression models are evaluated using:

* **MAE** — Mean Absolute Error
* **RMSE** — Root Mean Squared Error
* **R² Score** — Coefficient of Determination

### Invoice Risk Flagging

The classification models are evaluated using:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-score**
* **Classification Report**
* **Feature Importance Analysis**

---

<a id="application"></a>

## 🚀 End-to-End Application

A **Streamlit web application** demonstrates the complete machine learning pipeline.

The application allows users to:

* 📝 Enter invoice details
* 📈 Predict expected freight cost
* 🚩 Flag potentially high-risk invoices
* 💡 View human-readable prediction explanations

The application connects the trained machine learning models with a simple user interface for real-time predictions.

---

<a id="project-structure"></a>

## 📁 Project Structure

```text
invoice_intelligence_machine_learning/
├── data/
│   └── Inventory.db
│
├── freight_cost_prediction/
│   ├── data_preprocessing.py
│   ├── model_evaluation.py
│   ├── train.py
│   └── predict_freight.py
│
├── invoice_flagging/
│   ├── data_preprocessing.py
│   ├── model_evaluation.py
│   ├── train.py
│   └── inference/
│       └── predict_invoice_flag.py
│
├── models/
│   ├── predict_freight_model.pkl
│   └── predict_flag_invoice.pkl
│
├── notebooks/
│   ├── Invoice Flagging.ipynb
│   └── Predict Freight Cost.ipynb
│
├── app.py
├── README.md
├── requirements.txt
└── .gitignore
```

---

<a id="how-to-run-this-project"></a>

## ⚙️ How to Run This Project

### 1. Clone the Repository

```bash
git clone https://github.com/samyakmda/invoice_intelligence_machine_learning.git
```

### 2. Navigate to the Project Directory

```bash
cd invoice_intelligence_machine_learning
```

### 3. Install Required Dependencies

```bash
pip install -r requirements.txt
```

### 4. Train the Models

Train the freight cost prediction model:

```bash
python freight_cost_prediction/train.py
```

Train the invoice risk classification model:

```bash
python invoice_flagging/train.py
```

### 5. Test the Models

Test freight cost prediction:

```bash
python freight_cost_prediction/predict_freight.py
```

Test invoice risk prediction:

```bash
python invoice_flagging/inference/predict_invoice_flag.py
```

### 6. Run the Streamlit Application

```bash
streamlit run app.py
```

The application will open in your browser.

---

<a id="author--contact"></a>

## 👤 Author & Contact

**Samyak Meshram**
**Data Analyst**

✉️ Email: [samyakmda@gmail.com](mailto:samyakmda@gmail.com)

🔗 LinkedIn: https://linkedin.com/in/samyakmda

💻 GitHub: https://github.com/samyakmda

📁 Portfolio: Add your portfolio link here

🔗 [LinkedIn](https://www.linkedin.com/in/samyakmda/)  
🔗 [Portfolio](https://samyakmda.github.io/)
