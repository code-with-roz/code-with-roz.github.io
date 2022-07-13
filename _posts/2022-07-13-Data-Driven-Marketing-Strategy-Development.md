---
layout: post
title: Bank Marketing Strategy Development
categories: [Prediction]
---

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

|# | Variable label        | Variable description  |
|--| --------------------- | --------------------- | 
|1 | lorem ipsum           | lorem ipsum dolor     | 
|2 | lorem ipsum dolor sit | lorem ipsum dolor sit | 
|3 | lorem ipsum dolor sit | lorem ipsum dolor sit | 
|4 | lorem ipsum dolor sit | lorem ipsum dolor sit | 

The data consisted of both numeric (continuous) variables and categorical variables, therefore, to determine whether there was any correlation between the attributes the following three metrices were used:
1. Contingency Coefficient ($\mathcal{C}$) - Categorical Data "coerrelation"
2. One way ANOVA test - Categorical and Numerica data "correlation"
3. Pearson's correlation coefficient - Numeric data correlation

![](/images/reverie-demo.png)


## Identifying desireable customer segments


![](/images/reverie-demo.png)



- 
- Command-line free fork-first workflow, using GitHub.com to create, customize and post to your blog
- Fully responsive and mobile optimized base theme
- Sass/Coffeescript support using Jekyll 2.0
- Free hosting on your GitHub Pages user site
- All the SEO goodies comes in-built
- Markdown blogging
- Syntax highlighting using Pygments
    - [Dracula syntax theme](https://draculatheme.com/) included
- Disqus commenting
- Google Analytics integration
- Fuzzy search across blog posts
- Pagination of posts works out-of-the-box.
- Categorize posts out-of-the box
- RSS Feed
- In-built sitemap

<div style="text-align: center;">
 <script async type="text/javascript" src="//cdn.carbonads.com/carbon.js?serve=CE7D6KJY&placement=wwwamitmerchantcom" id="_carbonads_js"></script>
</div>

## Making Predictions




### Step 1) Linear regression

Fork [this repository](https://github.com/amitmerchant1990/reverie), then rename the repository to `yourgithubusername.github.io`.

Alternatively, you can use [Use this template](https://github.com/amitmerchant1990/reverie/generate) button if you want to create a repository with a clean commit history which will use Reverie as a template.

Your Jekyll blog will often be viewable immediately at <https://yourgithubusername.github.io> (if it's not, you can often force it to build by completing step 2)

### Step 2) Logistic 

Enter your site name, description, avatar and many other options by editing the `_config.yml` file. You can easily turn on Google Analytics tracking, Disqus commenting and social icons here.

Making a change to `_config.yml` (or any file in your repository) will force GitHub Pages to rebuild your site with jekyll. Your rebuilt site will be viewable a few seconds later at <https://yourgithubusername.github.io> - if not, give it ten minutes as GitHub suggests and it'll appear soon.

### Step 3) Publish your first blog post

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


