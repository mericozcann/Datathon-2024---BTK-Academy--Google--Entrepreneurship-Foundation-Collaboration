# Datathon 2024: Evaluation Score Prediction
## Project Overview
This project is part of Datathon 2024, focusing on predicting the "Degerlendirme Puani" (Evaluation Score) for a set of applicants. The provided dataset includes anonymized information on applicants from the Girişimcilik Vakfı, ranging from personal background to educational and socio-economic data.
The task involves building predictive models that estimate the missing evaluation scores for a group of 11,049 applicants from the year 2023. The evaluation metric for this competition is Root Mean Square Error (RMSE).
### Files in the Project
•	train.csv: Contains the data from previous applicants, including their Evaluation Scores.
•	test_x.csv: Holds the anonymized data for 11,049 applicants from 2023, missing only the Evaluation Score.
•	sample_submission.csv: A template for submission, with two columns: id and Degerlendirme Puani.
•	submission.csv: Your final submission file containing predicted Evaluation Scores for the test set.
## Objective
The objective is to predict the missing Degerlendirme Puani for the test set and submit the results in a format similar to the sample_submission.csv file, containing two columns: id and Degerlendirme Puani.
## Approach
### Data Preprocessing
1.	Handling Missing Values:
o	For numerical columns, missing values were filled using the mean.
o	For categorical columns, missing values were filled using the most frequent strategy.
2.	Categorical Encoding:
o	Two different approaches were used: Label Encoding for the first model and Target Encoding for the second, to handle categorical features effectively.
3.	Outlier Detection and Removal:
o	The Interquartile Range (IQR) method was used to identify and remove outliers in numerical columns.
Model Training
Two machine learning models were trained, optimized, and combined for an ensemble approach:
1.	RandomForestRegressor:
o	Hyperparameter tuning was done using GridSearchCV to find the best model configuration.
o	Recursive Feature Elimination (RFE) was applied to select the most important features.
2.	XGBoost:
o	Similarly, hyperparameter tuning was done with GridSearchCV to identify the best set of parameters.
o	A stratified k-fold cross-validation approach was used to ensure robustness.
Ensemble Model
•	The final predictions were made using an ensemble of both RandomForestRegressor and XGBoost, where the predictions from both models were averaged to improve accuracy.
### Evaluation
The model's performance was evaluated using RMSE on the validation set. RMSE provides a measure of the error between predicted and actual evaluation scores.
Exploratory Data Analysis (EDA)
•	Visualizations were made to understand the distribution of target variables and feature relationships.
•	A heatmap was generated to analyze the correlation between features, providing insights into data relationships.
Results and Submission
•	The predicted scores were saved in submission_ensemble.csv, following the format provided in sample_submission.csv.
## Conclusion
This project demonstrated the power of using ensemble models with careful preprocessing and feature selection to achieve better predictions for the Evaluation Score. The final ensemble model combined Random Forest and XGBoost for optimal performance on the test set.
