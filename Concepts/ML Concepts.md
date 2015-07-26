ML Concepts
========================================================
author: Gaurav Chaturvedi
date: 25-Jul-2015

Steps in Machine Learning
========================================================

Key steps in developing a Machine Learning solution

1. Define the Question
2. Input Data
3. Feature Selection
4. Use Machine Learning Algorithm (MLA)
5. Estimate Parameters of MLA
6. Evaluate accuracy of MLA
7. Select the best MLA

Relative Importance of steps
================================================================

- Question
- Feature selection 
- Algorithms matter less than we think 

step2 - Input data 
==============================================================

What data to use?

"To predict X use data as closely related to X as possible"

So to predict player performance use data about player performance (maybe other players)

Looser connection makes for a hard prediction. Unrelated data is the most common mistake(e.g. per Capita Chocolate Consumption vs. # Nobel Prizes)

Step 3 - Feature selection:
=====================================================
Good feature Selection: 

  - Leads to data compression
  - Retains relevant information
  - Created based on expert knowledge
  
Principal Component Analysis(PCA) is useful when there are lots of predictor variables

Step3 - Feature Selection (Preprocessing)
=============================================================================

Preprocessing more useful when using Model Based MLA like LDA, NB, GLM. Not very iseful with say non parametric approaches (like RF)

When to do Pre-processing:
- Skewed Variables 
- High variability 
- Missing data 

methods:
- Centre and Scaling
- Box Cox transforms (transform continuous data to normal data)
- K nearest neighbours imputation

Step 3 - Feature Selection (Covariate Creation)
======================================================================

When actual data has too many variables or not amenable to modelling (e.g. image)
- remove near zero variance (nearZeroVar function)
- create a polynomial variables (spline package, bs function OR gam in caret)

Trade-off in summarizing vs. Information Loss

Step 3 - Feature Selection (SVD/PCA)
==========================================================================
Useful when there are lots of variables and highly coorelated 


Step 4 - Trade-Offs in Machine learning Algorithm
=================================================
- Interpretability
- Scalability
- Simplicity
- Accuracy
- Speed

Step 5 - Estimating Parameters of MLA
===================================================================

Accuracy
ROC Curve - Used if outcome in binary, but prediction is quantitative (e.g. probability)
  - Plot Sensitivity vs. Spec. given different parameter values. Plot for different algorithms and choose one with highest area under the curve (0.5 is eq to coin flipping)


Step 6 - Accuracy of machine Learnign Algorithm 
=======================================================

We care a lot about accuracy. So how do we measure accuracy:

- In vs. Out of sample error - Overfitting can lead to low in sample and high out of sample error
- For binary outcome accuracy is confusion matrix (Specificity/Sensitivity, Accuracy)
- For continuous (RMSE, MSE or Median Absolute Deviation)

Step 7 - MLAs in R
===================================================

- Linear Discriminant Analysis
- Regression
- Naive BAyes
- Support Vector Machines (SVM)
- Classification and Regression Trees 
- Random Forest
- Boosting 

And many more...


Step 7 - How to select the right MLA
=============================================================

Use Cross valiation to select the right MLA (predictors, parameters, methodology) . Approach is:

- Use training set and split into training/test sets
- Build and evaluate model (accuracy etc.)
- Repeat and average the estimated errors
- Repeat for a different model

Training set can be split into training/test using Random Subsampling (with or w/o replacement), K Fold, Leave one out CV, Bootstrapping or Bootstrapping 632, Repeated CV
