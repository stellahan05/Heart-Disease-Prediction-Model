# Predicting Heart Disease Presence using Cleveland Heart Disease Dataset

## Introduction

According to the CCDSS, 14 Canadian adults (20 and over) with diagnosed heart disease die every hour (Canada, 2022), and incidences of sudden cardiac death (SCD) in athletes range from 1 in 40,000 to 1 in 80,000 athletes per year (Wasfy et al., 2016). These statistics underscore the urgency of implementing effective prevention strategies. With heart disease being the second leading cause of mortality in Canada (Dai et al., 2021), early detection and diagnosis remain a crucial first step in improving patient outcomes. In this proposal, the K-Nearest Neighbors (k-NN) algorithm is used on the Cleveland Heart Disease dataset for binary classification of heart disease based on the predictive variables of age, sex (1 = male; 0 = female), chest pain type (1-4), and resting blood pressure (mm Hg). By leveraging existing data, we aim to train our model to deliver rapid and accurate heart disease diagnoses to alleviate physician workload. This change will enable them to dedicate more time to direct patient interactions, improving patient and physician quality of life. 

## Methods

### Data Preparation and Cleaning
We initiated our analysis by loading the necessary R packages and reading the Cleveland Heart Disease dataset from a web source using the ‘read_csv’ function. The dataset initially lacked column names, so we manually assigned them to ensure accurate processing.
Next, we addressed missing values in the dataset, which were denoted by "?". We replaced these with "NA" to facilitate correct data processing in R. We also converted several variables expected to be categorical into factor variables. Specifically, the variables "sex", "fbs", "restecg", "exang", "thal", "ca", and "slope" were converted to factors. The response variable, initially labelled as "num", was transformed into a binary factor variable named "diag", with values of 0 representing "Absent" and values greater than 0 representing "Present" heart disease.

### Exploratory Data Analysis
We performed an exploratory data analysis (EDA) to understand the dataset's characteristics. We summarized the data by computing the means of the predictor variables "cp" and "trestbps" across the two diagnostic classes ("FALSE" and "TRUE") of heart disease. The summary revealed that higher average resting blood pressure (avg_trestbps) and chest pain type (avg_cp) were associated with a higher likelihood of heart disease. 
Furthermore, we visualized the relationship between chest pain type (cp) and resting blood pressure (trestbps) using a bar plot. This visualization aimed to compare the distributions of these predictor variables across the two diagnostic classes.

### Data Splitting
To develop our predictive model, we divided the dataset into a training set and a testing set using the ‘initial_split’ function. 75% of the data was allocated to the training set, and 25% for testing.

### Model Development
We standardized the predictor variables, "cp" and "trestbps", by scaling them to unit variance and centring them to zero mean. This standardization is crucial for distance-based algorithms like k-NN to ensure that attributes with larger ranges do not dominate the distance calculations.
We specified the k-NN model with a rectangular weight function and set the number of neighbours to be tuned dynamically. The model was configured for classification using the ‘kknn’ engine. To determine the optimal number of neighbours (k), we performed 10-fold cross-validation on the training dataset, stratifying by the "diag" outcome to ensure balanced sampling.
A grid of potential values for k ranging from 1 to 100 was prepared. The model was tuned across these values to identify the optimal k value that maximizes accuracy.

## Results

## Discussion
Results indicate that after tuning the model, the optimal k value was determined to be 11, which yielded the highest average accuracy of approximately 77.24%. The final k-NN model, fitted with the optimal k value, demonstrated an overall accuracy of approximately 76.92% on the testing set. The model correctly classified 36 cases of "Absent" heart disease and 24 cases of "Present" heart disease. However, it also misclassified 12 cases of "Absent" heart disease as "Present" and 6 cases of "Present" heart disease as "Absent." These findings suggest that the k-NN model shows potential in predicting heart disease.

The results align with our expectations, and a model to predict heart disease presence was successfully developed. However, the overall accuracy of approximately 76.92% on the testing set was slightly lower than expected.

These results provide a foundation for future research to build upon, potentially leading to further improvements in predicting heart disease using machine learning techniques. Such a model could enhance diagnostic accuracy by avoiding errors inherent in manual, case-by-case diagnoses. It relies on real-world case comparisons, potentially revolutionizing healthcare by allowing rapid diagnoses. For instance, doctors might only need to measure resting blood pressure upon admission, with all other features pre-filled (sex, age, chest pain type), benefitting patients with busy lifestyles. However, this raises questions about whether the dataset features are comprehensive enough for accurate diagnosis. Future research could focus on refining the model's performance by exploring additional features, such as genetic markers or lifestyle factors, that may enhance its predictive ability.

In conclusion, this study contributes to the ongoing efforts to utilize machine learning for predicting heart disease. By highlighting the strengths and limitations of the k-NN model, valuable insights for further research in this area were provided.


## References
(1) Canada, P. H. A. of. (2022, July 28). Heart Disease in Canada. Canada.ca. https://www.canada.ca/en/public-health/services/publications/diseases-conditions/heart-disease-canada.html 
(2) Wasfy, M. M., Hutter, A. M., & Weiner, R. B. (2016). Sudden cardiac death in athletes. Methodist DeBakey cardiovascular journal. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4969030/ 
(3) Dai, H., Younis, A., Kong, J. D., Bragazzi, N. L., & Wu, J. (2021). Trends and Regional Variation in Prevalence of Cardiovascular Risk Factors and Association With Socioeconomic Status in Canada, 2005-2016. JAMA network open, 4(8), e2121443. https://doi.org/10.1001/jamanetworkopen.2021.21443
(4) Janosi,Andras, Steinbrunn,William, Pfisterer,Matthias, and Detrano,Robert. (1988). Heart Disease. UCI Machine Learning Repository. https://doi.org/10.24432/C52P4X.



