# F1 Miami Grand Prix 2026: Top 5 Prediction with Five Methods

An individual project (SGH Warsaw School of Economics, MSc Advanced Analytics & Big Data, 2025/26) that predicts the top 5 finishers of the 2026 Formula 1 Miami Grand Prix (3 May 2026) using five methods: weighted scoring, Linear Regression, Random Forest, XGBoost and a Monte Carlo race simulation, combined by rank averaging. The project was submitted under the team alias "UnderCut"; I was the only member.

## Project context

This was a pre-race prediction task: the forecast had to be made before the race, using data available after Round 3 of the 2026 season (29 March 2026). With only three races completed, no ready-made dataset existed, so the data was entered manually from official F1 results. The project is mainly an exercise in combining very different method types (rule-based, machine learning and simulation) on a very small dataset, and in seeing what that combination can and cannot add.

## Data

* **2026 race results** for all 20 drivers: Australia (R1), China (R2), Japan (R3); DNF/DNS encoded as 20
* **2026 drivers' and constructors' championship points** after Round 3
* **Miami GP history 2022–2025** for drivers with previous Miami starts (partial; see limitations)

## Features (8)

| Feature | What it captures |
|---|---|
| `Points_2026` | Season form |
| `avg_finish_2026` | Average finish over 3 races (DNF counted as 15) |
| `recent_form` | Japan result |
| `momentum` | Change from Australia to Japan |
| `races_finished` | Reliability (finishes out of 3) |
| `constructor_pts` | Car strength |
| `miami_avg_pos` | Average Miami finish (DNFs excluded) |
| `miami_races_finished` | Miami finishes |

## Methods

1. **Weighted scoring**: hand-set weights (points 30%, average finish 25%, constructor 20%, Miami record 15%, momentum 7%, reliability 3%) on normalised features
2. **Linear Regression** (scikit-learn, MinMax-scaled features)
3. **Random Forest** (500 trees, max depth 5)
4. **XGBoost** (300 trees, max depth 3, learning rate 0.05)
5. **Monte Carlo simulation**: 10,000 simulated races; each driver's base performance (2026 average finish with small Miami and car adjustments) plus Gaussian noise (σ = 3.5 positions) and random DNFs based on each driver's 2026 retirement rate

Models 2–4 use `avg_finish_2026` as the target and are trained and scored on the same 20 drivers. The final prediction averages the five rank orders with equal weights.

## Prediction (made before the race)

| Place | Driver | Team | Monte Carlo top-5 probability |
|---|---|---|---|
| 1 | Antonelli | Mercedes | 96.9% |
| 2 | Russell | Mercedes | 96.0% |
| 3 | Leclerc | Ferrari | 92.6% |
| 4 | Hamilton | Ferrari | 81.0% |
| 5 | Gasly | Alpine | 33.5% |

All five methods placed Antonelli, Russell, Leclerc and Hamilton in positions 1–4. Four of five methods had Gasly fifth; the weighted scoring method had Piastri fifth instead.

## Outcome

Antonelli won the race, as predicted. The other four predicted positions did not match the actual result.

## What the method comparison actually shows

* **The three machine learning models mostly reproduced one feature.** Their target, `avg_finish_2026`, is also one of their inputs. Linear Regression put all its weight on that feature (every other coefficient is effectively zero), and it was also the top feature for Random Forest (0.46) and XGBoost (0.45). Their rankings are therefore close to a simple sort by 2026 average finish.
* **The Monte Carlo simulation starts from the same average finish**, so its agreement with the other methods is not independent evidence either. The high top-5 probabilities reflect the assumed noise level (σ = 3.5), which was set by judgement rather than estimated from data.
* **The agreement across methods mostly reflects shared inputs, not confirmation.** The method that differed most, the hand-weighted score, was the only one that brought in a different driver (Piastri).
* **With three races of data, the 2026 standings dominated everything.** Miami history added almost nothing (importance ≤ 0.005 in both tree models), which is consistent with the new 2026 regulations making older Miami results less relevant.

## Tech stack

* Python, Jupyter Notebook
* pandas, NumPy (including the vectorised Monte Carlo noise)
* scikit-learn: Linear Regression, Random Forest, MinMaxScaler
* XGBoost
* Matplotlib

## Project structure

```
F1-miami-gp-predictor-2026/
├── F1 Miami.ipynb     # Full notebook: data entry → features → EDA → 5 methods → ensemble → summary
└── README.md
```

All data is entered directly in the notebook, so no external file is needed. Running all cells reproduces the results (random seed 42).

## Honest limitations

* **Very small dataset**: 20 drivers and 3 races. The ML models were fitted and scored on the same 20 rows, with no hold-out data.
* **Target overlap**: the ML target (`avg_finish_2026`) is also a feature, as explained above.
* **Partial Miami history**: only some drivers' past Miami results were entered, and several finishes outside the top 10 were coded as 20 (the DNF value).
* **Assumed simulation parameters**: the Monte Carlo noise level, DNF cap (60%) and adjustment sizes were set by judgement.
* **Unmodelled race factors**: sprint-weekend format, qualifying, safety cars, weather and strategy.
