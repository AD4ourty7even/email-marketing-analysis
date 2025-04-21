# Email Marketing Campaign Analysis

## Project Overview

This project analyzes an email marketing campaign for an e-commerce site, focusing on understanding campaign performance and optimizing future email sends using machine learning. The analysis addresses four key questions:

1. What percentage of users opened the email and what percentage clicked on the link within the email?
2. How can we build a model to optimize future email sends to maximize the probability of users clicking on the link?
3. By how much would the model improve click-through rates, and how would we test that?
4. What interesting patterns exist in how the email campaign performed across different user segments?

## Dataset Description

The analysis uses three primary datasets:

1. **email_table.csv** - Contains information about each email sent:
   - `email_id`: Unique identifier for each email
   - `email_text`: Email length (long_text or short_text)
   - `email_version`: Personalization type (personalized or generic)
   - `hour`: Local time when the email was sent
   - `weekday`: Day of the week when the email was sent
   - `user_country`: Recipient's country
   - `user_past_purchases`: Number of previous purchases by the recipient

2. **email_opened_table.csv** - Contains IDs of emails that were opened:
   - `email_id`: Identifier of opened emails

3. **link_clicked_table.csv** - Contains IDs of emails where the link was clicked:
   - `email_id`: Identifier of emails where the link was clicked

## Technical Implementation

The analysis is implemented in Python using the following libraries:

- **pandas & numpy**: Data manipulation and analysis
- **scikit-learn**: Machine learning model development
- **xgboost**: Gradient boosting implementation
- **imbalanced-learn**: Handling class imbalance with SMOTE
- **matplotlib & seaborn**: Data visualization
- **statsmodels**: Statistical analysis and hypothesis testing

## Key Findings

1. **Current Campaign Performance**:
   - 10.35% open rate, 2.12% click rate, 20.48% click-to-open rate

2. **Model Performance**:
   - Achieved high precision, recall, and F1-scores for click prediction
   - ROC-AUC score of 0.97+ demonstrates excellent predictive power

3. **Expected Improvement**:
   - Model-based targeting can increase CTR by 200-250%
   - Optimal strategy targets the top 20-30% of users with highest click probabilities

4. **Segment-Specific Insights**:
   - English-speaking markets (UK/US) outperform non-English markets (ES/FR) by 3x
   - Short emails get 28% higher click rates than long emails
   - Personalized emails increase clicks by 81% compared to generic emails
   - Mid-week emails perform 40% better than weekend emails
   - Users with high purchase history are 3x more likely to engage with emails

## File Structure

- **answers.ipynb**: Main Jupyter notebook containing analysis and answers to all questions
- **README.md**: Project documentation
- Data files (should be placed in the same directory):
  - email_table.csv
  - email_opened_table.csv
  - link_clicked_table.csv



## Recommendations for the Marketing Team

1. **Implement Targeted Email Strategy**:
   - Use the predictive model to score and rank users by click probability
   - Focus on the top 20-30% of users for maximum ROI

2. **Optimize Email Content and Timing**:
   - Keep emails concise (shorter performs better)
   - Always use personalization
   - Send during mid-week, working hours
   - Customize timing by region

3. **Segment-Specific Strategies**:
   - Create different approaches for high vs. low engagement users
   - Consider localization for non-English markets
   - Prioritize users with purchase history

4. **Test and Iterate**:
   - Implement A/B testing as outlined in Question 3
   - Continuously update the model with new campaign data
   - Experiment with different content strategies for different segments

## Future Work

- Implement ongoing model retraining with new campaign data
- Explore more advanced personalization strategies
- Develop automated email scheduling system based on predicted optimal send times
- Expand analysis to include email subject line optimization
- Integrate with product recommendation system for personalized content

