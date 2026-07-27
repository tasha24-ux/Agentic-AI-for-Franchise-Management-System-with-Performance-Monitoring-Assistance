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

![Home](<img width="919" height="410" alt="home page" src="https://github.com/user-attachments/assets/538a2418-1c24-4644-911f-810668915eba" /> / )

---

## 🔑 Login Page

 <img width="488" height="347" alt="login page" src="https://github.com/user-attachments/assets/324ce726-caac-492e-bef9-8084f48d1862" />


---

## 🤖 AI Copilot

<img width="946" height="369" alt="AI copilot" src="https://github.com/user-attachments/assets/0f7ea932-1a08-494e-93e9-4c3ad2b3765f" />

---

## 🌦 Weather Demo

<img width="953" height="407" alt="weather demo" src="https://github.com/user-attachments/assets/ea96d712-4e5f-4628-9d84-0e27020ddcc3"/> 

---

## 📊 Outlet Tiering

 <img width="846" height="299" alt="outlet tiering" src="https://github.com/user-attachments/assets/f7a6b8e9-b972-4d17-9a9a-88467e0f6428" />

---

## 👨‍💼 Admin Dashboard

(<img width="946" height="404" alt="admin png" src="https://github.com/user-attachments/assets/9952a2de-d245-4822-900e-36a5a84d11f5" />




---

## 📈 ML Model Card

(<img width="951" height="154" alt="account information" src="https://github.com/user-attachments/assets/086360bc-155b-43e5-9c48-57e6b88483b5" />

---

## 🔒 Account Lockout

<img width="948" height="408" alt="ML model card png" src="https://github.com/user-attachments/assets/81ba0a7f-1070-4250-bb2f-858683cb3a96" /> 


---



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
