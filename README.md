# 🏎️ F1 Miami Grand Prix 2026: Predictive Ensemble Framework
### Advanced Analytics & Big Data | SGH Warsaw School of Economics

## 📊 Project Overview
This project develops a robust predictive framework to forecast the Top 5 finishers of the **2026 Formula 1 Miami Grand Prix**. The core philosophy of this study is that a single model is insufficient for the high-volatility environment of F1. Instead, we implement a **consensus-based ensemble** that balances human domain expertise with state-of-the-art machine learning.

---

## 🛠️ The 5-Method Predictive Pipeline
To maximize accuracy and minimize model bias, the final forecast is derived from five distinct methodologies, each selected for a specific statistical purpose:

| Method | Strategic "Why" |
| :--- | :--- |
| **Weighted Scoring** | Serves as a **transparent baseline**; allows for manual calibration of current season form vs. car performance. |
| **Linear Regression** | Enables the model to **automatically learn feature importance**, removing manual bias in determining which variables drive success. |
| **Random Forest** | Selected for its ability to handle **complex non-linear relationships** that traditional straight-line models often miss. |
| **XGBoost** | The **industry standard for tabular data**; utilized for its high accuracy and efficiency in small-scale sports datasets. |
| **Monte Carlo Simulation** | Moves beyond "deterministic guesses" by **simulating the race 10,000 times**, providing a realistic probability distribution of outcomes. |

---

## 🏁 Final Forecast: Predicted Top 5
Based on the ensemble output and current 2026 season data, the high-probability finishers for the Miami GP are:

| Place | Driver | Team | Key Justification |
| :--- | :--- | :--- | :--- |
| 🥇 **1st** | **Kimi Antonelli** | Mercedes | Championship leader (72 pts); won last 2 consecutive races; dominant Mercedes car (135 constructor pts). |
| 🥈 **2nd** | **George Russell** | Mercedes | P2 in standings (63 pts); winner in Australia; benefits from the same dominant W17 chassis. |
| 🥉 **3rd** | **Charles Leclerc** | Ferrari | P3 in standings (49 pts); high consistency with podiums in all 3 opening races. |
| 🏅 **4th** | **Lewis Hamilton** | Ferrari | P4 in standings (41 pts); most experienced driver on the grid with 6 Miami GP starts. |
| 🏅 **5th** | **Pierre Gasly** | Alpine | Consistent points scorer; P7 in Japan; underrated pace given Alpine’s competitive mid-season upgrades. |

---

## 🚀 Key Insights & Limitations
* **Mercedes Dominance:** The Mercedes car advantage (135 pts vs. Ferrari's 90) is currently the single strongest predictor of success in the 2026 regulation era.
* **Probabilistic Confidence:** Monte Carlo simulations show extremely high confidence (93%+) for the top 3 finishers, with significant variance emerging at P4 and P5.
* **Model Constraints:** As this was conducted early in the season, the small sample size (3 races) remains a limitation. The model also accounts for "Sprint Weekend" variance through probabilistic weighting.

---

## 📂 Project Structure
* `F1 Miami.ipynb`: Full research notebook including feature engineering, model training, and ensemble logic.
* `data/`: Curated dataset including 2026 Constructor points and historical Miami GP results (2022-2025).
* `visualizations/`: Plots showing the convergence of ML predictions and Monte Carlo distributions.

---

## 💻 Tech Stack
* **Language:** Python
* **ML Frameworks:** Scikit-Learn, XGBoost
* **Simulation:** NumPy (Vectorized Monte Carlo)
* **Data Processing:** Pandas
