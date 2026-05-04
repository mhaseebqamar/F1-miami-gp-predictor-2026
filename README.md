🏎️ 2026 Miami Grand Prix Predictive Modeling

Project Overview
This project focuses on predicting the outcome of the 2026 Miami Grand Prix using an ensemble of machine learning models. Predicting F1 results early in a season is a "small data" challenge. This repository demonstrates how to use Feature Engineering and Probabilistic Simulations to overcome data scarcity.  

🧠 The Ensemble Approach
To ensure a robust prediction, I utilized five distinct analytical methods:

Weighted Scoring: Domain-driven baseline.

Linear Regression: Historical trend analysis.

Random Forest: Capturing complex non-linear relationships.

XGBoost: High-performance gradient boosting for tabular data.

Monte Carlo Simulation: 10,000 iterations to account for race-day randomness (DNFs, Safety Cars).

🛠️ Feature Engineering
The "secret sauce" of this model lies in the custom metrics engineered to handle the 2026 season's early data:

Recent Form: A decay-weighted average of the first three races (eg, Japan GP).

Constructor Strength: A coefficient representing the car's 70% impact on race pace.

Reliability Index: Quantitative penalty based on historical DNF (Did Not Finish) frequency.

🏆 Key Findings: The "Antonelli" Surge
While traditional metrics favored veterans, the XGBoost and Weighted Scoring layers identified Kimi Antonelli (Mercedes) as the predictive winner. This was driven by:

High "Momentum" scores from the opening rounds.

Mercedes' technical upgrade trajectory.

Track-specific suitability for the W17 chassis.

🚀 Technical Stack
Language: Python

Libraries: pandas , scikit-learn, xgboost, numpy,matplotlib

Environment: Developed as part of the Advanced Analytics curriculum.  

📂 File Structure
data/: Cleaned F1 datasets.

notebooks/: Step-by-step EDA and Model Training.

src/: Python scripts for the Monte Carlo simulation.

results/: Final prediction tables and visualizations.
