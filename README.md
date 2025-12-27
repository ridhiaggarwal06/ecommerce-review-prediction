# Predictive-Analytics-Nile-Ecommerce

#### 📊 Business Overview
This project was developed for Nile, a large South American eCommerce platform. The primary objective was to build a predictive model to identify whether a customer would provide positive feedback (Review Scores 4-5) or negative feedback (Review Scores 1-3) based on their purchasing and delivery experience

By predicting these scores, Nile can proactively address customer dissatisfaction, optimize delivery operations, and refine marketing strategies to improve overall customer lifetime value (LTV).

#### 🛠️ Tech Stack
Language: Python
Libraries: Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn

#### 📈 Data & Feature Engineering
The analysis was performed on a comprehensive dataset of 107,258 records, merged from eight different sources (Orders, Products, Customers, Payments, etc.). Key features engineered to drive model accuracy included:
- Delivery Performance: Calculated the difference between the purchase date and the actual delivery date.
- Customer Engagement: Measured "Review Time"— the lag between a review request and the customer's response.
- Product Metrics: Derived "Product Size" (Length × Height × Width) to analyze its impact on shipping satisfaction.
- Aggregated Insights: Developed average review scores at the Product, Seller, and Category levels to capture historical satisfaction trends

#### 🤖 Modeling & Evaluation
I evaluated multiple Gradient Boosting frameworks to handle the non-linear relationships and class imbalance within the data

Performance Insight: The models achieved a 94-95% accuracy rate in predicting positive reviews. Hyperparameter tuning was utilized to ensure the models generalized well to unseen data and avoided overfitting

#### 💡 Key Business Insights
The analysis revealed the Top 5 Drivers of Customer Satisfaction:
- Delivery Status: On-time delivery is the strongest predictor of a 5-star review.
- Average Product Score: Historical product performance heavily influences new customer expectations.
- Delivery Time: Significant deviations from estimated delivery dates lead to immediate rating drops.
- Price: Influences the "perceived value"; higher prices correlate with stricter scoring criteria.
- Item Number (Quantity): Larger orders have a higher risk of dissatisfaction if even one item is defective.

#### 🚀 Strategic Recommendations
- Operational Focus: Prioritize logistics improvements in high-volume categories like "Health & Beauty" and "Sports/Leisure" to maintain high review scores.
- Risk Mitigation: Implement an automated alert for "Late Deliveries" so the marketing team can offer proactive discounts before a negative review is posted.
- Data Integrity: Moving toward deployment, I recommend auditing carrier-provided dates to ensure model inputs remain accurate
