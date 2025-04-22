# 🚀 Driven to Predict: Racing meets Statistics

A data-driven exploration of Formula 1 racing — combining statistical modeling and machine learning to predict race outcomes, cluster driver archetypes, and analyze the importance of starting grid positions.

---

## 📂 Project Overview

This project addresses three key research questions:

1. **Lap Time Prediction**  
   Predicting lap times using historical race data, circuit characteristics, and driver performance metrics through regression models.

2. **Driver Clustering**  
   Using unsupervised learning (K-means clustering) to identify different types of Formula 1 drivers based on racing behavior, pit stop frequency, consistency, and overtaking statistics.

3. **Impact of Grid Position on Race Outcome**  
   Statistical testing to understand how starting positions influence the likelihood of winning a race.

---

## 📊 Methodology

### 🏎️ 1. Lap Time Prediction
- **Data Used:** Lap times, driver and constructor information, race metadata, pit stops.
- **Techniques:** Linear Regression (Baseline), XGBoost Regression (Advanced).
- **Key Features:**  
  - Driver age, grid position, constructor performance, circuit altitude & geography, pit stop influence, lap position in the race.
- **Results:**  
  - RMSE (Root Mean Squared Error):
    - Linear Regression: ~1935 ms  
    - XGBoost Regression: ~1600 ms  
  - XGBoost outperformed linear regression in predictive accuracy.

---

### 🧑‍🏫 2. Clustering Drivers by Racing Style
- **Goal:** Classify F1 drivers into distinct groups based on race metrics:
  - Average lap time
  - Lap time consistency (standard deviation)
  - Average pit stops per race
  - Average positions gained per race
- **Method:** K-means Clustering with Elbow Method (optimal K = 5).
- **Cluster Archetypes Identified:**
  1. Efficient Overtakers  
  2. Short Run Strategists (fast but small group)  
  3. Mid-Pack Movers  
  4. Baseline Finishers (largest group)  
  5. Slower but Stable  
- **Cluster Validation:** Silhouette Score analysis for cohesion and separation.

---

### 🏁 3. Impact of Grid Position on Race Outcome
- **Hypothesis:** Does starting in the Top 5 significantly increase the chance of winning?
- **Approach:**  
  - Chi-square test of independence.
  - Win rate comparisons using Wilson confidence intervals.
  - Cramér’s V to measure effect size.
- **Findings:**
  - Top 5 starters have a **17.5%** win rate (95% CI: 15.7–19.5%).
  - Lower grid starters have a **0.47%** win rate (95% CI: 0.31–0.72%).
  - **Cramér’s V = 0.34**, suggesting a moderate association between grid position and win likelihood.

---

## 📂 Data Sources
- Formula 1 historical datasets:
  - `results.csv`
  - `drivers.csv`
  - `constructors.csv`
  - `races.csv`
  - `circuits.csv`
  - `lap_times.csv`
  - `pit_stops.csv`

---

## ⚙️ Tech Stack

- **Language:** R  
- **Key Libraries:**  
  `dplyr`, `tidyr`, `lubridate`, `caret`, `xgboost`, `Matrix`, `ggplot2`, `ggthemes`, `factoextra`, `cluster`, `binom`, `vcd`, `kableExtra`, etc.

---

## 📌 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/f1-lap-time-prediction.git
   cd f1-lap-time-prediction
