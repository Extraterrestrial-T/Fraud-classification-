### Links to parts of project
* Kaggle note book **(Contains all code and vizualizations)** = https://www.kaggle.com/code/jacker01/main-submission-data-science
* Project Brief = https://github.com/Extraterrestrial-T/Fraud-classification-/blob/main/data%20science%20breif.docx
# <p align="center">Project Name : Fraud Detection Model using Categorical Features</p>
##  <p align="center">Team Name - HIT</p>

<p align="center">
  <img src="https://github.com/Extraterrestrial-T/Fraud-classification-/assets/103042427/df88c02b-2429-4b8b-8fff-510281698116" alt="Image Description">
</p>

#  <p align="center">About Project</p>
## Overview
* [Project about](#Overview)
* [Data Exploration](#explore)
* [Data preprocessing](#process)
*  [Hypothesis Testing](#test)
* [Model Building](#build)

## <a name='Overview'></a> Project About: 

In this data science project, we aimed to develop a fraud detection model using categorical features to identify fraudulent and non-fraudulent transactions. The project involved analyzing the distribution of fraud and non-fraud cases across categorical columns, scaling the data using Standard Scaler, applying dimensionality reduction techniques, and building a classification model. 

## <a name='explore'></a>Data Exploration: 

During the initial data exploration phase, we observed that fraudulent cases appeared to be uniformly distributed among the various classes in the categorical columns. There were no clear or glaring predictors that could easily distinguish fraudulent from non-fraudulent transactions. Surprisingly, a similar uniform distribution was observed for non-fraudulent cases. 

## <a name='process'></a>Data Preprocessing: 
To prepare the data for modeling, we performed the following preprocessing steps: 

* Data preparation and categorical preprocessing with Target Encoding: we created a small sample from the entire dataset to fit our encoding model. This is to prevent data leakage.  

* Standard Scaling: We used the Standard Scaler to standardize the numerical features, ensuring that they all have a mean of 0 and a standard deviation of 1. This step was essential for models sensitive to feature scales. 

* Dimensionality Reduction: We applied dimensionality reduction techniques to reduce the complexity of the dataset while retaining as much information as possible. This step helped to mitigate the curse of dimensionality and improve model performance.

## <a name='test'></a> Hypothesis testing:
* We performed Identification of suitable predictors using Analysis of Variance (ANOVA), Chi Squared Contingency test and Pearson's Correlation coefficient
* For the ANOVA test, we chose a critical value of 0.05. If the p-value is less than 0.05, we reject the null hypothesis and accept the alternative hypothesis, otherwise we accept the null hypothesis and reject the alternative hypothesis. From the results, it was clear that no statistically significant relationship exists between the numeric features and the target variable. 
* The results of the Pearson's correlation coefficient further corroborated the findings from the result of the ANOVA Test.
* Using Chi Squared Contingency Test only one feature ("Country Code") appears to be correlated with our target variable. This show that 99% of the columns in this dataset cannot be used to predict the Target as no relationship exists.


## <a name='build'></a>Model Building: 

* Approach 1- 
**Plain logistic regression classifier** :
We chose to use logistic regression in our fraud classification project because of its simplicity and efficiency, align perfectly with the demands of real-time fraud detection. Its interpretable nature facilitates clear insight into the factors influencing fraudulent activities. In terms of data preprocessing, we employed Standard Scaler to standardize feature scales, ensuring uniformity across our dataset. Additionally, Principal Component Analysis (PCA) was leveraged for dimensionality reduction, enhancing computational efficiency and preventing overfitting. With this model we were able to achieve an **Accuracy of about 50%** at identifying fraud and non-fraud cases.

* Approach 2-
**Xgb Classifier** :
:  We chose to use a XGBoost classifier in our fraud classification project to try achieve optimal performance. XGBoost, a powerful ensemble learning algorithm, offers remarkable versatility and efficiency, making it an excellent choice for intricate tasks like fraud detection. To fine-tune our model, we diligently applied both random search and grid search hyperparameter optimization techniques. Remarkably, both methods yielded comparable results, with the model having **50% accuracy** also at identifying fraud and non-fraud cases.

* Approach 3-
**Plain decision tree classifier** :
We chose this model for the simplicity and interpretability of a plain Decision Tree classifier. We also had similar results with an Accuracy of 50%.

* Approach 4- 
**Ridge regression classifier and grid search** :
We used Ridge Regression because of its regularization properties. Ridge Regression offers us a balanced blend of simplicity and flexibility, allowing us to navigate the intricacies of fraud detection effectively. The results remained unchanged at 50% also.

* Approach 5- 
**Autoencoder representations feeding a decision tree** :
This approach trains an autoencoder which is a feed forward network whose input and output layers have the same shape and whose goal is to try and accurately transform the data into a richer representation. It also had an accuracy of about 50 % in identifying fraud and a f1 score of 50.

## Conclusion: 
In all it appears that most of our models have similar accuracy and F1 scores, this shows how data can hamper a model's performance. With Better data we believe that any of these models can be used to reasonable distinguish between fraudulent and non-Fraudulent transactions.
