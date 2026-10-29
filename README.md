# Student Performance, & Weather Classification

## Datasets

### Student Performance

Description: The Student Performance Dataset is a dataset designed to examine the factors influencing academic student performance. The dataset consists of 10,000 student records, with each record containing information about various predictors and a performance index.

Target variable: Performance Index

Link: https://www.kaggle.com/datasets/nikhil7280/student-performance-multiple-linear-regression 

### Weather Type Classification

Description: This dataset is synthetically generated to mimic weather data for classification tasks. It includes various weather-related features and categorizes the weather into four types: Rainy, Sunny, Cloudy, and Snowy. This dataset is designed for practicing classification algorithms, data preprocessing, and outlier detection methods.

Target variable: Weather Type

Link: https://www.kaggle.com/datasets/nikhil7280/weather-type-classification 

## EDA Summary

### Student Performance Dataset (Linear Regression)

Data did not include any missing, or duplicate values

Data didn’t contain any abnormal values

Data contained 10000 rows, and 6 columns

Changed column name from “Sample Question Papers Practiced” to “Papers_Practiced”

Examined the value count of the categorical column “Extracurricular Activities”, and it contained 5052 “No”, and 4948 “Yes’

Encoded the column “Extracurricular Activities” to 0, and 1

### Weather Type Classification (Logistic Regression)

Data did not include any missing, or duplicate values

Data didn’t contain any abnormal values

Data contained 13200 rows, and 11 columns

Examined the value counts of the four categorical columns in the dataset

Weather Type was evenly distributed across its four categories, with 3,300 observations each for Rainy, Cloudy, Sunny, and Snowy

Cloud Cover had an imbalanced distribution: overcast appeared 6,090 times, partly cloudy 4,560 times, clear 2,139 times, and cloudy only 411 times

Season also showed variation, with Winter being the most common (5,610), followed by Spring (2,598), Autumn (2,500), and Summer (2,492)

For Location, the dataset contained 4,816 inland, 4,813 mountain, and 3,571 coastal entries

Encoded the categorical variables to prepare them for the logistic regression model:

Weather Type was transformed using Label Encoding, assigning each class a unique numeric label suitable for multiclass classification

Cloud Cover was encoded using an ordinal mapping (from clear to overcast) to preserve the natural progression of cloudiness levels

Location and Season were converted using One-Hot Encoding, since these variables do not have an inherent order

## Visualizations

### Student Performance Dataset (Linear Regression)

Correlation heatmap shows the strength of relationships between numerical variables using color-coded correlation values

Scatter plot displays how performance changes with previous scores and highlights the relationship between the two variables

Distribution of Hours Slept shows how frequently each amount of sleep occurs in the dataset

Predicted vs Actual Performance Index compares model predictions with true values to assess accuracy

Residual Distribution shows the spread of prediction errors

### Weather Type Classification (Logistic Regression)

Correlation Between Variables displays how numerical features relate to each other. darker colors indicate stronger correlations.

Temperature Distribution shows the density of temperature values, highlighting the most common temperature ranges

Average Temperature by Weather Type compares mean temperatures across different weather conditions

Temperature Distribution Across Seasons shows the spread and variability of temperatures for each season

## Model Implementation Steps

### Student Performance Dataset (Linear Regression)

Split the data into a train, and a test datasets. The train dataset is 70% of the original one, while the test dataset is 30%.

Trained the model using the training dataset and measured performance using Mean Square Errors, and Root Mean Square Errors.

### Weather Type Classification (Logistic Regression)

Split the data into a train, and a test datasets. The train dataset is 70% of the original one, while the test dataset is 30% with stratified on to keep the balance of the classes.

Trained the model using the training dataset with 1000 iterations and mutliclass being “auto” 

Measured performance using Accuracy, Precision, Recall, F1-Score, Support, and Confusion Matrix.

## Evaluation Metrics

### Student Performance Dataset (Linear Regression)

Mean Square Errors: 4.19

Root Mean Square Errors: 2.04

### Weather Type Classification (Logistic Regression)

Accuracy: 0.87

Precision: 0.87

Recall: 0.87

F1-Score: 0.87

Support: 36960

Confusion Matrix: 

Actual Cloudy: Predicted as Cloudy 812, Rainy 91, Snowy 36, Sunny 51

Actual Rainy: Predicted as Cloudy 76, Rainy 830, Snowy 67, Sunny 17

Actual Snowy: Predicted as Cloudy 34, Rainy 12, Snowy 929, Sunny 15

Actual Sunny: Predicted as Cloudy 56, Rainy 28, Snowy 22, Sunny 884

## Interpretation of Results

### Student Performance Dataset (Linear Regression)

The linear regression model shows a Mean Squared Error (MSE) of 4.19 and a Root Mean Squared Error (RMSE) of 2.04. This indicates that, on average, the predicted performance index values deviate from the actual values by about 2 points. The relatively low RMSE suggests that the model provides reasonably accurate predictions, capturing the general trend of student performance based on the input features.

### Weather Type Classification (Logistic Regression)

The logistic regression model achieved an accuracy of 0.87, meaning it correctly predicts the weather type 87% of the time. The precision, recall, and F1-score are all 0.87, reflecting a balanced performance across all classes.

The confusion matrix provides further insight:

Cloudy instances are mostly correctly predicted (812), but some are misclassified as Rainy (91) or Sunny (51).

Rainy instances are largely correctly classified (830), though a few are confused with Snowy (67) or Cloudy (76).

Snowy instances have the highest correct prediction rate (929), with minimal misclassification.

Sunny instances are also mostly correct (884) but occasionally misclassified as Cloudy (56) or Rainy (28).

Overall, the model performs well across all classes, with slightly better performance for Snowy and Sunny conditions. Misclassifications tend to occur between classes with similar weather characteristics (e.g., Cloudy vs. Rainy).
