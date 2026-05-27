# CredBud: Adaptive Credit Decisioning System

CredBud is a cutting-edge loan application predictive system designed to empower underbanked users. By moving beyond traditional credit scores (like CIBIL), CredBud analyzes real-world financial data, including UPI transactions, assets, and debt obligations, to provide highly accurate loan approval predictions and actionable financial feedback.

## 🚀 Key Features

- **ML-Powered Predictions**: Uses a K-Nearest Neighbors (KNN) classifier to predict loan approval probability.
- **UPI Transaction Analysis**: Upload CSV/Excel statements to analyze spending patterns and financial behavior.
- **4-Layer Evaluation Architecture**: A sophisticated tiered analysis of a user's entire financial profile.
- **Transparent Feedback**: Provides clear reasons for decisions, highlighting strengths and offering recommendations for improvement.
- **Interactive Dashboard**: Track loan applications, view financial behavior scores, and manage your profile.
- **Bank Statistics**: Compare your profile against different bank requirements.

## 🏗️ 4-Layer Architecture

CredBud evaluates creditworthiness through four distinct logical layers:

1.  **Transactional Insight Layer**: Analyzes UPI transactions to categorize spending (Food, Medical, Education, EMI, etc.) and calculates a Behavior Score based on spending thresholds.
2.  **Financial Stability Layer**: Evaluates Debt-to-Income (DTI) and EMI-to-Income ratios to ensure the user isn't over-leveraged relative to their monthly earnings.
3.  **Asset Resilience Layer**: Assesses the user's total assets against their total debt (Asset-to-Debt ratio) and considers regional cost-of-living (City Tier) to determine financial cushioning.
4.  **AI Predictive Layer**: A machine learning model (KNN) synthesizes all previous layers' data points into a final approval probability and status.

## 🛠️ Tech Stack

### Backend
- **Framework**: FastAPI (Python)
- **Database**: Supabase (PostgreSQL)
- **Machine Learning**: Scikit-Learn (KNN Classifier), Pandas, Joblib
- **Authentication**: JWT (JSON Web Tokens)
- **Deployment**: Uvicorn

### Frontend
- **Framework**: React 19 (Vite)
- **Styling**: Tailwind CSS
- **Icons**: Lucide React
- **Charts**: Recharts
- **State Management**: React Context API
- **Animations**: Framer Motion

## 🚦 Getting Started

### Prerequisites
- Python 3.9+
- Node.js 18+
- Supabase Account (for Database & Auth)

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd credit-decision-backend
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file based on the settings:
   ```env
   SUPABASE_URL=your_supabase_url
   SUPABASE_KEY=your_supabase_service_role_key
   SUPABASE_ANON_KEY=your_supabase_anon_key
   JWT_SECRET=your_jwt_secret
   JWT_ALGORITHM=HS256
   ```
4. Run the backend server:
   ```bash
   python app/main.py
   ```
   The API will be available at `http://localhost:8000`. You can view the docs at `/api/docs`.

### Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd credit-decision-frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run the development server:
   ```bash
   npm run dev
   ```
   The application will be available at `http://localhost:5173`.

## 📊 Data Model

The system utilizes a balanced feature set for predictions:
- `num_debts`: Number of existing loans/debts.
- `total_debt_amount`: Cumulative debt value.
- `monthly_emis`: Current monthly installment obligations.
- `total_assets`: Total value of user assets.
- `monthly_income`: Net monthly income.
- `city_tier`: Cost of living indicator (Tier 1, 2, or 3).

## 📄 License

This project is licensed under the MIT License.
