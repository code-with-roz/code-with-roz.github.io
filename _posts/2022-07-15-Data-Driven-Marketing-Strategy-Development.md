---
layout: post
title: Developing Data Driven Marketing Strategies 
categories: [Regression | Clustering]
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










Marketing is creating value for your customers while extracting value from them (McDonald and Wilson, 2011). To create maximum value, finding a way to accurately target your desired customer segment is essential, however, determining this segment takes time and energy, but with access to the right type of data this process can be optimised using statistical analysis.
