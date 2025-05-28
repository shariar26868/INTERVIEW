# Gut Microbiota Status Prediction

## 📖 Project Overview
This project aims to predict the **current status of gut microbiota** — classified as `Optimal`, `Suboptimal`, or `At Risk` — using structured health-related tabular data. It integrates cutting-edge deep learning models, including **TabTransformer**, alongside traditional machine learning algorithms such as **Logistic Regression**, **Random Forest**, and **XGBoost**.

Key features:
- Detailed Exploratory Data Analysis (EDA)
- Robust preprocessing pipeline with imputation, encoding, and normalization
- Class imbalance handling with SMOTE
- Transformer-based modeling for tabular data
- SHAP-based interpretability for feature importance
- Evaluation using accuracy, F1-score, AUC-ROC, and confusion matrices

Get ready for a **powerful and interactive** microbiota prediction journey!

---

## Dataset Description

Each row in the dataset represents a patient's demographic, lifestyle, and health profile. Features are grouped into:

- **Demographics**:  
  `Height (cm)`, `Weight (kg)`, `BMI`

- **Medical History**:  
  `Medical conditions` (e.g., Diabetes, Hypertension), `Surgeries`, `Family history`

- **Lifestyle**:  
  `Physical activity type`, `Sleep hours`, `Stress level`, `Smoking status`

- **Dietary Habits**:  
  Weekly consumption of `vegetables`, `fermented foods`, `proteins`, `fruits`, `alcohol`, and `daily water intake`

- **Gastrointestinal Health**:  
  `Frequency of bowel movements`, `Stool consistency`, `Presence of bloating`, `gas`, `abdominal pain`

### Target Variable
- **Current status of microbiota**:  
  A multiclass label with values:  
  `Optimal`, `Suboptimal`, `At Risk`

---

## modeling_steps

1. **EDA & Cleaning**
   - Null check, outlier visualization, label distribution
2. **Feature Engineering**
   - Multi-label columns one-hot encoded (e.g., `Medical_conditions`)
   - Standard scaling for numerical features
   - Created features: `Plant_to_Animal_Protein_Ratio`, `Stress_Category`
3. **Train-Test Split**
   - Stratified split into 80% train, 20% test
4. **Modeling**
   - Baselines: Logistic Regression, Random Forest, XGBoost
   - Deep learning: TabTransformer (via PyTorch Tabular)
5. **Evaluation**
   - Accuracy, Precision, Recall, F1-score
   - Confusion Matrix
6. **Interpretability**
   - SHAP values plotted to explain predictions
"""

## Evaluation_results 




![qqqq](https://github.com/user-attachments/assets/d2f8bd97-cb3f-4067-9db3-6c1c8f9c41d6)

"""

# Enhanced prediction guide
prediction_guide = How to Predict

Use the trained TabTransformer model to predict gut microbiota status for new patients. The script prompts for input, with defaults for convenience. Multi-value columns (e.g., `Medical_conditions`) accept comma-separated values or random defaults (0–2 values).

### 🧾 Input Example

```python
input_sample = {
    'Height (cm)': 170,
    'Weight (kg)': 65,
    'BMI': 22.5,
    'Current diet': 'Omnivore',
    'Physical activity type': 'Cardio',
    'Presence of bloating': True,
    'Presence of gas': False,
    'Presence of abdominal pain': False,
    'Daily water intake (liters)': 2.0,
    'Average sleep hours (hours)': 7,
    'Stress level (1-10 scale)': 5,
    'Medical_conditions': 'Diabetes, Anemia',
    'Family history of diseases': 'None',
    'Smoking status (Yes/No, quantity)': 'No',
    'Diagnosed conditions': 'None',
    # ... (other features with defaults)
}
```

### Steps to Predict
1. Run the script (`python gut_prediction.py`).
2. Enter values when prompted or press Enter for defaults.
3. For multi-value columns, input comma-separated values (e.g., `Diabetes, Anemia`) or leave blank for random selection.
4. View the predicted status (e.g., `Predicted: Optimal`).
5. Optionally, view SHAP plots for feature importance.

**Example Interaction**:
```
Enter patient data (leave blank for default):
Height (cm) (e.g., 170): 172
Weight (kg) (e.g., 65): 70
Medical_conditions (e.g., None): Diabetes
...
Predicted Microbiota Status: Suboptimal
Predict another? (yes/no): No
```


**Usage**

1. **Run the Script**:
   - Execute `python_script.py` (TabTransformer implementation).
   - Outputs:
     - **EDA Plots**: `eda_plots/target.png`, `eda_plots/corr.png`, `eda_plots/outliers.png`
     - **Confusion Matrices**: `cm_logistic_regression.png`, `cm_random_forest.png`, `cm_xgboost.png`, `cm_tabtransformer.png`
     - **Model Comparison**: `model_comparison.csv`
     - **SHAP Plot**: `shap_values.png`

2. **Predict for New Patients**:
   - Follow prompts to input patient data.
   - Multi-value columns use comma-separated inputs or random defaults.
   - Results display predicted microbiota status and optional SHAP plots.




