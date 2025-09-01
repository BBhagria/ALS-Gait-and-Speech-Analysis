# ALS Gait and Speech Analysis

## 📌 Project Overview
This project aims to analyze **gait and speech signals** from ALS patients to predict disease progression and functional outcomes. Using wearable and digital health technologies, we engineer features (slopes, variability, baseline change) from time-series data and evaluate predictive models for clinical decision support.

The analysis contributes to the **Precision ALS** research initiative by developing interpretable models that can be integrated with digital biomarkers for monitoring Motor Neuron Disease (MND).

---

## ⚙️ Workflow

1. **Data Integration**
   - Merged multimodal datasets (gait, speech, clinical outcomes).
   - Handled missing values via regression and median imputation.

2. **Feature Engineering**
   - Slope (rate of change of signals over time).
   - Variability (spread/variance in signals).
   - Baseline change (difference from initial measurement).

3. **Outlier Detection**
   - Univariate outliers → Z-score & IQR.
   - Multivariate outliers → Mahalanobis distance.

4. **Feature Analysis**
   - Distribution checks & skewness corrections.
   - Correlation heatmaps → removal of redundant features.

5. **Baseline Models**
   - Logistic Regression.
   - Random Forest.
   - XGBoost (comparative).

6. **Model Evaluation**
   - Metrics: Accuracy, ROC AUC, Precision, Recall, F1-score.
   - Calibration curves & Brier scores for probability reliability.
   - Stratified 5-Fold Cross Validation for robustness.

7. **Feature Importance & Selection**
   - Logistic Regression odds ratios.
   - Random Forest & XGBoost feature importances.
   - Selection of clinically relevant predictors.

8. **Final Model**
   - Logistic Regression (regularized, calibrated).
   - Balanced performance with high ROC AUC (~0.91) and interpretable coefficients.

---

## 📊 Key Results

- Logistic Regression (with feature selection) outperformed Random Forest and XGBoost in this dataset.
- ROC AUC: ~0.91, F1 Score: ~0.83 after calibration.
- Important predictors: **MD_score, rolling_vol_acc, slope_pitch, rolling_pitch_vol**.
- Calibration showed improved reliability of probability outputs.

---

## 🧩 Clinical Relevance
- **Interpretability**: Odds ratios allow clinicians to see how features (e.g., gait slope, speech variability) affect disease outcome risk.
- **Practical Use**: Supports ALS monitoring with digital biomarkers and home-based assessments.
- **Integration**: Can be extended into the Precision ALS platform for longitudinal monitoring.

---

## 🚀 Next Steps
- Validate on **external datasets** to ensure generalizability.
- Explore **threshold tuning** with clinicians (high recall vs. high precision tradeoff).
- Extend feature engineering to cover additional modalities: strength, respiration, dexterity.
- Deploy as a pipeline (scaler + model + calibration) for integration into clinical systems.

---

## 📂 Repository Structure
```
├── ALS Gait and Speech Analysis.ipynb   # Main analysis notebook
├── data/                                # Raw & processed datasets
├── models/                              # Trained model artifacts
├── results/                             # Metrics, plots, calibration curves
└── README.md                            # Project documentation
```

---

## 🔧 Requirements
- Python 3.9+
- Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `xgboost`, `joblib`

Install dependencies with:
```bash
pip install -r requirements.txt
```

---

## 👤 Author
Bhavesh [Data Scientist Candidate – Precision ALS]
