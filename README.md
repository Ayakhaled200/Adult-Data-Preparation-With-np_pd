# **Data Preparation using Pandas & Machine Learning Model Training**

## **Project Overview**
This project focuses on **data preprocessing and model training** using the **Adult Income dataset**. The dataset undergoes multiple **data cleaning, transformation, and feature engineering** steps to enhance machine learning model performance. A simple model is trained and evaluated using the **F1-score**, with further iteration to analyze how modifications in preprocessing affect model outcomes.

---

## **Preprocessing Steps**
### **1️⃣ Data Cleaning & Preprocessing**
- **Dropping Useless Columns**: Removed non-contributory columns to avoid noise.
- **Handling Missing Values**: Detected and replaced missing data.
- **Dropping Duplicates**: Ensured dataset integrity by removing duplicate entries.

### **2️⃣ Data Splitting**
- **Train-Test Split (80-20)**: Split dataset before encoding and feature scaling.

### **3️⃣ Encoding Categorical Features**
- **One-Hot Encoding**: Applied to columns with 2–7 unique categories.
- **Target Encoding**: Used for categorical columns with **high cardinality** to prevent dimensionality issues.

### **4️⃣ Handling Outliers**
- **Z-Score Method**: Retained most of the data while removing extreme outliers.
- **IQR Method** (Experimented with): Identified more outliers but led to slight accuracy drop.

### **5️⃣ Feature Scaling**
- **Standardization (Z-score scaling)**: Applied as it works best with linear models and reduces bias from large-value features.

### **6️⃣ Feature Engineering**
- **Feature Removal**: Removed correlated or low-impact features (`education`, `fnlwgt`, `workclass_State-gov`, `workclass_Without-pay`).
- **Feature Combining**: Created `net_capital = capital-gain - capital-loss`, which **improved model performance**.

---

## **Model Training & Evaluation**
- **Models Used:**  
  - **Logistic Regression**
  - **Support Vector Machine (SVM)**  

- **Initial F1 Scores:**
  - **Logistic Regression**: `0.63`
  - **SVM**: `62.7`

- **Final Optimized Scores:**
  - **Logistic Regression**: `0.633`
  - **SVM**: `62.4`

---

## **Experimentation & Impact on Model Performance**
| **Preprocessing Change**                     | **Logistic F1-Score** | **SVM F1-Score** |
|----------------------------------------------|----------------------|------------------|
| **Without Feature Scaling**                   | `0.616`              | `0.55`           |
| **Without Outlier Handling**                  | `0.623`              | `0.621`          |
| **Using IQR for Outlier Handling**            | `0.63`               | `0.61`           |
| **Using Normalization Instead of Standardization** | `0.61`               | `0.599`          |
| **Not Dropping `capital-gain` & `capital-loss`** | `0.674`              | `0.664`          |
| **Combining `capital-gain` & `capital-loss` (`net_capital`)** | `0.63`  | `0.665` |

- **Key Takeaways:**
  - Keeping `capital-gain` & `capital-loss` **boosted accuracy**.
  - Feature scaling and outlier handling had a **significant impact** on performance.
  - Standardization worked **better than normalization** for this dataset.

---

## **Project Files**
- 📊 **`Adult`** – Dataset used for preprocessing and model evaluation.
- 📄 **`Data_Preparation_Report.docx`** – Detailed report on preprocessing techniques, experiments, and results.
- 📝 **`Adult_income.ipynb`** – Jupyter Notebook with code for preprocessing and model training.

