# 🏥 SMARTQUEUE — AI-Based Patient Flow Optimization

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Django-5.x-green?style=for-the-badge&logo=django&logoColor=white"/>
  <img src="https://img.shields.io/badge/AI%2FML-Powered-orange?style=for-the-badge&logo=tensorflow&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-In%20Development-yellow?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/License-MIT-purple?style=for-the-badge"/>
</p>

<p align="center">
  <b>A research-based minor project submitted to K.R Mangalam University</b><br/>
  Department of Computer Science and Engineering (AI & ML Specialization)<br/>
  <i>Supervised by Dr. Ravinder Beniwal | January 2026</i>
</p>

---

## 📌 About the Project

**SMARTQUEUE** is an AI-driven patient flow optimization framework designed to address the persistent problem of long waiting times, overcrowded hospital facilities, and uneven distribution of clinical workload in healthcare institutions.

Traditional queue management strategies like **First-Come-First-Serve (FCFS)** and static appointment scheduling lack the flexibility to respond to real-time changes. SMARTQUEUE replaces these with a proactive, data-driven system that:

- 📈 **Predicts** short-term patient arrivals using time-series forecasting
- ⏱️ **Estimates** consultation durations using ML regression
- 🔄 **Simulates** hospital queue dynamics using discrete-event simulation
- 🤖 **Optimizes** doctor scheduling dynamically using AI-based algorithms

---

## 🗂️ Project Structure

```
smartque/
├── manage.py                  # Django management utility
├── db.sqlite3                 # SQLite database
├── smartque/
│   ├── __init__.py
│   ├── settings.py            # Project settings
│   ├── urls.py                # Root URL configuration
│   ├── wsgi.py                # WSGI entry point
│   └── asgi.py                # ASGI entry point
├── dashboard/
│   ├── __init__.py
│   ├── admin.py               # Admin registration
│   ├── apps.py                # App config (DashboardConfig)
│   ├── models.py              # Database models
│   ├── views.py               # View functions (show/render index)
│   ├── urls.py                # Dashboard URL routes
│   └── tests.py               # Test cases
└── templates/
    └── index.html             # Main dashboard UI
```

---

## ⚙️ System Architecture

```
                    ┌─────────────────────┐
                    │  Public Queue Portal │ ◄── Patients view queue status
                    └────────┬────────────┘
                             │
              ┌──────────────▼──────────────┐
              │     SMARTQUEUE Core Modules  │
              └──────┬──────────────┬───────┘
                     │              │
           ┌─────────▼──┐    ┌──────▼──────────┐
           │ Prediction  │    │ Simulation Engine│
           │   Module    │    │  (Queue Dynamics) │
           └─────────┬──┘    └──────┬───────────┘
                     │              │
              ┌──────▼──────────────▼──────┐
              │     AI Scheduling Module    │
              └────────────┬───────────────┘
                           │
              ┌────────────▼───────────────┐
              │   Secure Dashboard Interface│
              └──────────┬────────┬────────┘
                         │        │
              ┌──────────▼─┐  ┌───▼──────┐
              │  Hospital   │  │ Doctors  │
              │   Admins    │  └──────────┘
              └─────────────┘
```

---

## 🔬 Methodology

The project follows a 6-phase development methodology:

| Phase | Description |
|-------|-------------|
| **Phase 1** | Data Collection & Preprocessing — temporal feature engineering, outlier removal |
| **Phase 2** | Patient Arrival Forecasting — LSTM-based time-series model for short-term inflow prediction |
| **Phase 3** | Consultation Time Estimation — ML regression models using triage level, patient type |
| **Phase 4** | Queue Simulation Modeling — Discrete-event simulation of arrivals, queues, and service |
| **Phase 5** | AI-Based Scheduling Optimization — Dynamic doctor assignment to minimize waiting time |
| **Phase 6** | System Evaluation — Benchmarking against FCFS and static scheduling baselines |

---

## 🛠️ Tech Stack

### Backend
- **Python 3.10+**
- **Django** — Web framework & routing

### Frontend
- **HTML5 / CSS3** — UI structure and styling
- **Tailwind CSS** — Dashboard design

### Data Science & ML
- **Pandas** — Data preprocessing
- **NumPy** — Numerical computations
- **Matplotlib / Seaborn** — Visualization
- **LSTM (Keras/TensorFlow)** — Time-series forecasting *(planned)*
- **Scikit-learn** — Regression & ML models *(planned)*

### Simulation
- **SimPy** — Discrete-event simulation *(planned)*

### Database
- **SQLite3** — Development database

---

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.10+
pip
virtualenv (recommended)
```

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/smartqueue.git
cd smartqueue

# 2. Create and activate virtual environment
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Apply migrations
python manage.py migrate

# 5. Run the development server
python manage.py runserver
```

---

## 📊 Key Features (Current & Planned)

- [x] Django web application scaffold
- [x] Dashboard UI with patient flow metrics
- [x] Routing setup (`dashboard` app)
- [ ] Patient arrival forecasting (LSTM model)
- [ ] Consultation duration estimation (ML regression)
- [ ] Discrete-event queue simulation
- [ ] AI scheduling optimization module
- [ ] Real-time dashboard with live queue updates
- [ ] Performance comparison reports (vs FCFS)

---

## 📈 Performance Metrics (Target)

| Metric | Traditional (FCFS) | SMARTQUEUE (Target) |
|--------|-------------------|----------------------|
| Avg. Waiting Time | ~35 mins | < 18 mins |
| Doctor Utilization | ~60% | > 85% |
| Queue Congestion | High | Significantly Reduced |

---

## 📚 References

1. Kim et al., *Prediction of hospitalization and waiting time within 24 hours of emergency department patients* — Health Care Management Science, 2024. [Link](https://link.springer.com/article/10.1007/s10729-023-09660-5)
2. Zhang et al., *Predicting patient risk of leaving without being seen using machine learning* — BMC Emergency Medicine, 2025. [Link](https://link.springer.com/article/10.1186/s12873-025-01287-9)
3. Alkan et al., *Optimizing emergency department efficiency using process mining and simulation* — BMC Medical Informatics, 2024. [Link](https://bmcmedinformdecismak.biomedcentral.com/articles/10.1186/s12911-024-02704-y)
4. Rahman et al., *Enhanced forecasting of ED patient arrivals using feature engineering* — BMC Medical Informatics, 2024. [Link](https://bmcmedinformdecismak.biomedcentral.com/articles/10.1186/s12911-024-02788-6)
5. Li et al., *Interpretable ML models for prolonged ED wait time prediction* — BMC Health Services Research, 2025. [Link](https://link.springer.com/article/10.1186/s12913-025-12535-w)
6. Demir & Yilmaz, *Changing the patient flow process using discrete-event simulation* — IJHMT, 2024. [Link](https://dergipark.org.tr/en/pub/ijhmt/issue/83822/1459872)
7. Patel et al., *An AI-based framework for predicting ED overcrowding* — JMIR Medical Informatics, 2025. [Link](https://medinform.jmir.org/2025/1/e73960)



## 📄 License

This project is developed for academic purposes under K.R Mangalam University. All rights reserved by the Echo Engineers team.

<p align="center">Made with ❤️ by <b>Echo Engineers</b> | SMARTQUEUE © 2026</p>
