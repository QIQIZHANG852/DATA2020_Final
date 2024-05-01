# DATA2020_Final

In the Rmd file, we include our R-code for data pre-processing, EDA, models and their results. 

For EDA part, we use four variables : "# k5e2a Picked on you or said mean things to you?  k5e2b Hit you?  Taken your things, like your money or lunch, without asking? k5e2c.   Purposely left you out of activities?  k5e2d
to calculate the bullying degree. And then we find that the distribution of our target variable is imbalanced and thus we decide to we decide to treat the sum whose value is smaller than 0 to "label 0" (never being bullied before) and sum whose value is larger than 0 as label 1(being bullied before) to ensure balanced data. Then, in the original dataset, there are so many features(around 3864 features). To reduce the number of features, first we choose alpha=0.2 to achieve the largest R^2 and based on this model, we select 30 features whose coefficient does not equal to 0.
As for missing values, We drop features with NAN values(those features are not important themselves) and For answers like "-1 Refuse", "-2 Don\'t know", "-3 Missing",..etc, we replace those values with -1. 
For Model Assumption, we decide to check two pre-assumptions:Co-linearlity betwen features (VIF) and Existence of Outliers(PCA). And both passed the check. 

In the second part, we include logistic Regression and Random Forest to fit in the data. To solve the problem of overfitting and uncertainty, we try to tune the hyperparameter and use 5-fold cross validation. Finally, we print out the final results of our models. And we find that both models perform very similar in terms of accuracy and F-1 score, whereas Logistic Regression produce more stable predictions and Random Forest has slight advantage in AUC. Both exceed the baseline accuracy of 0.62. 

Lastly, for the model that performs better(Random Forest), we interpreted the model by feature importance: The top 10 variables identified in the Random Forest model highlight emotional, behavioral, and environmental factors that are influential in predicting whether a child will be bullied at school. These variables collectively reflect a complex interplay of personal vulnerabilities and external pressures that can influence a child's likelihood of being bullied.
