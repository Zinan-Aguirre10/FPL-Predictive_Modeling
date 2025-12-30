# Predictive Fantasy Premier League (FPL) Model

This project builds a predictive model to predict FPL points for every premier league player in the upcoming gameweek. 
The models predict such results using the statstics of historical matches and past player performances. The goal is to 
help FPL managers in their decisions of their squad based on the model's predicted values.

---

## Problem Statement
FPL managers decisions are often based on intuition, recent performance, or bias towards certain teams and players.
This project asks:

> Can historical player and match data from the previous seasons be used to predict future FPL points with reasonable accuracy?

---

## Data
- Historical Premier League player statistics from 2022-2024(minutes played, goals, assists, clean sheets, etc.)
- Match-level features (opponent strength, home/away)
- Data sourced from publicly available FPL datasets

Preprocessing steps include:
- Handling missing values
- Feature normalization
- Create new features focusing on a player's form from the last 5 matches(goals scored last 5, assists last 5, etc.)

---

## Methodology
- Feature engineering on recent form and playing time
- Seperate the data into four based on each position, Goalkeeper, Defender, Midfielder, and Forward
- Models explored: Linear regression (baseline), Regularized regression, ensemble methods(Random Forest and XGBoost)

---

## Results
- Model performance was evaluated on MAE, RMSE, R2 statistic
- XGBoost performed the best in all metrics in comparison to all other models.

(See `report.pdf` for full analysis and plots.)

---

## MILP Optimization 
- Using the XGBoost model, it predicted on the full 2024-2025 FPL season, and a MILP algorithm
  was built to use these values to optimize in squad selection every week.
- This algorithm produced an overall fantasy score that reached top 2% of all FPL managers in the 2024-2025 season.

## Limitations & Future Work
- The model cannot learn injuries until a few gameweeks later after it is shown in the stats of form
- The model can improve in predicting expected points over a few gameweeks rather than the next gameweek,
  in order to improve accuracy and usability for long term management for FPL managers.

## Author
Zinan Aguirre
