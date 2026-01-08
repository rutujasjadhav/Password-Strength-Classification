# Password Strength Classification

This project builds a machine learning model to classify the strength of user passwords into categories such as **weak**, **medium**, and **strong** using a labeled password dataset and engineered character-based features. 

## Project Overview

The goal is to automatically assess password strength based on its composition instead of using only simple rule-based checks like length or character sets.  
Using a dataset of real-world passwords and their assigned strength labels, the project engineers several features (length, character frequencies, and common-password flags) and trains classification models to predict the strength class. 

## Dataset

The notebook uses a password dataset where each record has: 

- `password`: The raw password string.  
- `strength`: A label indicating password strength (originally numeric and also mapped to `weak`, `medium`, `strong`). 

Additional engineered features include: 

- `length`: Total number of characters. 
- `freq_lower_case`: Proportion of lowercase letters. 
- `freq_upper_case`: Proportion of uppercase letters. 
- `freq_digit`: Proportion of digits. 
- `freq_special_char`: Proportion of special characters. 
- `common_password`: Indicator if the password appears in a small list of very common passwords (e.g., `password`, `123456`, `qwerty`). 

> Note: The dataset is loaded directly in the notebook; if you want to run it independently, place the CSV file in the project directory and update the path in the notebook. 

## Methodology

The main steps in the notebook are: 

1. **Data loading and inspection**  
2. **Feature engineering**  
3. **Train–test split and preprocessing**  
4. **Model training**   
5. **Evaluation**  

## Model Comparison

- **Logistic Regression**
  - Simple and interpretable baseline model
  - Fast to train but limited to linear decision boundaries
  - Struggles with complex, non-linear feature interactions

- **Random Forest Classifier**
  - Captures non-linear relationships between password features
  - Strong performance across all three classes (`weak`, `medium`, `strong`)
  - Provides feature importance for better interpretability

- **Gradient Boosting / XGBoost**
  - Boosting-based ensemble model with higher predictive power
  - Slightly better accuracy at the cost of increased training time
  - Requires more hyperparameter tuning

**Evaluation Metrics**
- Accuracy
- Precision, Recall, and F1-score
- Confusion Matrix

**Final Model Selection**
- Tree-based models outperformed Logistic Regression, especially for the `weak` and `strong` classes.
- **Random Forest Classifier** was chosen as the final model due to its balanced accuracy, robustness across classes, and interpretable feature importance.


## Installation and Usage

### Prerequisites

Make sure you have the following installed:

- Python 3.x  
- Jupyter Notebook or JupyterLab  
- Common Python libraries:
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`
  - `seaborn` 

You can install the typical dependencies with:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
