# Duckworth-Lewis-Stern Implementation and Analysis

This repository implements and analyzes the Duckworth-Lewis-Stern (DLS) Method along with its predecessors, Duckworth-Lewis Standard (DL-STD) and Duckworth-Lewis Professional (DL-PRO). The DLS Method is an advanced algorithm used in cricket to calculate revised targets for interrupted matches, incorporating modern scoring trends and other key parameters.

---

## Methodology

1. **Data Preparation**:
   - Raw cricket ball-by-ball data from 2000–2023 is processed to generate relevant features like overs remaining, wickets lost, and runs remaining.
   - A curated dataset is used for both One Day Internationals (ODIs) and T20 Internationals (T20Is).

2. **Mathematical Models**:
   - **DL Standard (DL-STD)**: Uses a simple exponential decay formula based on overs remaining and wickets lost.
   - **DL Professional (DL-PRO)**: Enhances DL-STD by introducing a match factor (\(\lambda\)) for high-scoring games.
   - **Duckworth-Lewis-Stern (DLS)**: Further adapts DL-PRO by introducing overs and match factor-dependent adjustments.

3. **Win Prediction Model**:
   - A logistic regression model predicts the win probability during the second innings based on overs remaining, wickets in hand, and run rates.

4. **Web Application**:
   - The project includes a Streamlit-based web app for real-time target and par-score predictions.

---

## How to Run the Code

### 1. **Clone the Repository**
```bash
git clone https://github.com/chinmayjainnnn/DLS_implementation/.git
```

### 2. **Install Dependencies**
Use `pip` to install the required Python libraries:
```bash
pip install -r requirements.txt
```
---

## Features

1. **Model Implementation**:
   - Implements DL-STD, DL-PRO, and DLS methods using Python.
   - Incorporates non-linear regression to fit model parameters.

2. **Inference for Match Interruptions**:
   - Predicts revised targets using real-world scenarios for both ODIs and T20Is.
   - Supports predictions using DL-STD, DL-PRO, and DLS methods.

3. **Visualization**:
   - Generates graphs comparing predicted vs. actual data to validate the models.

4. **Web App**:
   - Interactive interface for real-time score and win probability prediction.

---

## References

1. Duckworth, F. C., & Lewis, A. J. (1998). A fair method for resetting the target in interrupted one-day cricket matches.
2. Duckworth, F. C., & Lewis, A. J. (2004). A successful operational research intervention in one-day cricket.
3. Stern, S. E. (2016). The Duckworth-Lewis-Stern method: Extending the Duckworth-Lewis methodology to deal with modern scoring rates. 

---
