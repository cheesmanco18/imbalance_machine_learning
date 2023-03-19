# Module 12 Report Template

## Overview of the Analysis


* The purpose of this analysis is to predict and identify loans that are high-risk using a logistic regression model. The training data is from a lending company and includes features on each loan such as size of loan, debt levels, interest rates, etc. We're using these features to predict the target variable: whether a loan is healthy (0) or high risk (1). As part of the analysis, I pulled in the data and split it into testing/training groups, trained/fit the model, made predictions and evaluated the model. Since the data was imbalanced (low amount of high risk loans in the dataset - which I identified using value_count()), I used an oversampling technique to make resample and make predictions and compare the model to the non-resampled model prediction. 


## Results

* Machine Learning Model 1:
  * Accuracy: high accuracy of 95%, but likely because there are a lot of healthy loans relative to non-healthy so it's identifying the healthy loans accurately because there are more. Could be not so accurate with the high-risk loans judging by this metric alone.  
  * Precision: high precision (1.0) with the healthy loans but lower (0.85) with the high-risk. This indicates a decent amount of false positives. 
  * Recall: high recall for healthy loans (0.99) but lower for at risk-loans (0.91). This indicates some false negatives, which would be costly for loans because you don't want to miss any that might be at risk. 



* Machine Learning Model 2:
  * Accuracy: high accuracy of 99%. This is encouraging given the sample is balanced so it's predictions are potentially more a matter of skill than randomness.   
  * Precision: high precision (1.0) with the healthy loans but lower (0.84) with the high-risk. This indicates a decent amount of false positives. 
  * Recall: high recall for healthy loans (0.99) and at risk-loans (0.99). This indicates few false negatives, especially relative to the non-resampled model. 

## Summary

* The oversampled model (ML Model 2) is the better model to use. It has higher accuracy, higher recall and scores similarly on the precision metrics versus ML Model 1. Both models have similar F1s. The recommendation is mainly based on its ML 2's higher recall versus ML1. This means there are less occurences where it produces a false negative, meaning it identifies a bad loan as good less often. This is important because in the context of giving out loans, you want to flag all instances where you could lose money. There are situations where a false negative (recall) would be less important, but in this context it's important. I would recommend Model 2 because it scores well on all of the observed metrics (including its high F1)

