# ✈️ Flight Delay Prediction — Ensemble Model Approach

This project aims to predict whether a flight will be delayed or not, using a **regression-to-classification pipeline** with ensemble learning models. The work was developed in a single notebook (`Flight_delay.ipynb`) and includes data generation, feature engineering, model training, and evaluation.

---

## 🧠 Problem Statement

Given flight attributes (e.g., departure time, origin/destination, airline carrier), the goal is to **predict the delay in minutes**, and then **classify** whether the delay exceeds 15 minutes — defining it as "Delayed".

---

## 📁 File Overview

- `Flight_delay.ipynb` — Main notebook containing all logic and results
- No external datasets used; data is generated synthetically using pandas/NumPy

---

## 📊 Features Engineered

- **FlightDate**: Converted to day of week and month
- **CRSDepTime**: Extracted departure hour
- **ArrDelay, DepDelay**: Target and explanatory features
- **Origin, Destination, Carrier**: One-hot encoded
- **Synthetic fields**: Generated using NumPy

---

## 🧪 Model Details

The following machine learning model was used:

- 🔹 `GradientBoostingRegressor` (from `sklearn.ensemble`)

### Target Conversion:
- Predicted delay (continuous value)
- Then converted to `"Delayed"` or `"Not Delayed"` using a **15-minute threshold**

---

## 📈 Evaluation

While the regressor predicts delay minutes, it is evaluated as a **classification task** by converting predictions into binary values:

| Metric             | Description                        |
|--------------------|------------------------------------|
| Prediction Output  | Delay in minutes (regression)      |
| Classification     | Delay > 15 mins → Delayed          |
| Evaluation         | First 5 predictions vs. threshold  |
| Visuals            | N/A (basic print output only)      |

---

## 🧾 Example Output


First 5 regression predictions (delay in minutes):
[21.0, 0.02, 2.01, 48.96, 17.00]

First 5 classifications:
['Delayed', 'Not Delayed', 'Not Delayed', 'Delayed', 'Delayed']
