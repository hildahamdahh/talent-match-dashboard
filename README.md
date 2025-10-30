# Talent Match Intelligence

**Talent Match Intelligence** is an analytics system that integrates employee performance, competency, and psychometric data to identify success patterns and benchmark top performers.

---

## 📁 Repository Contents

This repository contains all main source files used to build the **Talent Match Intelligence** dashboard and database functions.

| File | Description |
|------|--------------|
| `app.py` | Streamlit dashboard for visualization and analysis |
| `talentmatch_r5_fix` | Final PostgreSQL function used in Supabase |
| `join_allemployees_sql` | SQL script to join employee datasets |
| `employee_tv_scores.csv` | Employee-level Talent Variable data |
| `talent_benchmark.csv` | Benchmark data for top performers for app.py streamlit (input) |
| `requirements.txt` | Python dependencies for running the app |

---

## ⚙️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/talent-match-intelligence.git
cd talent-match-intelligence```

### 2. Create a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate   # For Mac/Linux
venv\Scripts\activate      # For Windows```

### 3. Install Dependencies
pip install -r requirements.txt

### 4. Run the Streamlit App
streamlit run app.py

### 5. Database Setup (PostgreSQL / Supabase)
Upload all SQL scripts (join_allemployees_sql, talentmatch_r5_fix, etc.) into your database.
Ensure function talentmatch_r5_fix is deployed successfully in Supabase.
Configure your database URL and API key in the app (inside app.py).

**Data Analysis (Google Colab)**
All exploratory data analysis and visualization of Top Performer insights are conducted in a Google Colab notebook.
The notebook includes:
Descriptive statistics
Correlation and psychometric pattern analysis
Visualization of competency and strength distributions

https://colab.research.google.com/drive/1NIGg7siSDvvSVOYVIgdRXuJN8YgSQ91E#scrollTo=BgmyDprn1L3d

Author
Developed by [Hilda Hamdah Husniyyah]
