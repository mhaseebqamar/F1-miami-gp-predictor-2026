# 🏎️ F1 Miami Grand Prix 2026: Predictive Ensemble Framework
### Advanced Analytics & Big Data | SGH Warsaw School of Economics

## 📊 Project Overview
This project develops a robust predictive framework to forecast the Top 5 finishers of the **2026 Formula 1 Miami Grand Prix**. The core philosophy of this study is that a single model is insufficient for the high-volatility environment of F1. Instead, we implement a **consensus-based ensemble** that balances human domain expertise with state-of-the-art machine learning.

---

## 🛠️ The 5-Method Predictive Pipeline
To maximize accuracy and minimize model bias, the final forecast is derived from five distinct methodologies, each selected for a specific statistical purpose:

| Method | Strategic "Why" |
| :--- | :--- |
| **Weighted Scoring** | Serves as a **transparent baseline**; allows us to manually calibrate the importance of current season form vs. car performance. |
| **Linear Regression** | Enables the model to **automatically learn feature importance**, removing manual bias in determining which variables drive success. |
| **Random Forest** | Selected for its ability to handle **complex non-linear relationships** that traditional straight-line models often miss. |
| **XGBoost** | The **industry standard for tabular data**; utilized for its high accuracy and efficiency in small-scale sports datasets. |
| **Monte Carlo Simulation** | Moves beyond "deterministic guesses" by **simulating the race 10,000 times**, providing a realistic probability distribution of outcomes. |

---

## 🚀 Key Features
* **Multi-Method Consensus:** Final predictions are a weighted ensemble, neutralizing the weaknesses of any single algorithm.
* **Probabilistic Outcomes:** Rather than a static list, the model generates "Win/Top-5 Probabilities" (e.g., George Russell at 96% confidence).
* **High-Stakes Application:** Designed specifically for the 2026 technical regulation era, prioritizing current constructor standings and recent momentum.

---

## 🏁 Final Forecast (Consensus Top 5)
Based on the ensemble output, the high-probability finishers for the 2026 Miami GP are:

1.  **George Russell** (Mercedes) — *96% Prob.*
2.  **Lewis Hamilton** (Mercedes) — *93% Prob.*
3.  **Charles Leclerc** (Ferrari) — *89% Prob.*
4.  **Oscar Piastri** (McLaren)
5.  **Pierre Gasly** (Alpine)

---

## 📂 Project Structure
* `F1 Miami.ipynb`: Full research notebook including feature engineering, model training, and ensemble logic.
* `data/`: Curated dataset including 2026 Constructor points and historical Miami GP results (2022-2025).
* `outputs/`: Visualization plots showing the convergence of ML predictions and Monte Carlo distributions.

---

## 💻 Tech Stack
* **Language:** Python
* **ML Frameworks:** Scikit-Learn, XGBoost
* **Simulation:** NumPy (Vectorized Monte Carlo)
* **Data Processing:** Pandas
