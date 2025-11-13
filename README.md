# Food Freshness Predictor

## Project Overview
This web application predicts the freshness or spoilage state of common food items (Cooked Rice, Milk, Paneer) based on user input. It features a dynamic UI that adapts to the selected food, incorporating specific validation rules and constraints (e.g., milk boiling, paneer storage). Predictions are powered by dedicated machine learning models for each food type hosted on a Python Flask backend.

## Features
* **Multi-Food Support:** Predicts spoilage for Cooked Rice, Milk (Pasteurized, UHT, Raw/Loose), and Paneer (Cooked, Raw).
* **Dynamic UI:** Presents a tailored input form specific to the selected food item.
* **Conditional Logic:** Shows/hides questions based on previous answers (e.g., "Was Boiled?" for milk, "Storage Container" for raw paneer).
* **Robust Validation:** Includes real-time input checks, serial flow (disabling fields), and cross-field validation (e.g., room temp hours vs. total time).
* **ML Model Integration:** Connects to a Flask backend hosting separate ML models.
* **Clear Results:** Displays predictions (Fresh, Stale, Spoiled) with safety indicators and confidence levels.
* **Scalable Architecture:** Designed for easy addition of new food types in both backend (routes/preprocessing) and frontend (Manager/Specialist pattern).

## Tech Stack
**Backend:**
* Python 3.x
* Flask
* Pandas
* Scikit-learn (Logistic Regression, Random Forest)
* XGBoost
* Joblib

**Frontend:**
* React
* Framer Motion (Animations)
* Lucide React (Icons)
* Tailwind CSS (Styling)

**Development:**
* Node.js & npm

## Setup and Installation
**Prerequisites:**
* Python 3.x
* Node.js and npm

### Backend Setup
1.  Navigate to the backend directory:
    ```bash
    cd backend
    ```
2.  Create and activate a virtual environment (recommended):
    ```bash
    # Create the environment
    python -m venv venv
    
    # Windows activation:
    .\venv\Scripts\activate
    
    # 🍽️ Food Freshness Predictor

    ![GitHub Repo Size](https://img.shields.io/github/repo-size/Dakshinde/Anna?style=flat-square)
    ![GitHub Issues](https://img.shields.io/github/issues/Dakshinde/Anna?style=flat-square)
    ![GitHub License](https://img.shields.io/github/license/Dakshinde/Anna?style=flat-square)
    ![GitHub Stars](https://img.shields.io/github/stars/Dakshinde/Anna?style=flat-square)

    ---

    ## **Project Overview**
    The **Food Freshness Predictor** is a web application designed to predict the **freshness or spoilage** of common food items such as Cooked Rice, Milk, and Paneer. Users provide input about storage conditions, preparation methods, and timing, and the app uses **dedicated ML models** to provide accurate predictions.

    The frontend is built with React + Vite, featuring a **dynamic, responsive UI**, while the backend uses Python Flask hosting specialized ML models. Results include user-friendly indicators, confidence levels, and safety advice.

    ---

    ## **Live Demo**
    Check out the live demo here: [Your Live Demo Link](https://your-live-demo-link.com)  

    ![App Demo](https://your-gif-link.com/demo.gif)  
    *Animated GIF preview of the app (replace with actual GIF)*

    ---

    ## **Key Features**
    - **Multi-Food Support:** Cooked Rice, Milk (Pasteurized, UHT, Raw), Paneer (Cooked, Raw)  
    - **Dynamic UI:** Conditional form fields based on food type and user input  
    - **Robust Validation:** Real-time input checks and cross-field validation  
    - **ML Integration:** Separate models for each food type (Logistic Regression, Random Forest, XGBoost)  
    - **Clear Results:** Displays Fresh, Stale, or Spoiled status with safety indicators  
    - **Scalable Architecture:** Easy to extend to new foods or ML models  

    ---

    ## **Technology Stack**
    **Backend:** Python 3.x, Flask, Pandas, Scikit-learn, XGBoost, Joblib  
    **Frontend:** React, Tailwind CSS, Framer Motion, Lucide React  
    **Development Tools:** Node.js & npm  

    ---

    ## **Setup & Installation**

    ### **Prerequisites**
    - Python 3.x  
    - Node.js & npm  

    ### **Backend Setup**
    ```powershell
    cd backend
    python -m venv venv      # Create virtual environment
    # Activate venv
    # Windows
    .\venv\Scripts\activate
    # macOS/Linux
    source venv/bin/activate
    pip install -r requirements.txt
    python app.py
    ```

    ### **Frontend Setup**

    ```powershell
    cd ..\annasampada
    npm install
    npm run dev
    ```

    * Open your browser at `http://localhost:5173`

    ---

    ## **Backend Architecture**

    * **Model Training (`train_*.py`)**: Loads raw data, preprocesses it, evaluates multiple classifiers, saves model artifacts.
    * **Flask API (`app.py`)**: Loads models on startup, exposes endpoints:

      * `/api/predict` → Cooked Rice
      * `/api/predict_milk` → Milk
      * `/api/predict_paneer` → Paneer
      * Applies preprocessing, feature alignment, and safety rules.

    ---

    ## **Frontend Architecture**

    * **Manager Component (App):** Global state, navigation, renders correct Specialist form.
    * **Specialist Forms (RiceForm, MilkForm, PaneerForm):** Own state, validation, API calls.
    * **Reusable UI Components:** Stepper, InputGroup, SelectGroup, ResultCard, ApiErrorCard.

    ---

    ## **Future Enhancements**

    * Add more food types (Roti, Dal)
    * Implement user accounts & prediction history
    * Improve ML model accuracy with larger datasets
    * Refactor frontend into multiple files for maintainability
    * Integrate advanced AI-based chatbot for recipe suggestions & food safety tips

    ---

    ## **Contributing**

    1. Fork the repo
    2. Create a branch: `git checkout -b feature/YourFeature`
    3. Commit your changes: `git commit -m "Add new feature"`
    4. Push: `git push origin feature/YourFeature`
    5. Open a pull request

    ---

    ## **License**

    MIT License © 2025

    ---

    ## **Contact**

    * GitHub: [Dakshinde](https://github.com/Dakshinde)
    * Email: [your-email@example.com](mailto:daksh.shinde.dhs@gmail.com)
