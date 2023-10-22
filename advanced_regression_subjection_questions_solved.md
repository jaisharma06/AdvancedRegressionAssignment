# Table Of Contents
- [Table Of Contents](#table-of-contents)
- [1. What is the optimal value of alpha for ridge and lasso regression? What will be the changes in the model if you choose double the value of alpha for both ridge and lasso? What will be the most important predictor variables after the change is implemented?](#1-what-is-the-optimal-value-of-alpha-for-ridge-and-lasso-regression-what-will-be-the-changes-in-the-model-if-you-choose-double-the-value-of-alpha-for-both-ridge-and-lasso-what-will-be-the-most-important-predictor-variables-after-the-change-is-implemented)
    - [After doubling the alpha values:](#after-doubling-the-alpha-values)
    - [Changes in Ridge Regression metrics:](#changes-in-ridge-regression-metrics)
    - [Changes in Lasso metrics:](#changes-in-lasso-metrics)
- [2. You have determined the optimal value of lambda for ridge and lasso regression during the assignment. Now, which one will you choose to apply and why?](#2-you-have-determined-the-optimal-value-of-lambda-for-ridge-and-lasso-regression-during-the-assignment-now-which-one-will-you-choose-to-apply-and-why)
- [3. After building the model, you realised that the five most important predictor variables in the lasso model are not available in the incoming data. You will now have to create another model excluding the five most important predictor variables. Which are the five most important predictor variables now?](#3-after-building-the-model-you-realised-that-the-five-most-important-predictor-variables-in-the-lasso-model-are-not-available-in-the-incoming-data-you-will-now-have-to-create-another-model-excluding-the-five-most-important-predictor-variables-which-are-the-five-most-important-predictor-variables-now)
- [4. How can you make sure that a model is robust and generalisable? What are the implications of the same for the accuracy of the model and why?](#4-how-can-you-make-sure-that-a-model-is-robust-and-generalisable-what-are-the-implications-of-the-same-for-the-accuracy-of-the-model-and-why)

# 1. What is the optimal value of alpha for ridge and lasso regression? What will be the changes in the model if you choose double the value of alpha for both ridge and lasso? What will be the most important predictor variables after the change is implemented?

- Optimal value of lambda for Ridge Regression = 10
- Optimal value of lambda for Lasso = 0.001

### After doubling the alpha values:

### Changes in Ridge Regression metrics:
- R2 score of train set decreased from 0.94 to 0.93
- R2 score of test set remained same at 0.93

### Changes in Lasso metrics:
- R2 score of train set decreased from 0.92 to 0.91
- R2 score of test set decreased from 0.93 to 0.91

<br>

# 2. You have determined the optimal value of lambda for ridge and lasso regression during the assignment. Now, which one will you choose to apply and why?
- The model we will choose to apply will depend on the use case.
- If we have too many variables and one of our primary goal is feature selection, then we will use Lasso.
- If we don't want to get too large coefficients and reduction of coefficient magnitude is one of our prime goals, then we will use Ridge Regression.

<br>

# 3. After building the model, you realised that the five most important predictor variables in the lasso model are not available in the incoming data. You will now have to create another model excluding the five most important predictor variables. Which are the five most important predictor variables now?

**Top 5 predictors we will drop are:**
1. OverallQual_9
2. GrLivArea
3. OverallQual_8
4. Neighborhood_Crawfor
5. Exterior1st_BrkFace

**After dropping our top 5 lasso predictors, we get the following new top 5 predictors:-**
1. 2ndFlrSF
2. Functional_Typ
3. 1stFlrSF
4. MSSubClass_70
5. Neighborhood_Somerst

<br>

# 4. How can you make sure that a model is robust and generalisable? What are the implications of the same for the accuracy of the model and why?
- A model is robust when any variation in the data does not affect its performance much.
A generalizable model is able to adapt properly to new, previously unseen data, drawn from the same distribution as the one used to create the model.
- To make sure a model is robust and generalizable, we have to take care it doesn't overfit. This is because an overfitting model has very high variance and a smallest change in data affects the model prediction heavily. Such a model will identify all the patterns of a training data, but fail to pick up the patterns in unseen test data.
- In other words, the model should not be too complex in order to be robust and generalizable.
- If we look at it from the prespective of Accuracy, a too complex model will have a very high accuracy. So, to make our model more robust and generalizable, we will have to decrease variance which will lead to some bias. Addition of bias means that accuracy will decrease.
- In general, we have to find strike some balance between model accuracy and complexity. This can be achieved by Regularization techniques like Ridge Regression and Lasso.