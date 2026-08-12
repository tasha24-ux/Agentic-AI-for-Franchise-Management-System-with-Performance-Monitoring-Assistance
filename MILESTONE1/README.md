# 🔐 Infosys Springboard Internship 7.0

## 🚀 Milestone 1 — Secure User Authentication & Intelligent Analytics Portal

--- **Agentic AI for Franchise Management System with Performance Monitoring Assistance**

## 📌 Project Overview

**Milestone 1** focuses on designing and deploying a **secure, production-ready User Authentication Module** integrated with a **high-fidelity data visualization dashboard**.

The application is developed as a **Single-Page Application (SPA)** using **Streamlit** and incorporates:

* 🔒 Industry-standard security protocols
* 🛡️ Server-side validation
* 🎫 Stateless session tracking using JWT
* 🔑 Secure password hashing using bcrypt
* 📧 Asynchronous OTP-based identity recovery
* 👥 Role-Based Access Control
* 📊 Interactive analytics dashboards
* 🗄️ Persistent SQLite database
* ☁️ Google Colab-based cloud execution
* 🌐 Public access through secure tunneling

The application securely utilizes **hidden environment secrets** and exposes the local Streamlit instance through a public URL for evaluation and testing.

---

# ✨ Core Features

## 📝 1. Secure Registration — Signup Page

The registration module allows new users to securely create an account.

### Features:

* 👤 Unique username validation
* 📧 Email validation
* 🔑 Password creation
* ❓ Security question and answer mapping
* 🧹 Input sanitization
* 🛡️ Password complexity validation using **Regex**
* 🔐 Salted password hashing using **bcrypt**
* 🗃️ Secure storage in SQLite database

Passwords are **never stored as plain text**. Instead, bcrypt converts them into secure cryptographic hashes before they are stored.

---

## 🔑 2. Multi-Class Authentication — Login Page

The login system provides separate authorization channels for:

* 👤 **Standard Users**
* 👨‍💼 **Administrators**

### Security Features:

* 🔐 Cryptographic password verification
* 🎫 JWT-based session token generation
* 🛡️ Role-based access control
* 🚫 Generic login error messages
* 🔎 Protection against account enumeration attacks
* 🔄 Stateless session management

After successful authentication, the application generates a **JSON Web Token (JWT)** that is used to maintain the user's authenticated session.

---

# 🔄 3. Multi-Route Identity Recovery — Forgot Password

The Forgot Password system provides **two recovery mechanisms**.

### 🛣️ Route A — Security Question Verification

The user can recover their account by answering their predefined security question.

The submitted answer is:

1. ✂️ Normalized
2. 🔐 Hashed/processed securely
3. 🔍 Compared against the stored secure value
4. ✅ Verified before allowing password recovery

---

### 📩 Route B — Asynchronous SMTP OTP Verification

The second recovery mechanism uses a **6-digit OTP**.

### Workflow:

```text
👤 User requests password recovery
            ↓
🎲 Random 6-digit OTP generated
            ↓
📧 OTP sent through Gmail SMTP
            ↓
📨 User receives OTP
            ↓
⌨️ User enters OTP
            ↓
✅ OTP verified
            ↓
🔑 Password recovery permitted
```

The email communication is handled using:

* `smtplib`
* `email.mime`
* Gmail SMTP Relay

---

# 👥 4. Role-Based Post-Authentication Dashboards

After successful login, users are redirected according to their assigned role.

## 👤 Standard User Dashboard

The user dashboard provides an interactive analytics interface containing:

* 📊 Key Performance Indicators (KPIs)
* 📄 Document tracking matrices
* 📈 Interactive analytics
* ⚙️ System status monitoring
* 📉 Dynamic Plotly visualizations

The dashboard is designed to provide a clean and professional data-monitoring experience.

---

## 👨‍💼 Administrator Console

The administrator interface provides privileged access to system information.

### Admin Features:

* 🔐 Privileged authentication
* 🗄️ Access to the user database ledger
* 👥 User monitoring
* 📋 User record inspection
* 📊 Administrative analytics

The administrator account:

```text
infosys@ai
```

is given privileged access to the administrative console.

---

# 🎫 5. Stateless Session Guarding — JWT

The application uses **JSON Web Tokens (JWT)** to maintain authenticated sessions.

JWT allows the application to securely preserve authentication information across client requests without depending heavily on traditional server-side session storage.

### Authentication Flow

```text
🔑 Login
   ↓
🔐 Credentials Verified
   ↓
🎫 JWT Generated
   ↓
📦 Token Stored in Session
   ↓
🛡️ Token Validated on Protected Routes
   ↓
👤 Authorized Dashboard
```

The JWT is cryptographically signed using the **HS256 algorithm**.

---

# 🛠️ Technology Stack

| Component                 | Technology                |
| ------------------------- | ------------------------- |
| 🖥️ Frontend / UI         | **Streamlit**             |
| 🗄️ Database              | **SQLite3**               |
| 🔐 Password Security      | **bcrypt**                |
| 🎫 Session Authentication | **PyJWT**                 |
| 🔑 JWT Algorithm          | **HS256**                 |
| 📧 Email / OTP            | **Python smtplib**        |
| ✉️ Email Formatting       | **email.mime**            |
| 📊 Data Visualization     | **Plotly Graph Objects**  |
| ☁️ Cloud Environment      | **Google Colab**          |
| 🔒 Secret Management      | **Google Colab Secrets**  |
| 🌐 Public Exposure        | **ngrok / Secure Tunnel** |
| 🐍 Programming Language   | **Python**                |

---

# 🎨 User Interface

The Streamlit interface follows a **neutral corporate design** with a professional **Slate and Blue** visual theme.

The application contains multiple routes/pages:

```text
🏠 Application
│
├── 🔑 Login
│
├── 📝 Signup
│
├── 🔄 Forgot Password
│   ├── ❓ Security Question
│   └── 📩 Email OTP
│
├── 👤 User Dashboard
│
└── 👨‍💼 Admin Console
```

---

# 🔒 Security Architecture

The application implements multiple layers of security.

### 🛡️ Security Measures

* 🔐 bcrypt salted password hashing
* 🎫 JWT-based authentication
* 🔑 HS256 token signing
* 🧹 Input sanitization
* 📝 Regex-based validation
* 🚫 Generic authentication error messages
* 👥 Role-based authorization
* 🔑 Environment-based secret management
* 📧 Secure SMTP communication
* 🗄️ Persistent database storage

### Password Security

Instead of storing:

```text
MyPassword123
```

the application stores a cryptographic bcrypt hash such as:

```text
$2b$12$................................
```

This ensures that the original password is not directly stored in the database.

---

# ☁️ Google Colab Deployment

The project is designed to run directly inside **Google Colab**.

## 🔐 Phase 1 — Configure Environment Secrets

Before running the notebook, open the **Secrets 🔑** section in Google Colab.

Add the following three secrets:

| Secret Name      | Purpose                                    |
| ---------------- | ------------------------------------------ |
| `JWT_SECRET`     | Secret key used to sign JWT session tokens |
| `EMAIL_ADDRESS`  | Gmail account used to send OTP emails      |
| `EMAIL_PASSWORD` | 16-digit Google App Password               |

### ⚠️ Important

Enable the **Notebook Access** toggle for all three secrets.

The `EMAIL_PASSWORD` must be a **Google App Password**, not the regular Gmail account password.

---

# ▶️ Phase 2 — Execution Workflow

Follow these steps to run the application.

### 1️⃣ Open the Project Notebook

Open the primary project notebook in **Google Colab**.

### 2️⃣ Install Dependencies

Run the initial setup cells to install the required packages:

```bash
pip install pyjwt bcrypt streamlit-option-menu plotly
```

### 3️⃣ Generate `app.py`

The notebook uses:

```python
%%writefile app.py
```

This command creates the `app.py` file and writes the complete Streamlit application code into it.

The generated file contains:

* 🖥️ Frontend interface
* 🔑 Login logic
* 📝 Registration logic
* 🔄 Password recovery
* 📩 OTP verification
* 🗄️ Database initialization
* 🎫 JWT authentication
* 📊 Dashboard layouts
* 👨‍💼 Admin console

### 4️⃣ Start Streamlit

Run Streamlit in the background:

```bash
streamlit run app.py &
```

### 5️⃣ Configure the Network Tunnel

Use **ngrok** or another secure tunneling solution to expose the local Streamlit server.

```text
Google Colab
     ↓
Streamlit
     ↓
Local Application
     ↓
Secure Tunnel
     ↓
🌐 Public URL
```

### 6️⃣ Open the Public URL

Click the generated public URL to access and test the application.

---

# 📊 Application Workflow

The complete application workflow can be summarized as:

```text
                 🚀 APPLICATION
                       │
          ┌────────────┴────────────┐
          ↓                         ↓
      📝 SIGNUP                 🔑 LOGIN
          │                         │
          ↓                         ↓
    Validate Input          Verify Credentials
          │                         │
          ↓                         ↓
    bcrypt Hashing             Generate JWT
          │                         │
          ↓                         ↓
      🗄️ SQLite              Role Verification
                                    │
                         ┌──────────┴──────────┐
                         ↓                     ↓
                    👤 USER              👨‍💼 ADMIN
                         │                     │
                         ↓                     ↓
                  📊 Analytics           🗄️ User Ledger
```

---

# 🔄 Password Recovery Workflow

```text
             🔄 FORGOT PASSWORD
                     │
             ┌───────┴───────┐
             ↓               ↓
       ❓ Security        📩 Email OTP
          Question           Route
             │               │
             ↓               ↓
       Verify Answer     Generate 6-Digit OTP
             │               │
             ↓               ↓
          ✅ Match       Send via SMTP
             │               │
             └───────┬───────┘
                     ↓
              🔑 Reset Password
```

---

# 📸 Screenshots & Proof of Execution

The project includes visual proof demonstrating successful execution of the major application modules.

### Screenshots Included:

* 🔑 **Login Viewport**
* 📝 **Signup Interface**
* ❓ **Forgot Password — Security Question Route**
* 📩 **Forgot Password — SMTP OTP Verification**
* 📬 **Received OTP Notification Email**
* 👤 **Standard User Analytics Portal**
* 👨‍💼 **Administrative Privileged Console**
* 🗄️ **User Ledger**

These screenshots demonstrate the working state of the authentication, recovery, dashboard, and administrative modules.

---

# 📁 Project Architecture

The project can be represented as:

```text
📦 Infosys-Springboard-Milestone-1
│
├── 📓 MILESTONE1.ipynb
│
├── 🐍 app.py
│
├── 🗄️ SQLite Database
│
└── 📸 Screenshots
    ├── Login
    ├── Signup
    ├── Forgot Password
    ├── OTP Verification
    ├── User Dashboard
    └── Admin Console
```

---

# 🎯 Learning Outcomes

Through this milestone, the following concepts were implemented and understood:

* 🔐 Secure authentication
* 🔑 Password hashing
* 🧂 Salted cryptography
* 🎫 JWT authentication
* 👥 Role-based access control
* 📧 SMTP-based OTP verification
* 🗄️ SQLite database management
* 🧹 Input validation and sanitization
* 🔎 Regex validation
* 📊 Interactive data visualization
* 🖥️ Streamlit application development
* ☁️ Google Colab deployment
* 🌐 Public URL tunneling
* 🔒 Environment secret management

---
# 📸 Screenshots — Application Demonstration

The following screenshots demonstrate the successful execution of all major modules implemented in **Infosys Springboard Internship 7.0 — Milestone 1**.

---

## 🔑 1. Login Page

The login page provides separate authentication for **Standard Users** and **Administrators**. It validates the entered credentials and generates a JWT session token after successful authentication.

![Login Page]<img width="549" height="422" alt="login_page" src="https://github.com/user-attachments/assets/128700c5-8fa6-4e15-b99e-9505691dd6a4" />


---


## 🔄 2. Forgot Password — Security Question

This screenshot demonstrates **Route A** of the password recovery system.

The user can verify their identity by answering the previously configured security question.

![Forgot Password - Security Question]<img width="382" height="410" alt="Forgot password(Security Question)" src="https://github.com/user-attachments/assets/617614e3-42e9-4102-9d12-303ad3a77a7e" />


---

## 📩 3. Forgot Password — OTP Verification

This screenshot demonstrates **Route B**, where the system generates a random **6-digit OTP** and sends it to the registered email address using Gmail SMTP.

![OTP Verification]<img width="330" height="395" alt="Forgot password(OTP)" src="https://github.com/user-attachments/assets/a89a1558-c7f2-47a9-9648-5afa9505dd75" />


---

## 📬 4. OTP Received Through Email

The following screenshot demonstrates the successful delivery of the generated OTP to the user's registered email account.

![OTP Email]<img width="635" height="326" alt="OTP fetched from Email" src="https://github.com/user-attachments/assets/87e4b1b7-0019-4efa-b11b-1fe7b62e987c" />


---

## 👤 5. Standard User Analytics Dashboard

After successful authentication, a Standard User is redirected to the analytics dashboard.

The dashboard contains:

* 📊 Key Performance Indicators
* 📄 Document tracking information
* 📈 Interactive Plotly charts
* ⚙️ System status information
* 📉 Data visualization components

![User Analytics Dashboard]<img width="951" height="410" alt="Dashboard" src="https://github.com/user-attachments/assets/dc451d7f-6af1-4792-b656-ab2669172f90" />





---

# 🖼️ Complete Application Flow

The screenshots collectively demonstrate the complete workflow of the application:

```text
                🚀 APPLICATION
                     │
                     ↓
                🔑 LOGIN
                     │
          ┌──────────┴──────────┐
          ↓                     ↓
      👤 USER                👨‍💼 ADMIN
          │                     │
          ↓                     ↓
   📊 USER DASHBOARD      🗄️ ADMIN CONSOLE


        🔄 FORGOT PASSWORD
                 │
        ┌────────┴────────┐
        ↓                 ↓
 ❓ Security Question   📩 Email OTP
        │                 │
        └────────┬────────┘
                 ↓
           🔑 Password Reset
```

---

# 📂 Recommended Screenshot Folder Structure

For GitHub, keep all screenshots inside a dedicated folder:

```text
📦 Infosys-Springboard-Milestone-1
│
├── 📓 MILESTONE1.ipynb
├── 🐍 app.py
├── 🗄️ database.db
│
└── 📸 screenshots
    │
    ├── login.png
    ├── signup.png
    ├── forgot_password_security.png
    ├── otp_verification.png
    ├── otp_email.png
    ├── user_dashboard.png
    ├── admin_dashboard.png
    └── admin_ledger.png
```

> 💡 **Tip:** GitHub automatically renders these images when the paths in the README match the actual filenames and folder structure.

---

# 🏆 Milestone 1 — Visual Proof

| Module                | Screenshot                     |
| --------------------- | ------------------------------ |
| 🔑 Login              | `login.png`                    |
| 📝 Signup             | `signup.png`                   |
| ❓ Security Question   | `forgot_password_security.png` |
| 📩 OTP Verification   | `otp_verification.png`         |
| 📬 OTP Email          | `otp_email.png`                |
| 👤 User Dashboard     | `user_dashboard.png`           |
| 👨‍💼 Admin Dashboard | `admin_dashboard.png`          |
| 🗄️ Admin Ledger      | `admin_ledger.png`             |

### ⭐ Successfully Implemented

**Secure Authentication 🔐 + OTP Recovery 📩 + JWT Sessions 🎫 + Role-Based Access 👥 + Analytics Dashboard 📊 + Admin Console 🗄️**


# 🏆 Milestone 1 Summary

**Infosys Springboard Internship 7.0 — Milestone 1** successfully combines **secure authentication, identity recovery, role-based authorization, database management, session security, and interactive analytics** into a single Streamlit-based application.

The project demonstrates how multiple backend and frontend components can be integrated into one production-oriented application while maintaining a strong focus on **security, usability, and scalability**.

```text
🔐 Secure Authentication
        +
🎫 JWT Session Management
        +
📧 OTP Verification
        +
🗄️ SQLite Database
        +
📊 Interactive Analytics
        +
👥 Role-Based Access
        ↓
🚀 Secure Intelligent Analytics Portal
```

---

## 👩‍💻 Internship Project

**Program:** Infosys Springboard Internship 7.0
**Milestone:** Milestone 1
**Project:** Agentic AI for Franchise Management System with Performance Monitoring Assistance
**Platform:** Google Colab + Streamlit
**Language:** Python

### ⭐ Milestone 1 — Completed Successfully!
