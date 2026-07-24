# FranchiseOps AI Platform
### AI-Powered Intelligent Franchise Management System

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-Web%20App-red)
![SQLite](https://img.shields.io/badge/Database-SQLite-green)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-orange)
![HuggingFace](https://img.shields.io/badge/LLM-Qwen2.5--3B-purple)
![JWT](https://img.shields.io/badge/Security-JWT-yellow)

---

# 📖 About the Project

FranchiseOps AI is an enterprise-level intelligent franchise management platform developed as part of the **Infosys Springboard Milestone 2 Project**.
The application combines **Artificial Intelligence, Machine Learning, Secure Authentication, Role-Based Access Control, Business Analytics, and Large Language Models** into a single dashboard designed to assist franchise owners and administrators in making smarter business decisions.
Unlike a traditional management system, FranchiseOps AI not only manages users securely but also predicts workforce attrition, forecasts inventory demand, simulates outlet revenue, analyzes outlet performance, provides AI-generated business recommendations, and offers administrative control through an advanced dashboard.
Milestone 2 extends the authentication system developed in Milestone 1 by integrating three autonomous machine learning agents, an AI Copilot powered by Hugging Face, progressive account security, password validation, weather-based demand forecasting, and complete administrator lifecycle management. :contentReference[oaicite:1]{index=1}

---

#  Project Objectives

The primary objectives of this project are:

- Develop a secure authentication system with JWT-based sessions.
- Protect user accounts using progressive account lockout.
- Improve password security through real-time password strength validation.
- Enable secure password recovery using Gmail OTP verification.
- Train multiple machine learning models and automatically select the best-performing algorithm.
- Generate AI-powered business insights using a Large Language Model.
- Assist franchise owners in predicting employee attrition and inventory demand.
- Classify outlet performance using K-Means clustering.
- Provide an administrative dashboard for complete user management.
- Demonstrate the integration of AI, ML, Web Development, and Cybersecurity into one production-ready application.

---

#  Key Features

##  Authentication & Security

The application provides a complete enterprise-grade authentication system that ensures user identities remain secure.

### Features

- User Registration
- Secure Login
- Forgot Password
- Gmail OTP Verification
- JWT Token Authentication
- Password Hashing using bcrypt
- SQLite Database Storage
- Session Management

---

##  Advanced Security Engine

To protect user accounts from brute-force attacks, the platform implements progressive account lockout.

### Progressive Lockout

| Failed Attempts | Action |
|----------------|--------|
| 3 | Locked for 5 Minutes |
| 4 | Locked for 15 Minutes |
| 5 | Permanently Locked |

Only an administrator can unlock permanently locked accounts.

### Additional Security

- OTP Resend Rate Limiting
- Password Strength Validation
- Secure JWT Session Handling
- Hashed Password Storage
- Role-Based Authentication

---

#  Artificial Intelligence & Machine Learning

The heart of the application consists of three independent AI agents.

Each agent trains multiple machine learning algorithms, compares their performance, and automatically selects the champion model.

---

##  Agent 1 — Workforce Attrition Prediction

### Purpose

Predicts whether an employee is likely to leave the organization.

### Algorithms

- Logistic Regression
- Random Forest
- Gradient Boosting
- Support Vector Machine
- Decision Tree

### Performance Metric

- ROC-AUC Score

### Benefits

- Identify employees at risk.
- Improve retention strategies.
- Reduce hiring costs.
- Support HR decision making.

---

##  Agent 2 — Revenue Prediction & Outlet Tiering

### Purpose

Predicts outlet revenue and categorizes franchise performance.

### Algorithms

- Random Forest Regressor
- Gradient Boosting Regressor
- Extra Trees Regressor
- Ridge Regression
- Decision Tree Regressor

### Clustering

K-Means clustering categorizes outlets into

- Excellent
- Good
- Needs Attention
- Critical

### Benefits

- Identify high-performing stores.
- Detect underperforming outlets.
- Improve sales planning.
- Assist management decisions.

---

##  Agent 3 — Inventory Demand Forecasting

### Purpose

Forecast future inventory demand using historical retail data.

### Algorithms

- Gradient Boosting Regressor
- Random Forest Regressor
- Extra Trees Regressor
- Ridge Regression
- Decision Tree Regressor

### Benefits

- Reduce stock shortages.
- Prevent overstocking.
- Improve warehouse planning.
- Reduce inventory costs.

---

# AI Copilot

The AI Copilot integrates a Large Language Model (Qwen2.5-3B Instruct) through Hugging Face.

Instead of displaying only numerical outputs, the AI Copilot analyzes the predictions generated by all three machine learning agents and converts them into easy-to-understand business recommendations.

The Copilot can:

- Explain prediction results.
- Suggest employee retention strategies.
- Recommend inventory improvements.
- Generate executive summaries.
- Produce structured JSON ERP actions.
- Answer franchise-related business questions.

---

# Weather Intelligence Module

Weather conditions directly impact retail demand.

The Weather Module retrieves live weather information for supported cities and helps users estimate possible impacts on inventory requirements and customer demand.

Supported Cities:

- Mumbai
- Delhi NCR
- Bengaluru
- Hyderabad
- Chennai
- Pune

---

#  Admin Dashboard

The Admin Dashboard provides complete administrative control over the application.

### User Management

- Add New Users
- Delete Existing Users
- Unlock Locked Accounts
- Assign User Roles
- View Registered Users

### Model Monitoring

The dashboard also displays

- ML Model Accuracy
- ROC-AUC Scores
- R² Scores
- KMeans Tier Metrics

---

#  System Architecture

```
                    User

                      │

          Login / Registration

                      │

           JWT Authentication

                      │

              SQLite Database

                      │

       Secure Streamlit Dashboard

 ┌───────────────────────────────────────────────┐
 │                                               │
 │   Workforce Attrition Agent                   │
 │                                               │
 │   Revenue Prediction Agent                    │
 │                                               │
 │   Inventory Forecasting Agent                 │
 │                                               │
 └───────────────────────────────────────────────┘

                      │

          AI Copilot (LLM)

                      │

     Business Recommendations

                      │

          Admin Dashboard
```

---

#  Technology Stack

### Programming

- Python

### Frontend

- Streamlit

### Database

- SQLite

### Machine Learning

- Scikit-Learn
- Joblib
- NumPy
- Pandas

### AI

- Hugging Face Transformers
- Qwen2.5-3B Instruct

### Security

- JWT
- bcrypt
- Gmail SMTP
- OTP Authentication

### Visualization

- Plotly
- Matplotlib

---

#  Folder Structure

```
Milestone2/

│
├── app.py
├── auth.py
├── admin_dash.py
├── db.py
├── ui_theme.py
├── llm_engine_franchise.py
├── train_m2_franchise.py
├── requirements.txt
├── README.md
├── FranchiseOps_AI_Milestone2.ipynb
│
├── models/
│
├── screenshots/
│
└── datasets/
```

---

# ⚙ Installation Guide

Clone the repository

```bash
git clone https://github.com/username/FranchiseOps-AI.git
```

Navigate into the project

```bash
cd Milestone2
```

Install dependencies

```bash
pip install -r requirements.txt
```

Launch the application

```bash
streamlit run app.py
```

---

# 🔑 Environment Variables

Configure the following secrets before running the application:

- JWT_SECRET_KEY
- ADMIN_EMAIL_ID
- ADMIN_PASSWORD
- EMAIL_ID
- EMAIL_PASSWORD
- HF_TOKEN
- NGROK_AUTHTOKEN
- KAGGLE_USERNAME
- KAGGLE_KEY

---

# 📈 Future Improvements

- Docker Deployment
- AWS Cloud Hosting
- Multi-language Support
- Voice-enabled AI Assistant
- Predictive Sales Dashboard
- Mobile Application
- Real-Time Notifications
- Power BI Integration

---

# 📷 Project Screenshots

## 🏠 Home Page

![Home](screenshots/home.png)

---

## 🔑 Login Page

![Login](screenshots/login.png)

---

## 🤖 AI Copilot

![AI](screenshots/ai_copilot.png)

---

## 🌦 Weather Demo

![Weather](screenshots/weather_demo.png)

---

## 📊 Outlet Tiering

![Tiering](screenshots/outlet_tiers.png)

---

## 👨‍💼 Admin Dashboard

![Admin](screenshots/admin_dashboard.png)

---

## 📈 ML Model Card

![ML](screenshots/ml_models.png)

---

## 🔒 Account Lockout

![Lockout](screenshots/lockout.png)

---

## 📩 OTP Cooldown

![OTP](screenshots/otp_cooldown.png)

---

# 📚 Learning Outcomes

Through this project, I gained practical experience in:

- Python Programming
- Streamlit Development
- Machine Learning Model Training
- Feature Engineering
- JWT Authentication
- Password Security
- SQLite Database Design
- AI Integration
- Hugging Face Transformers
- Data Visualization
- Software Architecture
- Git & GitHub
- End-to-End Full Stack AI Development

---

# 👩‍💻 Author

**Tazreen Rahman**

Infosys Springboard Internship

Milestone 2 Project

---

# ⭐ If you found this project interesting, don't forget to Star the repository!

