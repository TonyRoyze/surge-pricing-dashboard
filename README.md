# 🚖 Surge Pricing & Profit Dashboard

A sophisticated machine learning-powered web application designed to optimize ride-sharing fares and track profitability in real-time. This project addresses the inefficiencies of fixed pricing models by introducing dynamic, market-aware fare predictions and profit analysis.

## 🎯 Objective

### Problem Statement
Our ride-sharing company currently sets fares based **only on ride duration**, using a fixed pricing rule that ignores real-time market conditions such as demand surges, weather, and driver availability.

### Impact of Fixed Pricing
- 🕐 **Long waiting times** for riders due to mismatch in supply/demand.
- ❌ **High ride cancellations** when demand far exceeds supply.
- 🚗 **Inefficient driver allocation** as drivers lack incentive to move to high-demand areas.

---

## 🚀 Key Features

### 1. Live Fare Prediction
- Real-time prediction of optimized ride fares based on riders, drivers, and expected duration.
- Interactive input controls with instant AI-driven estimates.
- High-fidelity animations for price transitions using Framer Motion.

### 2. Profit Tracking Dashboard
- Historical and live-simulated ride tracking.
- Automated calculation of **Average Profit Percentage** for completed rides.
- Advanced filtering by city, country, and status (Completed, In Progress, Cancelled).
- Currency selection for global market configuration previews.

### 3. Machine Learning Backend
- Multi-model inference pipeline using scikit-learn.
- SHAP-based feature selection to identify key pricing drivers.
- Batch processing for fast profit percentage updates across multiple ride records.

---

## 🛠 Tech Stack

### Frontend
- **Framework**: React 19 + TypeScript 5
- **Build Tool**: Vite 7
- **Styling**: Tailwind CSS 4 (Custom design system)
- **Animations**: Framer Motion
- **UI Components**: Radix UI + Custom primitive abstractions
- **API Client**: Axios

### Backend
- **Framework**: FastAPI (Python 3.12+)
- **Server**: Uvicorn
- **Data Science**: Scikit-Learn, Pandas, NumPy, Joblib
- **Modeling**: SHAP analysis for feature importance and model interpretability.

---

## 📁 Project Structure

```text
surge-pricing-dashboard/
├── backend/                # FastAPI service & ML models
│   ├── main.py             # API endpoints and model serving
│   ├── model/              # Trained .pkl models and EDA notebooks
│   └── requirements.txt    # Python dependencies
├── frontend/               # React + TypeScript web app
│   ├── src/                # Component logic and dashboards
│   ├── public/             # Static assets (screenshots, icons)
│   └── tailwind.config.js  # Styling configuration
└── README.md               # Root documentation
```

---

## ⚙️ Getting Started

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Start the server:
   ```bash
   uvicorn main:app --reload --port 8001
   ```

### Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```

---

## 📊 Modeling Workflow

The backend utilizes an end-to-end pipeline for model training and selection:
1. **EDA**: Univariate/multivariate inspection in `EDA_Notebook.ipynb`.
2. **Feature Engineering**: Deriving `profit_percentage` from demand/supply multipliers.
3. **Optimized Selection**: SHAP analysis identified `Number_of_Riders` and `Number_of_Drivers` as the most significant features for profit prediction.
4. **Evaluation**: Hyperparameter tuning via `GridSearchCV` 5-fold CV, optimizing for RMSE and R².

---

## 📸 Screenshots

### Home Page - Fare Prediction
![Home Page](./frontend/public/homepage.png)

### Rides Dashboard - Profit Analysis
![Rides Dashboard](./frontend/public/dashboard.png)
