# MLB Team Win Percentage Predictor

A traditional ML project using historical Lahman baseball data to predict team win percentages. Built as a learning project to practice the full ML pipeline with real sports data.

## Project Goals
- Practice end-to-end traditional ML workflow (EDA → feature engineering → modeling → interpretation)
- Build an interpretable model using XGBoost + SHAP
- Create a simple 2026 mid-season win percentage projector using current standings

## Results

**Final Model Performance** (tested on 2020+ seasons)
- MAE: 0.0209 (~3.4 wins error over a full season)
- RMSE: 0.0270
- R²: 0.8938

This is significantly better than the naive baseline (MAE 0.0661).

### Key Insights from SHAP
- `run_diff` (Runs Scored - Runs Allowed) is by far the most important feature — as expected in baseball analytics.
- `run_ratio` and Pythagorean win % also show strong influence.
- Bullpen strength (`SV`) contributes meaningfully.

## Project Structure

mlb-win-predictor/
├── data/                  # Lahman CSVs (ignored in git)
├── notebooks/
│   ├── 01_eda.ipynb       # Data exploration + feature engineering
│   └── 02_modeling.ipynb  # (coming soon) Final modeling + SHAP
├── src/                   # reusable functions (optional)
├── README.md
├── requirements.txt
└── .gitignore

## How to Reproduce

1. Clone the repo
2. Download the latest Lahman Database and place CSVs in `/data/`
3. Create and activate virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate    # Windows
   # source venv/bin/activate   # macOS/Linux

## Install Dependencies

pip install -r requirements.txt

