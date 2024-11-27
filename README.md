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
git clone https://github.com/your-username/dls-implementation.git
cd dls-implementation
```

### 2. **Install Dependencies**
Use `pip` to install the required Python libraries:
```bash
pip install -r requirements.txt
```

### 3. **Prepare the Dataset**
- Place the dataset in the `data` directory. Ensure the CSV files are formatted as per the expected structure.
- Preprocess the dataset using the provided scripts.

### 4. **Run the Model Training**
Train the models using the provided scripts:
```bash
python train_dl_models.py
```

### 5. **Inference**
Run the inference script for ODIs or T20Is:
```bash
python inference.py
```

### 6. **Launch the Web App**
To use the Streamlit web application:
```bash
streamlit run app.py
```

---

## Directory Structure

```
dls-implementation/
│
├── data/                       # Dataset folder (store raw and preprocessed data here)
│   ├── raw_data.csv            # Raw dataset
│   ├── processed_data.csv      # Preprocessed dataset
│
├── src/                        # Source code folder
│   ├── main.py                 # Main functions for DLS/DL-STD/DL-PRO implementation
│   ├── train_dl_models.py      # Training script for models
│   ├── inference.py            # Inference for ODIs and T20Is
│   ├── app.py                  # Streamlit app for predictions
│
├── results/                    # Folder to store results
│   ├── graphs/                 # Visualizations and result graphs
│   ├── outputs/                # Output predictions
│
├── tests/                      # Unit tests for the code
│   ├── test_main.py            # Tests for main functionality
│
├── README.md                   # Project documentation
├── requirements.txt            # Python dependencies
└── LICENSE                     # License file
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

## Examples

### ODI Scenario
```python
team1_score = 350
team2_wicktes_down = 2
team2_overs_completed = 10
lost_overs_due_to_rain = 5

print(inference_ODI(Z_dls_params, Z_std_params, team1_score, team2_wicktes_down, team2_overs_completed, lost_overs_due_to_rain, method='DLS'))
```

### T20I Scenario
```python
team1_score = 139
team2_wicktes_down = 2
team2_overs_completed = 6.5
lost_overs_due_to_rain = 13.1

print(inference_T20I(Z_dls_params, Z_std_params, team1_score, team2_wicktes_down, team2_overs_completed, lost_overs_due_to_rain, method='DLS'))
```

---

## Limitations and Future Work

- **T20 Matches**: The method for T20 matches is adapted from ODI logic. More research is needed for T20-specific scenarios.
- **Isoprobability Criterion**: The current DLS method does not consider this, which can be an area for future improvement.
- **Win Probability**: The logistic regression model can be improved by incorporating probabilistic analysis for better predictions.

---

## References

1. Duckworth, F. C., & Lewis, A. J. (1998). A fair method for resetting the target in interrupted one-day cricket matches.
2. Duckworth, F. C., & Lewis, A. J. (2004). A successful operational research intervention in one-day cricket.
3. Stern, S. E. (2016). The Duckworth-Lewis-Stern method: Extending the Duckworth-Lewis methodology to deal with modern scoring rates. 

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

--- 

Feel free to contribute to this project by submitting issues or creating pull requests. Happy coding! 😊