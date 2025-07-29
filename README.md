🌱 Fertilizer Prediction Model
Unlock optimal crop yields with smart fertilizer recommendations! This machine learning project predicts the top-3 fertilizers for any given crop and soil condition, streamlining the decision-making process for farmers and agronomists.

📚 Table of Contents
  1.Project Structure
  2.Setup & Requirements
  3.Data Description
  4.Approach
  5.How to Run
  6.Outputs
  7.References

  🗂️ Project Structure
      File/Folder	Description
      Predicting_Fertilizers.ipynb	Jupyter notebook for data processing, modeling, and prediction.
      train.csv	Training data with fertilizer labels.
      test.csv	Unlabeled data for predictions.
      Submission_File.csv	Output: test set with top-3 predicted fertilizers per sample.

  ⚙️ Setup & Requirements
      Python 3.7+
      Required libraries:
      pandas
      numpy
      seaborn
      matplotlib
      scikit-learn
      xgboost    
      
🌾 Data Description
   Each record in the dataset contains:
   Temperature: Numeric
   Humidity: Numeric
   Moisture: Numeric
   Soil Type: Categorical (e.g., clay, loam)
   Crop Type: Categorical (e.g., wheat, rice)
   Nitrogen, Phosphorous, Potassium: Numeric nutrient values
   Fertilizer Name: (train only) Target label

   🔎 Approach
      A) Exploratory Data Analysis (EDA)
      1.Visual inspection of missing values & fertilizer distribution
      2.Feature correlation analysis with informative plots
      B) Data Preprocessing
      1.Impute or handle missing values
      2.Label encode categorical features (soil, crop types)
      3.Standardize numerical data for better model performance
      C) Modeling
      1.Utilize an XGBoost multi-class classifier (multi:softprob)
      2.Preserve label distribution using stratified train-validation split
      3.Tune hyperparameters with early stopping & regularization to avoid overfitting
      D) Evaluation
      1.Assess with MAP@3 (Mean Average Precision at top 3 recommendations)
      E) Prediction Workflow
      1.Output top-3 fertilizer predictions per test case
      2.Export results in the required competition submission format

   📤 Outputs
       Submission_File.csv
       --> id: Sample identifier
       --> Fertilizer Name: Space-separated top-3 fertilizer recommendations for each test entry

  📖 References
      --> Detailed, well-commented code for complete transparency
      -->Visual EDA and performance analysis within the notebook
      -->Reproducible from end-to-end with example plots and explanations
