
# **Anna Sampada: An AI-Powered Food Waste Management Platform**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python\&logoColor=white)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-18-blue?logo=react\&logoColor=61DAFB)](https://reactjs.org/)
[![Flask](https://img.shields.io/badge/Flask-3.0-black?logo=flask\&logoColor=white)](https://flask.palletsprojects.com/)
[![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?logo=vercel)](https://vercel.com/)

An intelligent web platform that uses a hybrid AI system—combining multiple Machine Learning models with a Generative AI chatbot—to help users predict food spoilage, generate recipes from leftovers, and donate surplus food responsibly.


---

## 🚀 **Core Features**

### **🔍 Multi-Model Spoilage Prediction**

Uses **five specialized ML models** for:

* Rice
* Milk
* Paneer
* Roti
* Dal

Each model provides accurate freshness predictions based on user inputs.

---

### **🤖 "Anna" – AI Chatbot (Powered by Google Gemini)**

The intelligent assistant can:

* **Generate recipes** from leftover ingredients
* **Give food safety tips**
* **Navigate the app** (e.g., “Take me to Predict Spoilage”)
* **Obey dietary preferences**: `Veg`, `Non-Veg`, `Jain`

---

### **👤 User Authentication & Role-Based Access**

Three user roles with distinct capabilities:

| Role          | Permissions                                 |
| ------------- | ------------------------------------------- |
| **User**      | Predict spoilage, chat with AI, donate food |
| **NGO**       | Receive donation notifications              |
| **Composter** | Listed as a food waste management option    |

---

### **🎁 NGO Donation Portal**

A complete donation workflow:

1. Users search and find nearby NGOs (demo list).
2. Fill out a donation form with food details.
3. Backend sends **automated email notifications** to NGOs.

---

### **📊 AI Training & Data Logging**

All chatbot logs and prediction inputs are stored in **Firestore** for:

* Future fine-tuning
* Debugging
* Personalized AI responses

---

## 🛠️ **Tech Stack**

| Area                | Technology                                                      |
| ------------------- | --------------------------------------------------------------- |
| **Frontend**        | React, Vite, Tailwind, Material UI, Framer Motion, Lucide Icons |
| **Backend**         | Flask (Python), Gunicorn                                        |
| **AI – Chatbot**    | Google Gemini Pro API                                           |
| **AI – Prediction** | Scikit-Learn, Pandas, XGBoost                                   |
| **Database**        | Google Firestore                                                |
| **Deployment**      | Vercel                                                          |

---

## 📁 **Project Architecture**

```
/annasampada-v1.1/
│
├── backend/
│   ├── ML/
│   │   ├── rice/ (rice_model.joblib)
│   │   ├── milk/ (xgboost_milk_spoilage_model.joblib)
│   │   ├── paneer/ (random_forest_paneer_model.joblib)
│   │   ├── roti/ (roti_spoiler_pipeline.joblib)
│   │   └── dal/ (dal_spoilage_final_model.joblib)
│   │
│   ├── app.py              # Main Flask server & API routes
│   ├── requirements.txt    # Python dependencies
│   ├── serviceAccountKey.json   # Firebase Admin Key (ignored)
│   └── .env                # API keys (ignored)
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── auth/ (ProtectedRoute.jsx)
│   │   │   ├── chatbot/ (ChatbotWidget.jsx)
│   │   │   ├── layout/ (Navbar.jsx, Footer.jsx)
│   │   │   └── ui/ (ChatMenu.jsx, ChatMessage.jsx, ...)
│   │   ├── context/ (AuthContext.jsx, ThemeContext.jsx)
│   │   ├── hooks/ (useChatSession.js)
│   │   ├── pages/
│   │   │   ├── auth/ (LoginPage.jsx, SignupPage.jsx)
│   │   │   ├── user/ (UserDashboard.jsx, UserHomePage.jsx)
│   │   │   └── UnderConstruction.jsx
│   │   ├── services/ (chatbot.service.js)
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env
│   ├── index.html
│   ├── package.json
│   ├── tailwind.config.js
│   └── vite.config.js
│
├── .gitignore
└── vercel.json
```

---

## ⚙️ **Setup & Deployment**

### ✅ 1. **Prerequisites**

You will need:

* A **Google Cloud Project** with:

  * Firestore enabled
  * Gemini API enabled
  * `serviceAccountKey.json`
  * `GEMINI_API_KEY`
* A Gmail account with an **App Password** for backend emailing

---

## 💻 **Local Development**

### **Backend Setup**

```bash
cd backend
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
```

Create `.env`:

```
GEMINI_API_KEY="your_key"
EMAIL_SENDER="your-bot@gmail.com"
EMAIL_APP_PASSWORD="your-16-digit-pass"
```

Add `serviceAccountKey.json`, then run:

```bash
python app.py
```

---

### **Frontend Setup**

```bash
cd ..
npm install
npm run dev
```

---

## ☁️ **Deploying on Vercel**

1. Push project to GitHub
2. Import repository into Vercel
3. Vercel auto-detects the monorepo
4. Add backend environment variables:

   * `GEMINI_API_KEY`
   * `EMAIL_SENDER`
   * `EMAIL_APP_PASSWORD`
5. Click **Deploy**

---

## 🎉 **Project Highlights**

* **Stable, production-ready system** with resolved CORS, routing, and dependency issues
* **Professional dashboard UI/UX**
* **Complete workflow**: authentication → prediction → chatbot → donation
* **Full AI integration** with Firestore logging

---

### *Made with ❤️ by Team AnnaSampada*

---
