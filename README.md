# 🏎️ F1 Miami Grand Prix 2026: Predictive Ensemble Modeling
### Advanced Analytics & Big Data | SGH Warsaw School of Economics

## 📊 Project Overview
This project develops a robust predictive framework to forecast the Top 5 finishers of the **2026 Formula 1 Miami Grand Prix**. By utilizing an ensemble of five distinct data science methodologies, the model compensates for the inherent volatility and "small sample size" issues common in early-season sports forecasting.

The objective was to move beyond a single model and create a consensus prediction backed by rule-based scoring, machine learning, and probabilistic simulations.

---

## 🛠️ The 5-Method Ensemble Architecture
To maximize predictive accuracy, the project implements an **Ensemble Approach**:

1.  **Rule-Based Scoring (Current Form):** A weighted matrix prioritizing recent 2026 performance and Constructor standings.
2.  **Historical Track Specialist Analysis:** A weighted decay model looking at driver performance at the Miami International Autodrome from 2022–2025.
3.  **Machine Learning (Random Forest):** A classification approach trained on historical race features to identify high-probability Top 5 candidates.
4.  **Elo Rating System:** A dynamic "strength-of-schedule" ranking that updates driver quality based on head-to-head results.
5.  **Monte Carlo Simulation:** 10,000 iterations simulating race-day variance, safety cars, and strategy errors to generate probability distributions for finishing positions.

---

## 🚀 Key Features
* **Multi-Method Consensus:** The final forecast is an ensemble of all five methods, reducing the risk of "overfitting" to a single statistical quirk.
* **2026 Regulation Modeling:** Accounts for the significant technical regulation changes of 2026, giving higher weight to current car performance over historical data.
* **Probabilistic Outcomes:** Provides specific probability percentages (e.g., "96% Top-5 probability for Russell") rather than just a flat list.
* **Strategic Limitation Analysis:** Includes a detailed section on model constraints, such as "Sprint Weekend" formats and unmodeled "Safety Car" events.

---

## 🏁 Final Forecast (Consensus Top 5)
Based on the ensemble output, the high-probability finishers for the 2026 Miami GP are:

1.  **George Russell** (Mercedes) - *96% Prob.*
2.  **Lewis Hamilton** (Mercedes) - *93% Prob.*
3.  **Charles Leclerc** (Ferrari) - *89% Prob.*
4.  **Oscar Piastri** (McLaren)
5.  **Pierre Gasly** (Alpine)

---

## 📂 Project Structure
* `F1 Miami.ipynb`: Full research notebook including data cleaning, method implementation, and ensemble logic.
* `data/`: Curated dataset including 2026 Constructor points and 2022-2025 Miami historical results.
* `visualizations/`: Plots showing the convergence of different model methods.

---

## 💻 Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib
* **Methods:** Random Forest, Monte Carlo Simulation, XGBoost, Weighted Scoring.
