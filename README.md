# 💼 Job Market Dashboard – Streamlit App

This is a **Streamlit-based dashboard** that visualizes real-time job market data including roles, companies, locations, contract types, salary ranges, and required skills. It pulls structured data from a **PostgreSQL database hosted on [Neon](https://neon.tech/)**.

🔗 **Live App**: [Click here to view the dashboard](https://jobmarketuk.streamlit.app/)

---

## 🚀 Features

- Interactive filtering of job listings by date
- Salary distribution and comparison using Plotly visualizations  
- Extracted skill keywords from job descriptions  
- Clean and responsive layout using Streamlit components

---

## 🗂️ Tech Stack

| Component       | Technology                    |
|----------------|-------------------------------|
| Frontend        | [Streamlit](https://streamlit.io/)             |
| Backend         | [PostgreSQL (Neon)](https://neon.tech/)        |
| Data Source     | [Adzuna Job API](https://developer.adzuna.com/)|
| ETL & Automation| [Apache Airflow (Docker)](https://airflow.apache.org/) |
| Deployment      | [Streamlit Cloud](https://streamlit.io/cloud)  |

---

## 🛠️ Setup Instructions (for local run)

1. **Clone the repo**  
   ```bash
   git clone https://github.com/najeeb_ur_rahaman/job_market_streamlit.git
   cd job_market_streamlit
   ````

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```
   
3. **Set up database credentials (local)**
   Create a .env file in your project 
   ```env
   DB_URL = "postgresql+psycopg2://<user>:<password>@<your-neon-host>/<db>?sslmode=require"
   ```
    
    > 🔒 **Never commit your `.env` file to GitHub.**
   
5. **Configure database credentials (Streamlit Cloud only)**  
   If you're deploying this app to [Streamlit Cloud](https://streamlit.io/cloud):

   - Go to **Advanced Settings** during app creation (or via Settings → Secrets later)
   - Add the following environment variable:
     ```
     DB_URL = "postgresql+psycopg2://<user>:<password>@<your-neon-host>/<db>?sslmode=require"
     ```

   The app uses this environment variable internally to establish a database connection.


6. **Run the app**

   ```bash
   streamlit run dashboard.py
   ```

---

## 🌐 Full Project with ETL and Airflow

The complete pipeline that extracts job data from the Adzuna API, processes it, and loads it into PostgreSQL (Neon), is available here:

👉 **GitHub (Full Project)**:
[https://github.com/najeeb-ur-rahaman/job\_market\_dashboard](https://github.com/najeeb-ur-rahaman/job_market_dashboard)

This includes:

* Dockerized Apache Airflow setup
* ETL DAG to extract & transform job data
* Database schema setup
* Pipeline orchestration

---

## 🙌 Acknowledgements

* [Adzuna](https://www.adzuna.com/) for the Job API
* [Neon](https://neon.tech/) for serverless PostgreSQL
* [Streamlit](https://streamlit.io/) for making data apps effortless
