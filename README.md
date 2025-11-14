# **Anna Sampada: AI-Powered Food Waste Management Platform**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python\&logoColor=white)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-18-blue?logo=react\&logoColor=61DAFB)](https://reactjs.org/)
[![Flask](https://img.shields.io/badge/Flask-3.0-black?logo=flask\&logoColor=white)](https://flask.palletsprojects.com/)
[![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?logo=vercel)](https://vercel.com/)

**Anna Sampada** is an intelligent web platform that integrates multiple machine learning models with a generative AI assistant to help users predict food spoilage, create recipes from leftovers, and donate surplus food efficiently.

### **Live Demo**

[https://anna-sampada-v1.vercel.app](https://anna-sampada-v1.vercel.app)
*(Replace with your actual deployed link.)*

---

## **Core Features**

### 1. Multi-Model Food Spoilage Prediction

The system uses five dedicated machine learning models to predict freshness and spoilage for:

* Rice
* Milk
* Paneer
* Roti
* Dal

Each model is trained on product-specific datasets to deliver more reliable predictions.

---

### 2. "Anna" – AI Assistant (Powered by Google Gemini)

A context-aware generative AI chatbot capable of:

* Generating recipes from user-provided leftover ingredients
* Providing food safety guidance
* Guiding users through the application
* Respecting dietary filters: *Vegetarian*, *Non-Vegetarian*, *Jain*

---

### 3. Role-Based User Management

Three distinct user roles provide structured access control:

| Role          | Capabilities                                                |
| ------------- | ----------------------------------------------------------- |
| **User**      | Predict spoilage, interact with the AI chatbot, donate food |
| **NGO**       | Receive food donation requests via email                    |
| **Composter** | Listed as waste management partners                         |

---

### 4. Food Donation and NGO Interaction

A complete donation workflow is provided:

1. Users browse or search registered NGOs.
2. Users submit a donation request form.
3. NGOs receive automated email notifications via the backend.

---

### 5. Data Logging for AI Improvement

All chatbot conversations and model prediction inputs are stored in Firestore.
This data supports:

* System debugging
* Behavioral analysis
* Future model fine-tuning
* Personalized user experiences

---

## **Technology Stack**

| Category             | Technologies                                                        |
| -------------------- | ------------------------------------------------------------------- |
| **Frontend**         | React, Vite, Tailwind CSS, Material UI, Framer Motion, Lucide Icons |
| **Backend**          | Flask (Python), Gunicorn                                            |
| **Generative AI**    | Google Gemini Pro API                                               |
| **Machine Learning** | Scikit-Learn, Pandas, XGBoost                                       |
| **Database**         | Google Firestore                                                    |
| **Deployment**       | Vercel                                                              |

---

## **Project Structure**

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
│   ├── app.py
│   ├── requirements.txt
│   ├── serviceAccountKey.json
│   └── .env
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── auth/
│   │   │   ├── chatbot/
│   │   │   ├── layout/
│   │   │   └── ui/
│   │   ├── context/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env
│   ├── package.json
│   ├── index.html
│   ├── tailwind.config.js
│   └── vite.config.js
│
├── .gitignore
└── vercel.json
```

---

## **Setup and Installation**

### 1. Prerequisites

* Google Cloud Project with:

  * Firestore
  * Gemini API enabled
  * `serviceAccountKey.json`
  * `GEMINI_API_KEY`
* Gmail account with an App Password for backend email functionality

---

## **Local Development**

### Backend

```bash
cd backend
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
```

Create `.env`:

```
GEMINI_API_KEY="your_key"
EMAIL_SENDER="your_email@gmail.com"
EMAIL_APP_PASSWORD="your_app_password"
```

Add `serviceAccountKey.json`.

Start the server:

```bash
python app.py
```

---

### Frontend

```bash
cd ..
npm install
npm run dev
```

---

## **Deployment on Vercel**

1. Push the project to GitHub.
2. Import the repository into Vercel.
3. Vercel will auto-detect the monorepo structure.
4. Set environment variables in the Vercel dashboard:

   * `GEMINI_API_KEY`
   * `EMAIL_SENDER`
   * `EMAIL_APP_PASSWORD`
5. Deploy the application.

---

## **Project Summary**

* Fully functional production-grade system integrating generative AI, machine learning prediction, and secure user authentication
* Stable and optimized backend with complete CORS, routing, and dependency management
* Modern UI/UX with properly structured navigation, protected routes, and responsive design
* End-to-end donation and communication workflow connecting users with NGOs

---

**Developed by Team Anna Sampada**

---
