---
layout: post
title: Making Predictions using Logistic Regression
categories: [Regression]
---

So, what is logistic regression and how does it work? In a nutshell, logistic regression is a way to predict the likelihood of a certain event occurring. For example, you might use logistic regression to predict the likelihood that a customer will make a purchase based on their past behaviour, or to predict the likelihood that a patient will develop a certain disease based on their medical history. 

To use logistic regression, you'll need two things: data and a prediction question. The data could be anything from customer demographics to medical records, and the prediction question could be anything from "Will this customer make a purchase?" to "Will this patient develop diabetes?"

Let's take the example of a Portugese bank that wanted to predict the likelihood of an exisitng customer subsrcibing to their new product offerring based on factors such as age, income etc. The full list of factors is shown below, with an outcome of either "yes" or "no". The prediction question would then be: "Will this customer subscribe to the new fixed term loan?"

| #   | Variable label   | Variable Description                                                                       |
| --- |:---------------- |:------------------------------------------------------------------------------------------ |
| 1   | age              | Numeric: Age of the client                                                                 |
| 2   | job              | Categorical                                                                                |
| 3   | marital          | Client's marital status                                                                    |
| 4   | education        | Education level achieved                                                                   |
| 5   | default          | Has credit in default?                                                                     |
| 6   | housing          | Has a housing loan?                                                                        |
| 7   | loan             | Has a personal loan?                                                                       |
| 8   | contact          | Contact communication type                                                                 |
| 9   | month            | Month of the year (Jan to Dec)                                                             |
| 10  | campaign         | umber of contacts performed during the campaign and for the specific client                |
| 11  | pdays            | Number of days that passed by after the client was last contacted from a previous campaign |
| 12  | previous         | Number of times the client had been contacted before the campaign                          |
| 13  | poutcomes        | Outcomes of previous marketing campaigns                                                   |
| 14  | y                | Did the client subcribe a term deposit? (yes or no)                                        |

The full dataset can be found here: link

Now that we have our data and prediction question we can conduct our logistic regression analysis. This will help us understand the relationship between different variables and how they influence the outcome we're trying to predict. The logistic regression analysis will help us understand how each of these variables affects the likelihood of a subscription, and we can use this information to make informed predictions. The following steps were taken in conducting the logistic regression:

1. Feature selection and model fitting 
2. Model performance testing 
3. New data predictions


## Feature Selection

The total data set consisted of 50 422 observations with 16 attributes (including the response variable). The data set was split into two sets; one set was used for the regression process, while the other was used to conduct the predictions. The data consisted of both numeric (continuous) variables and categorical variables, therefore, to determine whether there was any correlation between the attributes the following three metrices were used:
1. Contingency Coefficient ($\mathcal{C}$) - Categorical Data "coerrelation"
2. One way ANOVA test - Categorical and Numerica data "correlation"
3. Pearson's correlation coefficient - Numeric data correlation

Given the features were not correlated, I went forward with the Logistic regression process. 

<div style="text-align: center;">
 <script async type="text/javascript" src="//cdn.carbonads.com/carbon.js?serve=CE7D6KJY&placement=wwwamitmerchantcom" id="_carbonads_js"></script>
</div>

## Making Predictions
### Step 1) Variable Selection and Model Fitting
The significance of the variables and model performance were evaluated by carrying out hypothesis testing to disprove the null hypothesis defined as: $H_0: \hat{\beta}_1 =0, \hat{\beta}_2=0,...,\hat{\beta}_n=0$, meaning that the change on the variable inputs ($X$) does not influence the probability of the expected outcome.

Using the Akaike information criterion (AIC) backward selection method, which models fit by maximising the maximum likelihood, the best performing model was chosen, and the result was:


In summary, the combination of _jobs_, _marital, education, balance, housing, loan, contact, month,_ _campaign_ and _poutcome_ would result in the best performing model. The model was fit, and the results presented as:




The main insights derived from the regression analysis were:







### Step 2) Model Performance Testing  
The logistic model was used to conduct predictions using the test data. The model predicted the expected probabilities of the outcome. The outcome was then determine based on the condition presented in Equation 1.



Thereafter, a comparison was made between the actual outcomes and the predicted outcomes. The results of the comparison between the actual and predicted values of the test data is presented



The accuracy of the model was calculated to be approximately 92% similar to the linear regression model, with the added advantage of not having to manipulate the predicted outcomes further. The measure of the model performance was then carried out by evaluating the model sensitivity and specificity, and finally, the ROC curve of the model was plotted. The results are presented in




### Step 3) New Data Predictions
The logistic regression model was chosen to carry out the predictions on the “check2021” data because the model performed better in predicting the categorical outcome compared to the linear model. The approach followed was to fit the logistic model to the new data taking into account only the significant variables determined from the regression process (refer to Figure 16). The summary of the predicted results is presented in



The model predicted 165 possible subscriptions (≈ 3%) out of the 5211 clients.  This result was considered valid because the same prediction pattern was observed in the model testing phase.






So, now that you know what logistic regression is and how it works, it's time to get out there and start making some predictions! Whether you're trying to predict the likelihood of a customer making a purchase or the likelihood of a patient developing a certain disease, logistic regression can be a valuable tool for understanding the relationships between different variables and making informed predictions about the future. Just remember to keep an open mind and stay curious, because you never know what the future might hold!






