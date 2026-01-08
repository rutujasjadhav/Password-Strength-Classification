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
   - Read the password data into a pandas DataFrame and explore basic statistics.
     
2. **Feature engineering**  
   - Compute length and character frequency features (lowercase, uppercase, digits, special characters).   
   - Create a `common_password` feature using a small dictionary of very frequent passwords.  

3. **Label preparation**  
   - Use both numeric strength labels and their mapped text labels (`weak`, `medium`, `strong`) for analysis.   

4. **Train–test split and preprocessing**  
   - Split the dataset into training and testing sets. 
   - Optionally scale or normalize features depending on the chosen algorithm. 

5. **Model training**  
   - Train classification models (e.g., tree-based or other supervised classifiers) to predict password strength from the engineered features. 

6. **Evaluation**  
   - Evaluate model performance using accuracy and other metrics such as confusion matrix and classification report.   

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
