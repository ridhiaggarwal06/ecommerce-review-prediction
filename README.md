# Customer Review Prediction for Nile (E-commerce Case Study)

Customer reviews play a critical role in shaping trust and driving sales for e-commerce platforms. For Nile, a large South American e-commerce company, identifying whether a customer is likely to leave a positive or negative review can help improve service quality, reduce negative experiences, and strengthen brand reputation. Our project aimed to develop a predictive model to forecast review outcomes and inform operational improvements, including delivery efficiency and product quality.


The problem:
Nile, a leading e-commerce platform, faced the challenge of predicting whether customers would leave positive or negative reviews. With over 100,000+ order records, the company wanted to understand which factors most influenced satisfaction and how predictive modelling could improve customer experience.


Approach:
- Data Preparation
  - Integrated eight separate datasets into a single view of 91,000+ orders.
  - Cleaned anomalies such as mismatched delivery dates and missing values.
  - Engineered new features, including delivery time, review response time, product size, and order status categories (delivered early, delayed, cancelled, etc.).
 
- Model Selection and Evaluation
  - Gradient Boosting Decision Trees (GBDT) and XGBoost were chosen because they handle complex, non-linear relationships effectively and are well-suited for imbalanced datasets often seen in real-world reviews. XGBoost, in particular, was selected for its speed, scalability, and built-in regularisation, reducing the risk of overfitting.
  - Hyperparameter tuning was applied to strike a balance between accuracy and generalisation, ensuring the model performed well not only on training data but also on unseen future orders.
  - Precision, recall, and macro F1-score were used as evaluation metrics instead of accuracy alone. This choice ensured that both positive and negative reviews were measured fairly, even though the dataset contained far fewer negative reviews. The macro F1-score was particularly important, as it emphasises performance on minority classes that are business-critical (negative reviews).

- Insights from Features
  - Delivery reliability, delivery time, price, and order size emerged as the strongest predictors of customer satisfaction.
  - Faster and more reliable delivery strongly correlated with positive reviews.
  - Higher prices and late deliveries significantly increased the likelihood of negative reviews.

 
Outcome:
  - Models achieved ~80% accuracy and F1-score on unseen test data.
  - Predictive capability enables Nile to flag orders at risk of negative feedback before reviews are submitted.
  - Business teams can use the insights to prioritise improvements in logistics, pricing strategy, and product quality.


Business Impact:
  - Anticipating reviews allows customer support to intervene early, reducing complaint volumes.
  - Feature importance analysis provides clear evidence for investing in delivery performance and competitive pricing.
  - Predictive analytics can be scaled to other business areas, such as fraud detection or personalised recommendations, maximising long-term ROI from the data platform.

