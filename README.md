# Ecommerce recommendation system design using Python
A well developed recommendation system will help businesses improve their shopper's experience on website and result in better customer acquisition and retention.

The recommendation system, I have designed below is based on the journey of a new customer from the time he/she lands on the business’s website for the first time to when he/she makes repeat purchases. 

The data sets are from:
1. Amazon product ratings by multipe users, Data Source: https://www.kaggle.com/skillsmuggler/amazon-ratings
2. Home Depot products with descriptions, Data Source: https://www.kaggle.com/c/home-depot-product-search-relevance/data
3. Twitter data: https://www.kaggle.com/datasets/jp797498e/twitter-entity-sentiment-analysis

## System Design Overview
The recommendation system is designed in three parts based on the business context:

1. ### Cold Start Recommendation:
   When a new customer without any previous purchase history visits the e-commerce website for the first time, they are recommended the most popular products sold on the company's website or we get their inference through their microblogging data and recommend similar products.

2. ### Collaborative Filtering:
   Once the customer makes a purchase, the recommendation system updates and recommends other products based on the purchase history and ratings provided by other users on the website using collaborative filtering techniques.

3. ### Content-Based Recommendation:
    For businesses without any user-item purchase history, a search engine-based recommendation system is designed. The product recommendations are based on textual clustering analysis given in the product description.

## Strategy/Techniques used: 
### 1. Cold Start Problem Solution
For new businesses without any user-item purchase history, sentiment analysis on social media data (e.g., Twitter) is performed to categorize tweets into positive, neutral, and negative sentiments. This helps identify trends and popular products based on customer opinions.

#### Sentiment Analysis using VADER and BERT:
VADER: A rule-based sentiment analysis tool specifically designed for social media text.

BERT: A state-of-the-art machine learning model used for text classification and sentiment analysis.

#### Example Workflow:
1) Preprocessing: Clean and preprocess the text data to remove noise and irrelevant information.
2) Sentiment Analysis: Use VADER and BERT to classify tweets into positive, neutral, or negative sentiments.
3) Categorization: Assign categories to products based on the sentiment analysis results.

### 2) Product Popularity-Based Recommendation System
This strategy targets new customers with the most popular products sold on a business's website, which is useful for addressing the cold start problem of a recommendation engine.

Analysis:

The above graph shows the most popular products (arranged in descending order) sold by the business. For example, product ID #B001MA0QY2 has sales of over 7000, and the next most popular product, ID #B0009V1YR8, has sales of 3000, etc.

![image](https://user-images.githubusercontent.com/38769913/51401953-27a90a00-1b1a-11e9-9dca-c18c9d592121.png)

### 3) Model-Based Collaborative Filtering System: 

This technique recommends items to users based on purchase history and the similarity of ratings provided by other users who bought similar items. A model-based collaborative filtering technique is chosen as it helps in predicting products for a particular user by identifying patterns based on preferences from multiple user data.

Recommending top 10 highly correlated products in sequence based on a customer's purchase history:

Product Id #: Here are the top 10 products to be displayed by the recommendation system to the above customer based on the purchase history of other customers on the website.

![image](https://user-images.githubusercontent.com/38769913/51402144-a8680600-1b1a-11e9-8c45-3f8177516a48.png)

### 4. Item-Item Based Collaborative Filtering System

This system is useful for a business without any user-item purchase history. A search engine-based recommendation system can be designed for users where the product recommendations are based on textual clustering analysis given in the product description. Predictions are done based on other products from the same cluster (based on text analysis of the product description) on key search words.

![image](https://user-images.githubusercontent.com/38769913/51402355-393ee180-1b1b-11e9-9f98-8af45733d496.png)

## Summary
This recommendation system works best if a business is setting up its e-commerce website for the first time and does not have user-item purchase/rating history initially. This system helps users get good recommendations to start with. Once the buyers have a purchase history, the recommendation engine can use the model-based collaborative filtering technique to provide more personalized recommendations.

By implementing this comprehensive recommendation system, businesses can enhance their customers' shopping experience, leading to increased customer satisfaction and loyalty.
