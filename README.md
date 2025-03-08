# E-commerce-Customers-Segmentation
with a dataset consisting of five interrelated tables, each containing crucial information about customers, transactions, branches, and merchants.,
1- Build a Dashboard for Stakeholders 
2- Customer Segmentation Using Unsupervised Learning


📌Dataset Overview:
a dataset consisting of five interrelated tables, each containing crucial information about customers, transactions, branches, and merchants. 
The tables are described as follows:
1. Customers Table:
   
- customer_id: Unique identifier for each customer.
- join_date: The date the customer joined.
- city_id: The ID representing the customer's city.
- gender_id: The ID representing the customer's gender.

2. Genders Table:
   
- gender_id: Unique identifier for each gender.
- gender_name: Name of the gender (e.g., male, female).

3. Cities Table:
   
- city_id: Unique identifier for each city.
- city_name: Name of the city.

4. Transactions Table:
   
- transaction_id: Unique identifier for each coupon transaction.
- customer_id: ID of the customer who performed the transaction.
- transaction_date: The date the coupon was claimed.
- transaction_status: Status of the coupon (e.g., claimed, burnt).
- coupon_name: The name of the coupon.
- burn_date: The date the coupon was burnt.
- branch_id: ID of the branch where the coupon was burnt.

5. Branches Table:
   
- branch_id: Unique identifier for each branch.
- merchant_id: ID of the merchant who owns the branch.

6. Merchants Table:
   
- merchant_id: Unique identifier for each merchant.
- merchant_name: Name of the merchant.



## Customer Segmentation Using Unsupervised Learning 

- Step 1: Understanding the Dataset
- Step 2: Feature Selection (Data Preprocessing) :
         Coupon-Related Features ----> 'customer_id','time_between_transactions', 'time_to_burn', 'subscribed_duration', 'gender_name', 'city_name', 'transaction_status', 'coupon_name'
- Step 3: Handling Categorical Data
- Step 4: Scaling Numerical Features
- Step 5: Finding Optimal Clusters for K-Means
         - Elbow Method (using Inertia)
         - Silhouette Score (to measure clustering quality)
- Step 6: Choosing the Clustering Algorithm (visualization)
         - Apply PCA to reduce dimensions to 2D
         - Apply t-SNE for better separation
- Step 7: Model Training & Evaluation using:
         - Inertia (lower is better)
         - Silhouette Score (higher is better)
         - DBSCAN clustering density (if using DBSCAN)

# results:

1- features: 'gender_id', 'city_id', 'branch_id' ,'merchant_id','transaction_status', 'coupon_name', 'time_between_transactions', 'time_to_burn', 'subscribed_duration'
2- check correlation: transaction_status_subscribed with time_to_burn , subscribed_duration --> remove transaction_status_subscribed , subscribed_duration
![Image](https://github.com/user-attachments/assets/d909d1d0-8400-4173-83ef-c4483b8a77a1)         |       ![Image](https://github.com/user-attachments/assets/c1842e26-0373-480e-b019-79c7f3f6bc02)
-----
3- Finding Optimal Clusters for K-Means 
![Image](https://github.com/user-attachments/assets/15f2ca9d-47ad-4cbd-bf98-13b22fb8a557)         |       ![Image](https://github.com/user-attachments/assets/55e88e74-9524-4b8a-99ed-9b776546a803)
-----
4- Model Training & Evaluation using:   (0  ,  1882) | (1  ,  1736) | (2  .  1382)
![Image](https://github.com/user-attachments/assets/4340f8ae-51b7-4abe-831b-2846c9a6373d)         |        ![Image](https://github.com/user-attachments/assets/198cca2c-83c2-428d-a36a-ddc40e78e9d9)
-----
5- 
# Cluster 0: Balanced Customers (Largest Group - 1882 customers)
- Gender & City: Neutral effect (near 0), meaning gender and city distribution is well-balanced.
- Branch & Merchant: Lower engagement with branches and merchants, suggesting fewer interactions.
- Coupon Usage: Slightly positive, meaning these users engage with coupons but not significantly.
- Transaction Frequency: Moderate time between transactions (close to zero), indicating they transact at a steady pace.
- Time to Burn Coupons: Neutral, meaning they neither delay nor immediately use their coupons.

# Cluster 1: Occasional Users (1736 customers)
- Gender & City: Slightly lower values, meaning these users might belong to a slightly different demographic.
- Branch & Merchant: Higher than Cluster 0, meaning they interact with specific branches and merchants more.
- Coupon Usage: Slightly negative, indicating less frequent coupon use.
- Transaction Frequency: Higher time between transactions, meaning they transact less frequently.
- Time to Burn Coupons: Neutral, suggesting they use coupons at a normal rate when they do engage.

# Cluster 2: High-Value Customers (1382 customers)
- Gender & City: Higher in gender impact, possibly indicating stronger engagement from a particular gender.
- Branch & Merchant: High interaction, meaning they frequently visit and engage with specific branches and merchants.
- Coupon Usage: Slightly negative, but still relatively engaged compared to others.
- Transaction Frequency: Lower time between transactions, meaning they transact frequently.
- Time to Burn Coupons: Slightly positive, meaning they take a bit longer to redeem coupons but still use them.

| Cluster  |	Customer Type  |	Behavior	Recommended Coupons|
| 0 | Balanced Customers	| Steady engagement, moderate transactions	Tiered loyalty rewards, personalized coupons, small but frequent discounts|
| 1 |	Occasional Users	| Less frequent transactions, some branch/merchant preference	Time-limited discounts, event-based promotions, cashback incentives|
| 2 |	High-Value Customers |	Frequent transactions, high engagement with branches/merchants	Premium coupons, early-access deals, referral rewards|

# recommendations:
- Offer time-limited discounts to encourage more frequent purchases.
- Offer re-engagement discounts to bring them back.   (cluster 1)
- Provide premium coupons or exclusive rewards to maintain their loyalty. (cluster 2)

FUTURE STEPS:
1- other patterns discovery
2- Feature Engineering: Introduce additional behavioral metrics to improve separation.
3- Try a Different Clustering Algorithm:
      - Gaussian Mixture Model (GMM) can capture soft boundaries between clusters.
      - DBSCAN might better identify dense regions and outliers.
4- Cluster Profiling with Decision Trees
