# Enterprise Data Pipeline Hub: Predictive Analytics Suite

Welcome to the **Enterprise Data Pipeline Hub**, a centralized portfolio showcasing production-grade, end-to-end data engineering, machine learning, and business intelligence solutions across two industry domains: **Telecommunications** and **Healthcare**.

These projects demonstrate complete analytics pipelines—from raw data ingestion and database modeling to predictive machine learning and interactive dashboards—designed to support real-world business decision-making and operational automation.

---

# 📂 Repository Structure

## 📂 Repository Structure

```text
Enterprise-Data-Pipeline-Hub/
│
├── Healthcare Appointment No-Show Prediction/
│   ├── Dashboard/                 # Power BI Dashboard (.pbix)
│   ├── Healthcare Appointment No-Show data/   # Dataset
│   ├── Images/                    # Dashboard screenshots
│   ├── Python Notebook/           # Data preprocessing & Decision Tree model
│   └── Report/                    # Project report
│
└── telecom-customer-churn-analytics/
    ├── Data/                      # Raw dataset
    ├── Images/                    # Project screenshots
    ├── Python Notebook/           # Data preprocessing & Random Forest model
    ├── Report/                    # Project report
    └── SQL File/                  # Staging tables & Star Schema scripts
```

---

# 📊 Project 1: Telecom Subscriber Churn Prediction Pipeline

## 📌 Overview

Customer retention is significantly more cost-effective than acquiring new subscribers. This project builds a production-ready churn prediction pipeline capable of identifying high-risk customers before cancellation, enabling proactive retention strategies through automated workflows.

The solution integrates data warehousing, machine learning, and explainable AI into a complete analytical pipeline.

## 🛠️ Technology Stack

* MySQL (Staging Architecture & Star Schema)
* Python
* Pandas
* NumPy
* Scikit-Learn
* Random Forest Classifier
* ELI5 Explainability

## 🚀 Pipeline Architecture

### Data Warehouse

* Imported raw CSV exports into a staging database.
* Designed a Star Schema consisting of:

  * Customer Dimension
  * Customer Usage Fact Table
* Reduced schema drift through staged data validation.

### Customer Segmentation

Business rules were implemented directly inside MySQL for fast weekly batch processing.

* **At-Risk Customers**

  * Customer Service Calls ≥ 3
  * OR Total Day Minutes > 280

* **Loyal Customers**

  * Account Length > 120 Months
  * Zero historical churn

### Machine Learning

* Removed high-cardinality categorical variables.
* Addressed multicollinearity using Random Forest.
* Stratified 80/20 train-test split.
* Trained a Random Forest model with **100 estimators**.

### Explainability & Automation

ELI5 feature importance identified:

* Customer Service Calls
* Daytime Usage

as the strongest churn indicators.

The pipeline automatically triggers a retention webhook whenever a customer exceeds **3 support calls within 60 days**, allowing immediate intervention.

## 📈 Model Performance

| Metric    | Score     |
| --------- | --------- |
| Accuracy  | **94.5%** |
| Precision | **0.92**  |
| Recall    | **0.63**  |
| F1 Score  | **0.75**  |

---

# 🏥 Project 2: Healthcare Appointment No-Show Prediction & BI Suite

## 📌 Overview

Missed medical appointments create operational inefficiencies and increase healthcare costs. This project combines predictive machine learning with a custom-built Power BI dashboard to identify patients at high risk of missing appointments before they occur.

The solution enables healthcare administrators to improve scheduling efficiency through proactive interventions.

## 🛠️ Technology Stack

* Python
* Pandas
* NumPy
* Scikit-Learn
* Decision Tree Classifier
* Power BI Desktop

## 🚀 Pipeline Architecture

### Data Preparation

* Processed over **110,000 appointment records**.
* Removed invalid age values.
* Standardized inconsistent medical condition labels.
* Cleaned duplicate categorical entries.

### Feature Engineering

Created the **AwaitingDays** feature by calculating the duration between appointment booking and appointment date.

Within Power BI:

* Disabled summarization for PatientID and AppointmentID.
* Preserved row-level auditing integrity.

### Machine Learning

* Stratified 80/20 train-test split.
* Decision Tree with **max_depth = 5**
* Balanced class weights to handle class imbalance.
* Optimized for interpretability while minimizing overfitting.

### Interactive Power BI Dashboard

Developed a fully customized **Glassmorphism** dashboard featuring:

* Dark theme interface
* Floating translucent cards
* Interactive slicers
* KPI cards
* High-risk patient monitoring
* Weekday appointment analysis
* Conditional alert indicators

Feature importance revealed:

* **AwaitingDays — 87.29%**
* **Age — 10.58%**

indicating appointment lead time as the strongest predictor of patient absenteeism.

## 📈 Model Performance

| Metric         | Score      |
| -------------- | ---------- |
| Accuracy       | **58.54%** |
| No-Show Recall | **0.81**   |

The model successfully identifies more than **4 out of every 5** patients who are likely to miss their appointments, making it well suited for proactive scheduling interventions.

---

# ⚡ Operational Impact

Both projects demonstrate how predictive analytics can drive measurable business outcomes.

### Telecom Pipeline

* Automated customer retention alerts
* Explainable AI for churn drivers
* Star Schema data warehouse
* Production-ready predictive pipeline

### Healthcare Pipeline

* Early identification of high-risk appointments
* Lead-time optimization strategies
* Dynamic overbooking recommendations
* Interactive executive dashboard for operational monitoring

---

# 🎯 Key Skills Demonstrated

* Data Engineering
* SQL Data Warehousing
* Star Schema Design
* ETL Pipelines
* Feature Engineering
* Machine Learning
* Explainable AI (ELI5)
* Model Evaluation
* Business Intelligence
* Power BI Dashboard Development
* Predictive Analytics
* Data Visualization
* Production-Oriented Analytics Solutions
