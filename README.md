# Machine-Learning-Project

## 📂 Dataset Description

The dataset used in this project is **`dbt-district-wise`**, containing **3,825 records** across **8 columns**, representing **Direct Benefit Transfer (DBT)** data for Indian districts between **2019–20 and 2023–24**.

### 🧾 Columns Overview
| Column | Description |
|--------|--------------|
| `id` | Unique identifier for each record |
| `fy` | Financial year (e.g., 2019–2020) |
| `state_name` | Name of the Indian state |
| `state_code` | Numeric state code |
| `district_name` | Name of the district |
| `district_code` | Numeric district code |
| `total_dbt_transfer` | Total DBT amount transferred (in INR) |
| `no_of_dbt_transactions` | Total number of DBT transactions in that period |

### 🧹 Data Cleaning and Preprocessing
To ensure data quality and consistency, the following preprocessing steps were applied:
- Removed missing and duplicate records.  
- Standardized column names to lowercase with underscores.  
- Converted numeric columns (`total_dbt_transfer`, `no_of_dbt_transactions`) to float.  
- Transformed categorical columns (e.g., `fy`) into string format.  
- Verified a clean dataset of **3,704 usable entries** ready for visualization and modeling.

---

## 📊 Exploratory Data Analysis (EDA)

The project analyzes DBT distribution across India using descriptive statistics and visualizations.  
Key analyses include:
- Yearly trend of **total DBT transfers** and **number of transactions** (2019–20 → 2023–24).  
- Top 10 **states and districts** by total transfer and transaction count.  
- Distribution plots of transfer values and transaction frequencies.  
- Year-over-year (YoY) growth analysis to identify major surges or declines.  
- Simple Linear Regression between **transactions and total transfers (R² = 0.63)**.

---

## 🤖 Machine Learning Models

### 1. **Regression**
- **Simple Linear Regression:** Explored the relationship between total transactions and total transfers.
- Found a **positive correlation** — more transactions correspond to higher total transfer amounts.

### 2. **Classification**
- **Logistic Regression** and **Decision Tree** models were built to classify districts into *High* and *Low* DBT categories.
- Achieved **~90% accuracy** on test data.
- Confusion matrices, precision, recall, and F1 scores were used for evaluation.

### 3. **Clustering**
- Applied **K-Means (K=3)** on total transfers and transactions to group districts into:
  - Low activity  
  - Medium activity  
  - High activity clusters  

---

## 🧠 Natural Language Processing (NLP) on District & State Names

Even though the dataset is primarily numeric, NLP techniques were applied to extract insights from **text columns** (`state_name`, `district_name`).

### NLP Tasks Performed
1. **Text Cleaning:**  
   - Lowercased all names, removed special characters and extra spaces.

2. **Word Frequency Analysis:**  
   - Extracted the most common words (e.g., *nagar*, *garh*, *pur*) to study regional naming patterns.

3. **Word Cloud Visualization:**  
   - Generated a word cloud of all district names to visually highlight common suffixes and prefixes.

4. **Text Similarity (TF-IDF + Cosine Similarity):**  
   - Identified districts with similar names, e.g., *North 24 Parganas* ↔ *South 24 Parganas*.

5. **Text Clustering (K-Means on TF-IDF):**  
   - Grouped districts into clusters based on textual similarity.

6. **Pattern Analysis:**  
   - Found that districts ending with words like “**nagar**”, “**pur**”, and “**garh**” often show similar naming conventions.
   - Combined NLP outputs with numeric DBT data (e.g., comparing average transfer amounts for districts ending with “nagar”).

### Example NLP Insights
- The word **“Nagar”** appears most frequently in district names across India.  
- Districts with similar linguistic patterns often share geographic or cultural proximity.  
- Text-based clustering complements numeric data by revealing **naming trends** across Indian regions.

---

## 📈 Key Findings

- **Uttar Pradesh, Bihar, and Maharashtra** record the highest DBT transaction volumes.  
- DBT transfers peaked during **2020–21** (pandemic period) with over **1200% growth**.  
- Both **Logistic Regression** and **Decision Tree** achieved ~90% accuracy for classification.  
- **NLP analysis** added a linguistic dimension — showing regional naming similarities and their relationship to DBT patterns.

---

## ⚙️ Tools and Libraries Used

| Category | Libraries |
|-----------|------------|
| Data Handling | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `plotly`, `wordcloud` |
| Machine Learning | `scikit-learn` |
| NLP | `re`, `TfidfVectorizer`, `WordCloud`, `Counter` |
| Environment | Jupyter Notebook, Python 3.x |

---

## 🏁 Conclusion

This project demonstrates how **data science and NLP** can be combined to understand large-scale government initiatives like DBT.  
By integrating numerical analysis, classification models, clustering, and NLP-based text insights, the study provides a holistic understanding of how DBT transactions vary across states and districts in India.

**Result:** A comprehensive data-driven perspective on India’s Direct Benefit Transfer system — enhancing transparency, accountability, and regional insight.

---
