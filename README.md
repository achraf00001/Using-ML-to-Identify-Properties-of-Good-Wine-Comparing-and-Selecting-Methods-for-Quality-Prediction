# Using-ML-to-Identify-Properties-of-Good-Wine-Comparing-and-Selecting-Methods-for-Quality-Prediction 

Red Wine Quality:

We consider the wine dataset.
Data description :

For this study I will analyze a Red Wine data set created by:
Paulo Cortez (Univ. Minho), Antonio Cerdeira, Fernando Almeida, Telmo Matos and Jose Reis (CVRVV) @ 
2009. This data set has 1599 observation and it contains 11 input variables: fixed acidity, volatile acidity, 
citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol 
and the output variable quality.

Input variables (based on physicochemical tests):all the variables are numerical.

1 - Fixed Acidity: Most acids involved with wine or fixed or nonvolatile (do not evaporate readily) (tartaric 
acid - g/dmˆ3)

2 - Volatile Acidity: The amount of acetic acid in wine, which at too high of levels can lead to an unpleasant, 
vinegar taste. (acetic acid - g/dmˆ3)

3 - Citric Acid: Found in small quantities, citric acid can add ‘freshness’ and flavor to wines. (g/dmˆ3)

4 - Residual Sugar: The amount of sugar remaining after fermentation stops, it’s rare to find wines with less 
than 1 gram/liter and wines with greater than 45 grams/liter are considered sweet. (g/dmˆ3)

5 - Chlorides: The amount of salt in the wine. (sodium chloride - g/dmˆ3)

6 - Free Sulfur Dioxide: The free form of SO2 exists in equilibrium between molecular SO2 (as a dissolved 
gas) and bisulfite ion; it prevents microbial growth and the oxidation of wine. (mg/dmˆ3)

7 - Total Sulfur Dioxide: Amount of free and bound forms of S02; in low concentrations, SO2 is mostly 
undetectable in wine, but at free SO2 concentrations over 50 ppm, SO2 becomes evident in the nose and 
taste of wine. (mg/dmˆ3)

8 - Density: The density of water is close to that of water depending on the percent alcohol and sugar content. 
(g/cmˆ3)

9 - pH: Describes how acidic or basic a wine is on a scale from 0 (very acidic) to 14 (very basic); most wines 
are between 3-4 on the pH scale

10 - Sulphates: A wine additive which can contribute to sulfur dioxide gas (S02) levels, wich acts as an 
antimicrobial and antioxidant. (g/dm3)

11 - Alcohol: The percent alcohol content of the wine 

Output variable (based on sensory data):

12 - quality (score between 0 and 10)

GOAL :

we are going to use machine learning to determine which physiochemical properties make wine ‘good’! Three 
methods are compared for this data set, the best one is selected and applied to the data for the final model 
in order to determine the quality of wine.

METHOD :

we are going to apply three different supervised learning algorithms on this data,Multiple linear regression(MLR),neural network(NN) and principal component regression(PCR). using 10-fold cross validation to 
compare the performance of the three methods we are going to choose the best method that give us the best 
prediction model for the wine quality.
First we split the data into training and test set. The training set should be used to build our machine 
learning models. in other words we are going to create a model based on our training data then we test our 
model on the test data.The test set should be used to see how well our model performs on unseen data.
The quality is the univariate response y. we need a couple of steps:

• Step 1. Construct 2 nested for loops, where the outer for loop is for 10-fold cross validation in order 
to compare the performance of the three methods; the inner for loop is for finding the best tuning 
parameter value for the NN model:

– Within the outer for loop, the MLR,NN and PRC are fit on the train set, predictions on the test 
set are made, and test errors (MSE) are obtained. The model fitting, prediction on test set, and 
calculation of test error given by NN must be done after the inner for loop determines the best 
number of nodes.

• Step 2. Make boxplot for the 10 cross-validation errors of the three methods. Perform paired t test for 
significance of difference of CV errors between the three methods.

• Step 3. Choose the one with better performance, fit to the whole data, to get the final model.

Multiple linear regression:

Multiple linear regression (MLR), is a statistical technique that uses several explanatory variables to predict 
the outcome of a response variable. The goal of multiple linear regression is to model the linear relationship 
between the explanatory (independent) variables and response (dependent) variables.
Advantages of Multiple linear Regression: There are two main advantages to analyzing data using a 
multiple regression model. The first is the ability to determine the relative influence of one or more predictor 
variables to the criterion value.The second advantage is the ability to identify outliers, or anomalies.
Disadvantages of Multiple linear Regression -Linear Regression Only Looks at the Mean of the 
Dependent Variable. -Linear regression looks at a relationship between the mean of the dependent variable 
and the independent variables. -Linear Regression Is Sensitive to Outliers.also the Data Must be Independent.

Neural Network :

A neural network is a series of algorithms that endeavors to recognize underlying relationships in a set of 
data through a process that mimics the way the human brain operates. In this sense, neural networks refer 
to systems of neurons, either organic or artificial in nature
Advantages of Neural Network -Store information on the entire network. -The network problem does not 
immediately corrode. -Ability to train machine: Artificial neural networks learn events and make decisions by 
commenting on similar events. -Parallel processing ability: Artificial neural networks have numerical strength 
that can perform more than one job at the same time.
Disadvantages of Neural Network Neural networks usually require much more data than traditional 
machine learning algorithms, as in at least thousands if not millions of labeled samples. This isn’t an easy
problem to deal with and many machine learning problems can be solved well with less data if you use other 
algorithms.

Principal component regression:

principal component regression (PCR) is a regression analysis technique that is based on principal component 
analysis (PCA). More specifically, PCR is used for estimating the unknown regression coefficients in a standard 

linear regression model.

Advantages of PCR -Removes Correlated Features. -Improves Algorithm Performance. -Reduces Overfitting
-Improves Visualization:
Advantages of PCR - Independent variables become less interpretable. - Data standardization is must 
before PCR. - Information Loss: Although Principal Components try to cover maximum variance among the 
features in a dataset, if we don’t select the number of Principal Components with care, it may miss some 
information as compared to the original list of features.
