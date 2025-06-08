# 🫀 Framingham Heart Study: Data Governance & Privacy-Preserving Techniques

This project presents a **comprehensive data management and privacy framework** using the Framingham Heart Study dataset. It demonstrates best practices in **data profiling, cleaning, validation, privacy, and security**—essential for responsibly handling sensitive health data in real-world applications.

---

## 📌 Project Highlights

* **Dataset Profiling** with `dataprofiler` and traditional descriptive statistics
* **Data Cleaning** including imputation and encoding
* **Data Validation** using `pandera` and `great_expectations`
* **Privacy-Preserving Techniques** such as generalization, masking, perturbation, hashing, encryption, and synthetic data generation
* **Access Control Implementation** (RBAC & ABAC)

---

## 🧠 Key Features

### 🧪 Phase 0: Data Profiling

* **Automated Profiling:** Generates detailed statistics using `dataprofiler`
* **Manual Summary:** Provides `.describe()`, `.info()`, `.isnull().sum()`, and `dtypes`

---

### 🧹 Phase 1–2: Data Cleaning, Validation, and Privacy

#### 🧼 Data Cleaning

* **Duplicates Detection**
* **Missing Value Imputation**

  * Mean for numeric columns
  * Mode for categorical columns
* **Encoding**

  * Label Encoding (e.g., `male`, `education`, etc.)
  * One-Hot Encoding (e.g., `currentSmoker`, `cigsPerDay`)

#### ✅ Data Validation

* **Schema Definition with `pandera`**
* **Lazy Validation Mode for Error Reporting**
* **Automated Schema Inference**
* **Expectations with `great_expectations`**

  * Null checks
  * Value ranges (e.g., `age` between 32–70)
  * Uniqueness checks
  * Checkpoint creation and validation

---

### 🔐 Data Privacy & Security

#### 🔒 Privacy Techniques

* **Generalization:** Bucketing values for columns like `age` and `glucose`
* **Masking:** Replacing sensitive values (`totChol`, `sysBP`, etc.) with fake data
* **Perturbation:** Adding noise to `glucose` for privacy
* **Aggregation:** Summary stats grouped by features (e.g., `currentSmoker`)
* **Suppression:** Removing unnecessary sensitive fields
* **Swapping:** Shuffling sensitive data between records
* **Nulling:** Replacing sensitive values with nulls or blanks
* **Synthetic Data Generation:** Using `faker` to mimic data structure without using real values
* **Hashing:** SHA256 applied to columns for pseudonymization
* **Encryption:** Column-wise encryption using `cryptography.fernet`

#### 🧾 Access Control

* **RBAC (Role-Based Access Control):** Defines user roles with CRUD permissions
* **ABAC (Attribute-Based Access Control):** Granular access decisions based on attributes using `py_abac`

---

## 🩺 Dataset Info

* **Dataset Name**: Framingham Heart Study
* **File Format**: CSV (e.g., `framingham.csv`)
* **Description**: Contains cardiovascular risk factors for predicting 10-year risk of coronary heart disease (CHD)

---

## 🛠 Technologies Used

* **Python 3.x**
* `pandas`, `numpy`, `matplotlib`
* `dataprofiler` – for automated data profiling
* `scikit-learn` – for encoding
* `pandera` – for schema-based validation
* `great_expectations` – for automated data quality checks
* `faker` – for synthetic data generation
* `anonymizedf` – for data masking
* `hashlib` – for hashing
* `cryptography` – for column encryption
* `py_abac` – for ABAC enforcement

---

## ▶️ How to Run

1. **Install Dependencies:**

```bash
pip install pandas numpy matplotlib dataprofiler pandera[io] great_expectations faker anonymizedf cryptography py_abac
```

2. **Place the dataset** (`framingham.csv`) in the project directory (or update the file path in the code).

3. **Open and Run the Jupyter Notebook**:

   * Download the project notebook
   * Use Jupyter Notebook or JupyterLab
   * Run all cells in order

