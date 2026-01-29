# 🧠 Employee Retention Analysis  
## An Unsupervised Learning Approach to HR Analytics

## 📑 Table of Contents
1. [Introduction](##introduction)
2. [Project Background & Motivation](#project-background--motivation)
3. [Business Problem Statement](#business-problem-statement)
4. [Analytical Objectives](##analytical-objectives)
5. [Dataset Description](#dataset-description)
6. [Tools, Libraries & Technologies](#tools-libraries--technologies)
7. [Project Workflow](#project-workflow)
   - Exploratory Data Analysis
   - Feature Engineering
   - K-Means Clustering
   - PCA Visualization
8. [Key Insights & Risk Profiles](#key-insights--risk-profiles)
9. [Business Recommendations](#business-recommendations)
10. [Evaluation & Validation Approach](#evaluation--validation-approach)
11. [Limitations & Assumptions](#limitations--assumptions)
12. [Future Improvements](#future-improvements)

---

## 📌 Introduction

This repository contains a comprehensive **HR analytics data science project** focused on understanding **employee retention and attrition patterns** using **unsupervised machine learning techniques**.

Rather than relying solely on binary *“stay vs. leave”* predictions, this project emphasizes **employee profiling and segmentation** to uncover *why* employees leave and *which groups* are most at risk. By leveraging clustering and dimensionality reduction, the analysis identifies distinct employee segments and translates findings into **actionable, data-driven retention strategies**.

---

## 💡 Project Background & Motivation

Employee attrition is a complex phenomenon influenced by a combination of demographic, professional, and psychological factors. In many organizations:

- Attrition labels are limited or incomplete
- Root causes of turnover are poorly understood
- Traditional predictive models lack interpretability

This project adopts an **unsupervised learning approach** to move beyond surface-level predictions and instead **discover hidden workforce patterns** that drive retention outcomes.

The analysis is framed from the perspective of a **Data Scientist supporting an HR Analytics team** tasked with improving workforce stability and engagement.

---

## 🎯 Business Problem Statement

The organization faces a persistent employee attrition challenge but lacks clarity on:
- Which employees share similar risk characteristics
- What underlying factors contribute to disengagement
- How to design targeted, cost-effective retention initiatives

Because attrition drivers are not always explicit or labeled, **unsupervised machine learning** provides an effective framework for exploratory analysis and insight discovery.

---

## 🧭 Analytical Objectives

The primary objectives of this project are to:

- Segment employees into meaningful, data-driven groups
- Identify high-risk employee profiles associated with attrition
- Visualize high-dimensional HR data for interpretability
- Validate discovered clusters against attrition outcomes
- Translate technical findings into business-ready recommendations

---

## 📊 Dataset Description

The analysis is performed on **`employee_data.csv`**, containing **1,470 employee records**. Each record includes:

### 🔹 Demographics
- Age  
- Gender  
- Distance from Home  

### 🔹 Professional Information
- Job Level  
- Department (e.g., R&D, Sales)  
- Monthly Income  

### 🔹 Sentiment & Performance
- Job Satisfaction  
- Performance Rating  

### 🔹 Target Variable
- **Attrition** (used only for *post-clustering validation*, not model training)

All records are structured at the **employee level**, ensuring correct row granularity for modeling.

---

## 🧰 Tools, Libraries & Technologies

- **Python**
- **Jupyter Notebook**

### Core Libraries
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn`

### Techniques Applied
- K-Means Clustering
- Principal Component Analysis (PCA)
- Feature Scaling & Encoding
- Cluster Validation Metrics

---

## 🔄 Project Workflow

### 1️⃣ Exploratory Data Analysis (EDA)

Before modeling, an exploratory analysis was conducted to establish a baseline understanding of the workforce.

Key findings:
- Overall attrition rate: **16.1%**
- Strong initial relationships observed between attrition and:
  - Age
  - Job Level
  - Distance from Home

These insights guided feature selection and modeling decisions.

---

### 2️⃣ Feature Engineering

Unsupervised models require clean, numeric input. The following transformations were applied:

- **Binary Encoding**  
  - Converted `Gender` and `Attrition` into numeric format (0/1)

- **One-Hot Encoding**  
  - Transformed categorical departments into dummy variables

- **Feature Selection**  
  - Focused on variables with high variance and strong business relevance

- **Scaling**  
  - Standardized features to ensure distance-based models performed correctly

---

### 3️⃣ K-Means Clustering

K-Means was applied iteratively to segment employees into distinct groups.

- **Round 1:** Initial clustering to identify natural groupings  
- **Round 2:** Feature refinement to improve cluster separation and silhouette scores  

Cluster centroids were analyzed to interpret employee profiles and behavioral patterns.
<Figure size 640x480 with 1 Axes><img width="576" height="453" alt="image" src="https://github.com/user-attachments/assets/f96522ec-9e2d-41d1-b771-4ce411135bec" />


---

### 4️⃣ PCA for Visualization

High-dimensional HR data is difficult to visualize directly.  
**Principal Component Analysis (PCA)** was used to:

- Reduce the dataset to two dimensions
- Preserve the majority of variance
- Visually validate cluster separation

The PCA plot confirmed that the final clusters were **well-separated and interpretable**.
<Figure size 640x480 with 1 Axes><img width="567" height="432" alt="image" src="https://github.com/user-attachments/assets/e46ca0bb-bdd4-4fcf-b31a-117d3cc8456d" />


---

## 🔍 Key Insights & Risk Profiles

Analysis of cluster characteristics revealed **three major employee risk profiles**:

### 🚗 The Commuters
- Employees living far from the workplace
- High attrition regardless of compensation
- Indicates commute burden as a dominant factor

### 😕 The Disengaged
- Predominantly male employees
- Low job satisfaction scores
- Moderate performance but high turnover risk

### 🚀 High-Potential Flight Risks
- Strong performance ratings
- Mid-level roles with limited advancement
- Likely experiencing career stagnation

### ✅ High-Retention Groups
- Senior management
- Female employees  
This suggests organizational structures or cultural elements that positively support these groups.

---

## 💼 Business Recommendations

| Segment | Recommended Strategy |
|------|----------------|
| Long Commuters | Introduce remote-first or hybrid work policies |
| Low Satisfaction Men | Conduct targeted 1-on-1 manager interventions |
| High Performers | Establish fast-track promotions and leadership programs |
| Low Attrition Groups | Identify and replicate successful cultural practices |

---

## 📈 Evaluation & Validation Approach

Although clustering is unsupervised:
- Silhouette scores and PCA plots were used for internal validation
- Attrition labels were used **post hoc** to assess cluster relevance
- Interpretability and business logic guided final conclusions

---

## ⚠️ Limitations & Assumptions

- Results depend on feature selection and scaling
- Attrition is influenced by external factors not captured in the data
- Clusters describe tendencies, not certainties

---

## 🚀 Future Improvements

- Incorporate time-series employee behavior
- Extend analysis to include engagement surveys
- Build interactive dashboards
- Integrate findings into HR decision systems

