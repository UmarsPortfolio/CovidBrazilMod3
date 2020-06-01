

# Overview

The aim of this project is to develop a model that can accurately classify the kind of hospitalization required for patients suffering from COVID Sars 2, based on their clinical data and test results. 

The final model can determine whether a patient needs to be admitted to the regular ward, the intensive care ward or if they do not require any admission whatsoever. 

# Dataset

The dataset used in this project comes from the Hospital Israelita Albert Einstein in Sao Paulo Brazil, and can be found [here](https://www.kaggle.com/einsteindata4u/covid19).

The data set contains around 5000 records and consists of over 100 features. The biggest challenge with this dataset was the enormous amount of missing data. This absence of data points is partly due to the nature of the problem itself. Most of the records are for patients that were never admitted at all, and labs were only performed on patients who were. Since most of the features relate to lab test results, we have many features empty for many records on account of the fact that the labs were never performed. 

Additionaly, there is strong class imbalance between not hospitalized, regular ward and intensive care patients. 

# Methodology

To address the challenge of missing data, I have employed an iterative regression technique that takes data that IS present as a training set to predict the values missing for a given feature, and then adding the now complete feature to the training set for the next feature. 

As for developing the actual model, I fit a variety of models to the data nd selected the best one. The following dataframe shows the performance metrics for each class with each model variant. 

<img source='resultsdf.png'>

To verify the coefficients computed by the best model, I used hypothesis testing to compare the means of features between admited and not admitted patients to see if there was a statistically significant difference those two populations for that feature. The idea is, that is a significant difference exists, then those features do in fact bear heavily on determing which category a patient will fall into. 

# Conclusions

A Logistic Regression model using SMOTE to address the imbalance issue appears to be the best peforming model. 

The following chart shows the most important features identified by the model. 

<img source='Images/feature_importance.png'>

# Recommendations

Additional data would be very helpful. There are some easy to obtain data points that are missing, things like BMI data, pre-existing conditions, smoking history etc. Ofcourse, patient privacy might be a concern. 
