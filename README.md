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
| `requirements.txt` | Python dependencies for running the app |

---

## ⚙️ Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/hildahamdahh/talent-match-dashboard/tree/main
cd talent-match-intelligence
```

### 2. Deploy on Streamlit Cloud
a. Go to Streamlit Cloud (https://share.streamlit.io/).    
b. Click “New app”.  
c. Connect your GitHub account and select the repository talent-match-intelligence.  
d. Choose the main branch (usually main) and set the entry point file to:
```bash
app.py
```
e. Click Deploy  
Streamlit Cloud will automatically:  
Install all dependencies listed in requirements.txt.  
Launch your app online.  

### 3. Database Configuration (PostgreSQL / Supabase)
Copy paste the talentmatch_r5_fix script to your SQL Editor.  
This function is the core logic used by the dashboard to calculate Talent Match scores.  
Make sure the function talentmatch_r5_fix is successfully deployed and running in Supabase.  
**⚙️ Required Tables**  
You must upload the following two tables to Supabase:  
1. employee_tv_scores → Contains all employee records, including both benchmark (top performers) and non-benchmark employees.  
You must also upload a duplicate of this table named all_employee. The employee_tv_scores table is primarily used for benchmark selection, while all_employee serves as the comparison dataset during the scoring process.  
2. tv_tgv → Upload the file “Talent Variables (TV) and Talent Group Variables (TGV)” and rename the table to tv_tgv in Supabase.  
The tv_tgv table is used by the talentmatch_r5_fix function to read and apply custom TGV weights when users adjust weightings in the Streamlit app.  
**⚙️ Supabase Configuration**
Configure your Supabase credentials inside app.py:  
```python
url = "https://your-supabase-url.supabase.co"
key = "your-supabase-api-key"
supabase = create_client(url, key)
``` 

### 4. AI Integration (OpenRouter)
The dashboard uses OpenRouter API to generate AI-powered insights and explanations.  
To enable this feature:  
a. Create an account on (https://openrouter.ai/)  
b. Generate an API key from your profile settings.  
c. In Streamlit Cloud, go to App Settings → Secrets, and add:  
```
OPENROUTER_API_KEY = "your-openrouter-api-key"
```
d. The app will automatically load this key using:
```python
client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key=st.secrets["OPENROUTER_API_KEY"]
)
```

### 5. (Optional) Run Locally
If you prefer to test the app on your local machine:
```bash
pip install -r requirements.txt
streamlit run app.py
```

**📁 Data Analysis (Google Colab)**
All exploratory data analysis and visualization of Top Performer insights are conducted in a Google Colab notebook.
The notebook includes:
Descriptive statistics
Correlation and psychometric pattern analysis
Visualization of competency and strength distributions

https://colab.research.google.com/drive/1NIGg7siSDvvSVOYVIgdRXuJN8YgSQ91E#scrollTo=BgmyDprn1L3d

Author
Developed by [Hilda Hamdah Husniyyah]
