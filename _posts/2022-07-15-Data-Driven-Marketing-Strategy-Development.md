---
layout: post
title: Making Predictions using Logistic Regression
categories: [Regression]
---





Financial intitutions invest enourmous amounts of money running campaigns on new product offerings to their existing customers and to acquire new business through traditional media and (most recently) digital media strategies. The use of these marketing strategies is to determine the customer segments that would be most likely to subscribe to their product offerring. 

To determine these different customer segments, statistical analysis is usally carried out on historical data collected by the financial instituation (such as a bank), and statisticians and/or data scientist attempt to predict the likelihood of a customer (with a certain combination of attributes) subscrbing to a product. These results then inform the most appropriate marketing strategy that should be followed to maximise customer subscription. 

![](/images/reverie-demo.png)

Taking the example of the marketing campaign run by the Portuguese bank, we can derive the best strategy that should be followed to maximise the probability of customers subscribing to the new product offer of the bank.

The general marketing strategy development steps are:
1. Stating marketing objectives
2. **Identify the desirable customer segment**
3. Identify your competition
4. Describe your product/service
5. Define place (distribution strategy)

The article will be focused on **step 2** of this developmental process, where the desirable customer segment will be extracted from the historical data collected by the bank.

The data contains the records of previous phone calls carried out to market the new product offer to customers in attempt to get them to subscribe to it. The customer features considered were:

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

Initial data processing was carried out to determine the correlation (if any) between the different features listed above. Given the features are a combination of categorical and numeric type data, the following metrics were calculated:
1. Contingency Coefficient ($\mathcal{C}$) - Categorical Data "coerrelation"
2. One way ANOVA test - Categorical and Numerica data "correlation"
3. Pearson's correlation coefficient - Numeric data correlation

Since none of the features were correlated, I went forward with the Logistic regression process to estimate a model that would then be used to determine the density function and thereafter use kNN clustering to determine the most desirable customer segment.

The Logistic Regression process can be found in my previous post here: **Making Predictions using Logistic Regression**

The density function derived from the estimated model was then used to carry out kNN clustering to determine the most desirable customer segment based on the highest peak obtained from the clustering. 



## Feature Selection


The total data set consists of 50 422 observations with 16 attributes (including the response variable). The data set was split into two sets; one set was used for the regression process, while the other was used to conduct the predictions. The two sets will be referred to as the “Regression set” and the “Prediction set” respectively. The regression set consisted of 45 211 observations and the prediction set consisted of 5 211 observations.

The list of varibles considered were:

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

The data consisted of both numeric (continuous) variables and categorical variables, therefore, to determine whether there was any correlation between the attributes the following three metrices were used:
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




## Conclusions and Insights
Both the Linear and Logistic regression models performed decently in predicting the outcomes, however the logistic regression performed slightly better with the added advantage of not having to conduct further data manipulation to calibrate the outcomes. In addition, the logistic regression model included more variables in the regression process that were computed as insignificant with the linear model regression. Thus, the logistic regression model provided more information regarding the possible influence of other factors not considered by the linear model.

Overall, the logistic model was better suited to conducting the regression analysis given the categorical response variable. However, the use of a linear regression model was proven to be feasible, just more computationally expensive.

The value lies in the interpretation of the results.








