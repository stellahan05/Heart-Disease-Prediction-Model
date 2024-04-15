# Methods
## Data Preparation and Cleaning
We initiated our analysis by loading the necessary R packages and reading the Cleveland Heart Disease dataset from a web source using the ‘read_csv’ function. The dataset initially lacked column names, so we manually assigned them to ensure accurate processing.
Next, we addressed missing values in the dataset, which were denoted by "?". We replaced these with "NA" to facilitate correct data processing in R. We also converted several variables expected to be categorical into factor variables. Specifically, the variables "sex", "fbs", "restecg", "exang", "thal", "ca", and "slope" were converted to factors. The response variable, initially labeled as "num", was transformed into a binary factor variable named "diag", with values of 0 representing "Absent" and values greater than 0 representing "Present" heart disease.
## Exploratory Data Analysis
We performed an exploratory data analysis (EDA) to understand the dataset's characteristics. We summarized the data by computing the means of the predictor variables "cp" and "trestbps" across the two diagnostic classes ("FALSE" and "TRUE") of heart disease. The summary revealed that higher average resting blood pressure (avg_trestbps) and chest pain type (avg_cp) were associated with a higher likelihood of heart disease. 
Furthermore, we visualized the relationship between chest pain type (cp) and resting blood pressure (trestbps) using a bar plot. This visualization aimed to compare the distributions of these predictor variables across the two diagnostic classes.
## Data Splitting
To develop our predictive model, we divided the dataset into a training set and a testing set using the ‘initial_split’ function. 75% of the data was allocated to the training set, and 25% for testing.
## Model Development
We standardized the predictor variables, "cp" and "trestbps", by scaling them to unit variance and centering them to zero mean. This standardization is crucial for distance-based algorithms like k-NN to ensure that attributes with larger ranges do not dominate the distance calculations.
We specified the k-NN model with a rectangular weight function and set the number of neighbors to be tuned dynamically. The model was configured for classification using the ‘kknn’ engine. To determine the optimal number of neighbors (k), we performed 10-fold cross-validation on the training dataset, stratifying by the "diag" outcome to ensure balanced sampling.
A grid of potential values for k ranging from 1 to 100 was prepared. The model was tuned across these values to identify the optimal k value that maximizes accuracy.
# Results
## Model Evaluation
After tuning the k-NN model, we collected accuracy metrics for each model configuration, focusing on accuracy as the primary performance measure. The top-performing configurations were identified based on the highest average accuracy. Among them, the 11th neighbor yielded the highest average accuracy of approximately 77.24%.
## Final Model
With the optimal k value determined (k=11), we finalized our k-NN model. We fitted the model to the training dataset using the specified k value and other configurations.
## Model Testing
We evaluated the performance of our final k-NN model on the testing set. The overall accuracy of the model was found to be approximately 76.92%. The confusion matrix revealed that the model correctly classified 36 cases of "Absent" heart disease and 24 cases of "Present" heart disease, while misclassifying 12 cases of "Absent" heart disease as "Present" and 6 cases of "Present" heart disease as "Absent".


