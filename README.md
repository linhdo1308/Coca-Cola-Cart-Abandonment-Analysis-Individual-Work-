# 1. An overview of the project

## a. Business Problem
Cart abandonment is when online shoppers add items to their digital cart but leave before paying. This represents a major revenue loss caused by multiple factors such as surprise costs (shipping/taxes), complex checkouts, forced sign-ups, slow sites, or lack of trust. In this project, we want to understand the patterns behind cart abandonment on Coca-Cola B2B platform and come up with actionable recommendations to recover cart abandonment.

## b. Analytical Methodology
From the clickstream data on GA4 and order window data, we created a dataset where each row represents a unique order window of a customer. In addition, we created another customer dataset where each row represents a unique customer and their aggregated purchasing behaviors. 


Our goal is (1) to discover browsing patterns that lead to cart abandonment in general and (2) to understand different customer segments based on purchasing behaviors. Therefore, we develop two main models: customer-level model and order-window model using different machine learning algorithms such as Logistic Regression, Boosted Logistic Regression, Random Forest, Decision Tree. Throughout the model development, we downsampled on the minority class (cart abandonment) and conducted feature engineering to understand the feature importance and at the same time, improve the model performance. 

In general, our best model (Boosted Logistic Regression) achieves an overall 93% accuracy and a Recall of 87%.

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

# 3. My contribution in the group project:

In this project, I contributed to exploratory data analysis, feature engineering and order-window modelling. While feature-engineering, I discovered some features that could improve our models without exposing to data leakage. These features are then applied in customer-level modelling as well.
