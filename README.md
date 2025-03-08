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
