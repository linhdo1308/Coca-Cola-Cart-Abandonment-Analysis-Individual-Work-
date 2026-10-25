# 1. An overview of the project

## a. Business Problem
Cart abandonment is when online shoppers add items to their digital cart but leave before paying. This represents a major revenue loss caused by multiple factors such as surprise costs (shipping/taxes), complex checkouts, forced sign-ups, slow sites, or lack of trust. Specifically, total revenue lost within 12 months from cart abandonment at Swire Coca-Cola is $246,944. In this project, we want to understand the patterns behind cart abandonment on Coca-Cola B2B platform and come up with actionable recommendations to recover cart abandonment.

## b. Analytical Methodology
From the clickstream data on GA4 and order window data, we created a dataset where each row represents a unique order window of a customer. In addition, we created another customer dataset where each row represents a unique customer and their aggregated purchasing behaviors. 

Our goal is (1) to discover browsing patterns that lead to cart abandonment in general and (2) to understand different customer segments based on purchasing behaviors. Therefore, we develop two main models: customer-level model and order-window model using different machine learning algorithms such as Logistic Regression, Boosted Logistic Regression, Random Forest, Decision Tree. Throughout the model development, we downsampled on the minority class (cart abandonment) and conducted feature engineering to understand the feature importance and at the same time, improve the model performance. 

In general, our best model (Boosted Logistic Regression) achieves an overall 93% accuracy and a Recall of 87%.

## c. Business Value of the Solution
Implementing our solutions, Swire Coca-Cola can work on targeted interventions to recover these cart abandonment and increase their revenue. 
- 10% recovery: $21,484 potential savings
- 20% recovery: $42,968 potential savings
- 25% recovery: $53,710 potential savings
- 50% recovery: $107,421 potential savings
- 75% recovery: $161,131 potential savings
- 100% recovery: $214,841 potential savings


# 2. Business Insights and Recommendations:
## a. Business Insights
- Customers who view product details tend to abandon more than who don't.
- Customers who spend more time browsing the platform and view the cart multiple time are more likely to abandon.
- The more a customer engages with the website, the more likely they are to abandon.
- Larger order sizes are less likely to be abandoned.
- Abandonment behavior is repetitive.

## b. Recommendations:
For chronic abandoners, the focus is to help them create a purchasing habit and address any concerns around contract:
- Offering stable pricing tied to committed order schedules 
- Revisit the contract terms since they might have some sudden changes in business conditions that lead them to abandon their cart. Our hypothesis is that many chronic abandoners drop orders because current agreements don’t match their actual operational patterns or they face business contraints, so adjustments can stabilize their purchasing behavior

For heavy browsers who still complete purchases, the focus is on reducing decision friction due to confusing products:
- Proactive consultation from the account manager to guide these customers toward the optimal product mix based on what similar locations typically order.
- Add curated product bundles on the website. This shortens the browsing process and helps them place orders faster and more consistently

# 3. My contribution & Learning Points:
In this project, I contributed to exploratory data analysis, feature engineering and order-window modelling. While feature-engineering, I discovered some features that could improve our models without exposing to data leakage such as view_product_details, mycoke_cart_count, total_orders_running and many more. These features are then applied in customer-level modelling as well.

In this project, I learned:
- How data are stored and distributed in a large beverage company like Coca-Cola. For example, data in Google Analytics 4 are recorded as every single interaction of the customer with the platform.
- Understand what datasets are needed and not needed when facing with large number of datasets by starting from the business questions, analytical goals and sticking to it. In addition, noting down every hypothesis as they come up are very helpful to keep the analytics on track and organize the thinking process.
- How to deal with messy big data in real world and generate actionable insights from them

# 4. Difficulties during analytical and modelling process:
- Conducting feature engineering on big data are time-consuming, especially as we want to try out new features or run through the notebook again
- Fine-tuning the model is difficult. It seemed to us that there is a cut-off point where we could not improve the model performance despite adding features and changing hyper-parameters.
- Even though domain knowledge is very critical in data analytics, our group do not have much industry knowledge or customer understanding of Coca-Cola.
- We want to work on causal inference model to dig deeper into customer behaviors, but data on previous periods were not available.

- While building a fill rate analysis, we found that the sales table only covers about a third of order lines. We tested the obvious explanations: ID formats, units, timing, and order revisions. None of them explained it. The gap is consistent over time but varies by channel, which suggests the data extract was filtered somehow. It makes sense because the Swire team might not want to share all business data for just a Capstone Project. So we left fill rate out rather than report a misleading number. The good news: it doesn’t affect our core cart abandonment analysis, and where we do have both records, fulfillment looks very strong.
