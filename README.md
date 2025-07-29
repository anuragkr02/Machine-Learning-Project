Fertilizer Prediction Model
This project predicts the top-3 recommended fertilizers for given crop and soil conditions using machine learning. The model is trained on an agricultural dataset (train.csv), tested on an unseen dataset (test.csv), and produces predictions suitable for submission in a competition format.

Table of Contents
Project Structure

Setup and Requirements

Data Description

Approach

How to Run

Outputs

References

Project Structure
Predicting_Fertilizers.ipynb — Main notebook containing code for data preprocessing, model training, evaluation, and prediction.

train.csv — Training dataset with labeled fertilizer recommendations.

test.csv — Testing dataset without fertilizer label.

Submission_File.csv — Output file with predicted fertilizer recommendations for test set.

Setup and Requirements
Python 3.7+

Libraries:

pandas

numpy

seaborn

matplotlib

scikit-learn

xgboost

Install all requirements with:

bash
pip install -r requirements.txt
Data Description
Each data point includes:

Temparature: Numeric value.

Humidity: Numeric value.

Moisture: Numeric value.

Soil Type: Categorical variable.

Crop Type: Categorical variable.

Nitrogen, Potassium, Phosphorous: Numeric soil nutrients.

Fertilizer Name: (train only) Target categorical variable.

Approach
Exploratory Data Analysis

Visualized missing values and target distribution.

Analyzed correlation among features.

Preprocessing

Handled missing values (if any exist).

Label-encoded categorical variables for both train and test data.

Standard-scaled numerical features.

Modeling

Used XGBoost classifier for multi-class prediction (multi:softprob).

Stratified data split for train/validation to preserve class distribution.

Hyperparameter tuning with early stopping and regularization to prevent overfitting.

Evaluation

Evaluated performance using MAP@3 (mean average precision at 3), i.e., correct fertilizer predictions among the top-3 recommended.

Prediction

Produced top-3 fertilizer recommendations per input row in test.csv.

Saved submission file for further evaluation.

How to Run
Place train.csv and test.csv in the project directory.

Open and run all cells in Predicting_Fertilizers.ipynb sequentially.

The final output will be saved as Submission_File.csv.

Outputs
Submission_File.csv: Contains two columns:

id: Sample identifier.

Fertilizer Name: Space-separated, top-3 predicted fertilizer names for each test sample.

References
The code includes extensive comments and plots for EDA, correlation, and model evaluation.

All code is provided in the notebook for full reproducibility
