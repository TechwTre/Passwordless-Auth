# Passwordless Authentication Implementation

## 📌 Project Overview
This project demonstrates a **Passwordless Authentication** setup using **Okta**, **WebAuthn**, and **Magic Links**. It eliminates passwords while maintaining strong security, improving user experience and reducing phishing risks.

## 🚀 Features
- 🔑 **WebAuthn (Biometric/FIDO2) Authentication**
- ✉️ **Magic Link Login Flow**
- 🔄 **Adaptive Authentication Policies**
- 🏗 **Okta API Integration for User Management**

---

## 🛠 Prerequisites
- [ ] Okta Developer Account ([Sign up for free](https://developer.okta.com/))
- [ ] Python 3.x installed
- [ ] WebAuthn-supported browser (Chrome, Edge, etc.)
- [ ] Okta API Token

---

## 🔧 Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourgithubusername/passwordless-auth.git
cd passwordless-auth
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Configure Environment Variables
Create a `.env` file in the project root and add:
```
OKTA_ORG_URL=https://your-okta-domain.okta.com
OKTA_API_TOKEN=your_api_token
```

### 4️⃣ Run the Passwordless Authentication Setup
```bash
python setup_passwordless.py
```

---

## 📜 License
This project is open-source and available for educational use.

---
### ⭐ Show Some Love
If this project helps you, star it on GitHub! ⭐

