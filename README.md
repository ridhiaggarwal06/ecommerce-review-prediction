# Customer Review Prediction for Nile (E-commerce Case Study)

#### Project Summary
This project predicts whether a customer will leave a positive or negative product review on an eCommerce platform. The aim was to help the business target the right customers for review requests, improve online reputation, and use incentives more efficiently.

The project was completed as part of a real-world analytics consulting assignment

#### Business Problem
Online reviews strongly influence customer trust and sales. However, requesting reviews from every customer is costly and ineffective.
The business wanted to:
* Predict which customers are likely to leave positive reviews
* Focus review requests on high-probability customers
* Improve overall rating quality in a cost-efficient way

#### Data Used
* Real transactional eCommerce data
* 90,000+ orders after cleaning
* Data from 8 linked tables including:
  - Orders, customers, products, payments, sellers, deliveries, and reviews
* Product categories translated into English for analysis

#### Approach:
1. Data Cleaning & Quality Checks:
* Joined 8 different datasets (orders, products, customers, payments, reviews, sellers, and delivery data) into one clean analysis table.
* Removed:
  - Orders where payment values did not match product and freight totals
  - Delivered orders with missing delivery dates
  - Undelivered orders that incorrectly had delivery dates
  - Rows with missing key values
* Retained real-world delivery delays and mismatches as they reflect actual operational issues rather than data errors.
* After cleaning and merging, the final dataset contained ~91,600 records.

2. New Features Created:
To better capture customer experience and order behaviour, several new columns were created, including:
* Delivery time – days from purchase to delivery
* Review time – time taken by customers to leave a review
* Item count – total number of products in each order
* Product size – calculated using length, width, and height
* Average review scores at:
  - Product level
  - Seller level
  - Product category level
* Encoded order delivery status into simple numeric groups:
  - Cancelled/unavailable
  - Delivered early
  - Delivered late
  - Shipped
  - Processing
These features helped capture delivery reliability, product scale, and customer experience more realistically.

3. Target Variable Creation:
Converted 1–5 star ratings into a binary outcome:
  - 1–3 stars → Negative
  - 4–5 stars → Positive
Chosen due to very few neutral (3-star) reviews.

4. Class Imbalance:
The dataset was imbalanced, with far more positive reviews than negative ones.
This was accounted for by:
* Using evaluation metrics that work well with imbalanced data (precision, recall, and F1-score)
* Interpreting results carefully to avoid being misled by high accuracy alone
 
5. Model Selection and Evaluation:
* Gradient Boosting Decision Trees (GBDT) and XGBoost were chosen because they work well with complex, non-linear data and handle imbalanced datasets effectively. XGBoost was especially useful due to its speed, scalability, and built-in overfitting control.
* Hyperparameter tuning was applied to ensure the models performed well not only on training data but also on unseen future orders.
* Precision, recall, and macro F1-score were used instead of accuracy alone to evaluate both positive and negative reviews fairly. The macro F1-score was prioritised to ensure the minority negative class was properly evaluated.

#### Key Insight
Customer reviews are most strongly influenced by delivery reliability, delivery speed, pricing, and order size. When delivery is delayed or unreliable, negative reviews become far more likely.

#### Business Value
If deployed, this solution could help the platform:
  - Increase the volume of positive online reviews
  - Improve customer trust and conversion
  - Use marketing incentives more effectively
  - Support data-driven operations and delivery improvements
    
#### Limitations
* The model relies on historical behaviour, which may not fully reflect future customer trends.
* Data imbalance leads to weaker performance in predicting negative reviews.
* Some features (average product/seller/category score) introduced data leakage risk and were later removed for realistic deployment.
* One review is recorded per order, even when multiple products are purchased, which creates ambiguity about which product influenced the rating.
* Binary classification may oversimplify how different customers interpret star ratings.
