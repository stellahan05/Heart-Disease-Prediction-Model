# Group Project Proposal
## Predicting Heart Disease Presence using Cleveland Heart Disease Dataset

## Introduction:

-
According to the CCDSS, 14 Canadian adults (20 and over) with diagnosed heart disease die every hour. With heart disease being the second leading cause of mortality in Canada, early detection and diagnosis remain a crucial first step in improving patient outcomes. In this proposal, the K-Nearest Neighbors (k-NN) algorithm is used on the Cleveland Heart Disease dataset for binary classification of heart disease based on the predictive variables of age, sex (1 = male; 0 = female), chest pain type (1-4), and resting blood pressure (mm Hg). By leveraging existing data, we aim to train our model to deliver rapid and accurate heart disease diagnoses to alleviate physician workload. This change will enable them to allocate more time towards direct patient interactions, improving both patient and physician quality of life. 
-

## Preliminary exploratory data analysis:
Demonstrate that the dataset can be read from the web into R 
Clean and wrangle your data into a tidy format
Using only training data, summarize the data in at least one table (this is exploratory data analysis). An example of a useful table could be one that reports the number of observations in each class, the means of the predictor variables you plan to use in your analysis and how many rows have missing data. 
Using only training data, visualize the data with at least one plot relevant to the analysis you plan to do (this is exploratory data analysis). An example of a useful visualization could be one that compares the distributions of each of the predictor variables you plan to use in your analysis.

## Methods:
For our predictive task, we will employ the k-nearest neighbors (k-nn) algorithm for binary classification of heart disease presence in the Cleveland Heart Disease dataset. Predictor variables including age, sex, chest pain type, and resting blood pressure will be used for prediction of the predicted attribute “num”. The attribute “num” represents the diagnosis of heart disease based on angiographic disease status and has two possible values; value 0 suggests a lower likelihood of significant heart disease, while value 1 suggests a higher likelihood. Since we will be working with “num” as a categorical variable, we will convert it to a factor type, and  rename its values 0 to “Absent” and 1 to “Present”. Cross-validation will be utilized to select the optimal value of k, which we will use to retrain the classifier, then finally we will evaluate the estimated accuracy of the classifier in diagnosing heart disease. One way we will visualize the results is by using Receiver Operating Curves (ROC), which shows the relationship between the True Positive Rate (Sensitivity), and False Positive Rate (Specificity) of the model. Visualization of the results will aid in understanding the differentiation ability of the model and guide further analysis.

## Expected outcomes and significance:

We expect to use existing data to predict future heart disease diagnoses. This finding could enhance diagnostic accuracy by avoiding errors inherent in manual, case-by-case diagnoses. This model relies on real-world case comparisons, potentially revolutionizing healthcare by allowing rapid diagnoses. For instance, doctors might only need to measure resting blood pressure upon admission, with all other features pre-filled (sex, age, chest pain type). This could benefit patients with busy lifestyles. However, this raises questions about whether the dataset features are comprehensive enough for accurate diagnosis. To improve accuracy, further research is needed to identify additional features outside the dataset that influence heart disease.
