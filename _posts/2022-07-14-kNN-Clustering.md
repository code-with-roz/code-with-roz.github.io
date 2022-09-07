---
layout: post
title: kNN Clustering 
categories: [Clustering]
---

Clustering is a fundamental statistical process. Clusterring enables us to categories different data points and thereafter infer key insights from the categories found and thereafter empower s in making decisions based on these insights drawn from the different categories. The process of categorising items based on colour, behaviour, shape, history is as old as the evolution of the human mind. We insiticively carry out clustering in our every day lives by categories the objects around us. Knowing that a "dog" falls under the category of "animals", and can be further classified as a "canine" under the "mammal" categroy is an example of sophisticated clustering processes that our minds conduct in a split second that came about from the extensive learning we underwent while in school. Primary is looking a lot more sofisticated than you thought, isn't it? 

Our goal as data scientists is to program such clustering processes into machines, and after countless iterations refine the the resulting clusters so that if new data is fed into this machine, it can accurately place the new data points in the right categories based on the similarity (or dissimilarity) metric programmed into the process. For example, let's consider retail, clustering processes can help us identify different customer segments based on factors such as age, spending habits, income or other demographic traits. This informations empowers retail companies to be able to make data-driven decisions on designing marketing campaigns, modifying products or whatever other initiatives that would result in increased profits (all within ethical bounds of course). 

Different clustering methods used in statistics include: Hierarchical clustering, k means clustering, ........ When considering real-world conditions in most cases unsupervised machine learning techniqes are the most appropriate, given the data properties are unkown or diffficult to interpret....... In these cases Density based clustering is used. 

In this post, I will explore the kNN mode seeking ensemble method proposed by Myhre et. al (2018), which involved forming a clustering ensemble consisting of repeated and bootstrapped runs of the recently developed kNN mode seeking algorithm. For more information you can find their published article here: .... This method enables the "deterministic" kNN mode seeking method to be applied as an unsupervised machine learning technique by introducing randomness into the selection process of the k-value and using bootstrapping techniques to increase the robustness of the method and find the optimum k-value based on the consensus value..... 

An arbitrary dataset is used, you can find the dataset here: ... All programming was done in R









References: 
Original Source code and data: Prof...., University of Pretoria.
Article: Myhre et. al (2018)

The approach of this post is to used the kNN mode seeking ensemble method on arbitrary data and measure the performance, while commenting on the 

Financial intitutions invest enourmous amounts of money running campaigns on new product offerings to their existing customers and to acquire new business through traditional media and (most recently) digital media strategies. The use of these marketing strategies is to determine the customer segments that would be most likely to subscribe to their product offerring. 

To determine these different customer segments, statistical analysis is usally carried out on historical data collected by the financial instituation (such as a bank), and statisticians and/or data scientist attempt to predict the likelihood of a customer (with a certain combination of attributes) subscrbing to a product. These results then inform the most appropriate marketing strategy that should be followed to maximise customer subscription. 

![](/images/reverie-demo.png)

Thus bringing us to the example of a marketing campaign ran by a Portuguese banking institution that had the goal of making predictions on whether an exisiting customer would subscribe to the "bank term deposit" product they were offering. The predictions made involved carrying out a Logistic Regression analysis taking into account the significant factors that would influence the probability of a customer saying "yes" to the product subscription. The marketing campaigns were based on phone calls (either cellular or telephone) and often multiple contact sessions with the client was necessary to assess the client’s receptivity to subscribing to the “bank term deposit” product.

Development of a proposed marketing strategy involved:
1. Feature selection process to determine the significant variables to be used in the regression process
2. Logistic regression and model performance evaluation to determine whether reliable predictions can be made using the estimated model
3. Insight derivation and conclusions on the most appropriate marketing strategy to be followed

## Feature Selection
The dataset can be found here: [Dataset](http://archive.ics.uci.edu/ml/datasets/Bank+Marketing). 

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

Given the features were not correlated, I went forward with the Logistic regression process to estimate a model. 

<div style="text-align: center;">
 <script async type="text/javascript" src="//cdn.carbonads.com/carbon.js?serve=CE7D6KJY&placement=wwwamitmerchantcom" id="_carbonads_js"></script>
</div>

## Making Predictions
### Step 1) Variable Selection and Model Development



Fork [this repository](https://github.com/amitmerchant1990/reverie), then rename the repository to `yourgithubusername.github.io`.

Alternatively, you can use [Use this template](https://github.com/amitmerchant1990/reverie/generate) button if you want to create a repository with a clean commit history which will use Reverie as a template.

Your Jekyll blog will often be viewable immediately at <https://yourgithubusername.github.io> (if it's not, you can often force it to build by completing step 2)

### Step 2) Model Testing  

Enter your site name, description, avatar and many other options by editing the `_config.yml` file. You can easily turn on Google Analytics tracking, Disqus commenting and social icons here.

Making a change to `_config.yml` (or any file in your repository) will force GitHub Pages to rebuild your site with jekyll. Your rebuilt site will be viewable a few seconds later at <https://yourgithubusername.github.io> - if not, give it ten minutes as GitHub suggests and it'll appear soon.

### Step 3) New Data Predictions

Create a new file called `/_posts/2019-2-13-Hello-World.md` to publish your first blog post. That's all you need to do to publish your first blog post! This [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) might come in handy while writing the posts.

> You can add additional posts in the browser on GitHub.com too! Just hit the <kbd>Create new file</kbd> button in `/_posts/` to create new content. Just make sure to include the [front-matter](http://jekyllrb.com/docs/frontmatter/) block at the top of each new blog post and make sure the post's filename is in this format: year-month-day-title.md

## Conclusions and Insights

You can categorize your content based on `categories` in Reverie. For this, you just need to add `categories` in front matter like below:

For adding single category:

```md
categories: JavaScript
```

For adding multiple categories:

```md
categories: [PHP, Laravel]
```

The contegorized content can be shown over this URL: <https://yourgithubusername.github.io/categories/>

## RSS

The generated [RSS feed](https://en.wikipedia.org/wiki/RSS) of your blog can be found at <https://yourgithubusername.github.io/feed>. You can see the example RSS feed over [here](https://www.amitmerchant.com/reverie/feed).

## Sitemap

The generated sitemap of your blog can be found at <https://yourgithubusername.github.io/sitemap>. You can see the example sitemap feed over [here](https://www.amitmerchant.com/reverie/sitemap).

## License

MIT


