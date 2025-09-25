# Bureau of Indian Standards – Compliance Prediction & Dashboarding  

## 📌 Project Overview  
This project integrates **data engineering**, **SQL analytics**, **machine learning**, and **Power BI dashboards** to analyze and predict compliance of industrial components with Bureau of Indian Standards (BIS).  

The workflow covers the entire data lifecycle:  
1. **Data Cleaning & Preparation (SQL + Python)**  
2. **Exploratory Data Analysis (EDA)**  
3. **Feature Engineering**  
4. **Machine Learning Model (Random Forest Classifier)**  
5. **Interactive Dashboard in Power BI**  

The goal is to provide decision-makers with **real-time insights** into compliance trends across plants, suppliers, and standards — and to use predictive modeling for proactive risk management.  

---

## 📂 Repository Contents  
- **`Bureau_of_indian_standards_prapti108.pbix`** → Power BI dashboard for compliance monitoring and analysis.  
- **`MYSQL_BIS`** → SQL queries for data cleaning, feature engineering, and supplier-level analysis.  
- **`Untitled140.ipynb`** → Jupyter Notebook implementing machine learning pipeline (Random Forest).  
- **`industrial_components_dashboard_v2.xlsx`** → Source dataset (industrial components with compliance details).  
- **`README.md`** → Project documentation (you’re reading it now 🚀).  
- **`LICENSE`** → Open-source license (Apache-2.0).  

---

## ⚙️ Data Workflow  

### 1. **Data Source**  
- Data collected from **3 industrial plants**.  
- Dataset includes component details, suppliers, purchase dates, compliance status, and standard applicability.  

### 2. **SQL Queries (Data Cleaning & Feature Engineering)**  
Key SQL tasks:  
- Standardize compliance status labels.  
- Extract purchase year, month, and component age.  
- Create binary flags (e.g., `std_applicable_flag`, `has_standard_number`).  
- Compute supplier-level compliance statistics.  
- Final dataset exported for ML training.  

📄 See: `MYSQL_BIS`  

### 3. **Machine Learning Pipeline**  
- **Library:** scikit-learn  
- **Model:** Random Forest Classifier  
- **Pipeline Design:**  
  - Numeric preprocessing → imputation + scaling  
  - Categorical preprocessing → imputation + one-hot encoding  
  - Combined with `ColumnTransformer`  
- **Metrics Used:** Accuracy, ROC-AUC, Classification Report, Confusion Matrix  
- **Feature Importances:** Identified supplier compliance rate, component age, and applicability flags as top predictors.  
- **Deployment:** Model saved using `joblib` and predictions exported as CSV.  

📄 See: `Untitled140.ipynb`  

### 4. **Power BI Dashboard**  
- Built using the cleaned dataset.  
- Features:  
  - Compliance distribution by plant  
  - Supplier-wise compliance trends  
  - Standard applicability breakdown  
  - Predictive compliance insights (via ML outputs)  
- Designed for decision-makers to quickly identify non-compliance risks and supplier performance issues.  

📄 See: `Bureau_of_indian_standards_prapti108.pbix`  

---

## 📊 Key Insights  
- Supplier compliance rates vary significantly → strong predictor of future compliance.  
- Component age and purchase month reveal seasonal/non-seasonal compliance patterns.  
- Plants differ in compliance distribution, allowing targeted interventions.  
- Standards applicability strongly impacts compliance probability.  

---

## 🚀 How to Run  

### 🔹 SQL  
1. Load `industrial_components_dashboard_v2.xlsx` into a MySQL database (`Components` table).  
2. Run queries from `MYSQL_BIS` to generate the **final dataset**.  

### 🔹 Machine Learning  
```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn joblib openpyxl
```
Run the notebook:  
```bash
jupyter notebook Untitled140.ipynb
```

### 🔹 Power BI  
1. Open `Bureau_of_indian_standards_prapti108.pbix`.  
2. Connect to the processed dataset.  
3. Explore dashboards interactively.  

---

## 🛠️ Tech Stack  
- **SQL (MySQL)** → Data cleaning, feature engineering, supplier stats  
- **Python (pandas, scikit-learn, seaborn, matplotlib)** → ML pipeline + visualization  
- **Power BI** → Interactive dashboards  
- **Excel** → Initial data source  

---

## 📌 Future Enhancements  
- Integrate **real-time supplier data streams** into dashboards.  
- Deploy ML model as an API for **live compliance prediction**.  
- Automate ETL pipeline (SQL → Python → Power BI).  
- Add anomaly detection for fraud / misreporting.  

---

## 🤝 Contributing  
Pull requests are welcome! For major changes, please open an issue first to discuss.  

---

## 📢 Connect  
👩‍💻 **Author:** Prapti Mishra  

📌 If you found this project helpful, **don’t forget to star ⭐ this repository!**  

---

✨ *Made with dedication by Prapti Mishra* ✨  
