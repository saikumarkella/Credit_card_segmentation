# Credit Card Segmentation

## Problem Statement
A Bank wants to develop a system that it can assign customers to a specific group based on their usage of Credit Cards.So by Doing this they can apply Marketing stratagies.

### Data Overview 
The dataset was contains the information of 8950 customers with 17 attributes which will define the usage of credit card by the customer.

**Data Attributes :**

- CUST_ID: Credit card holder ID
- BALANCE: Monthly average balance (based on daily balance averages)
- BALANCE_FREQUENCY: Ratio of last 12 months with balance
- PURCHASES: Total purchase amount spent during last 12 months
- ONEOFF_PURCHASES: Total amount of one-off purchases
- INSTALLMENTS_PURCHASES: Total amount of installment purchases
- CASH_ADVANCE: Total cash-advance amount
- PURCHASES_ FREQUENCY: Frequency of purchases (Percent of months with at least one purchase)
- ONEOFF_PURCHASES_FREQUENCY: Frequency of one-off-purchases 
- PURCHASES_INSTALLMENTS_FREQUENCY: Frequency of installment purchases 
- CASH_ADVANCE_ FREQUENCY: Cash-Advance frequency
- AVERAGE_PURCHASE_TRX: Average amount per purchase transaction
- CASH_ADVANCE_TRX: Average amount per cash-advance transaction
- PURCHASES_TRX: Average amount per purchase transaction
- CREDIT_LIMIT: Credit limit
- PAYMENTS: Total payments (due amount paid by the customer to decrease their statement balance) in the period
- MINIMUM_PAYMENTS: Total minimum payments due in the period.
- PRC_FULL_PAYMEN: Percentage of months with full payment of the due statement balance
- TENURE: Number of months as a customer

**Framing in to a Machine Learning Problem**
It doesn't contains any target variables. So by given statement we need to do segementation . Let consider it as Unsupervised Problem .The problem statement doesn't specify any kind groups i.e quantities of groups.

**So Aim is we need to find the clusters using clustring techniques**

**Data Preprocessing and Exploratory Data Analysis**
- Some Attributes contains some missing values : Dealt with the Imputation Techniques.
- Performed univariae and Multivariate Analysis using a pair plots 
- heatmaps for correlations

*observations*

       - Some Attributes contains lot od skewness. to solve this we used some Transformers like log , and sqrt transformers
       - Dataset contains multicorrelated variables. To eliminate those things we can use reduction techniques like PCAbut by using this we cannot interpret the problem.
  
  - To deal with the categorical variables , one hot encoding used
  
**Data Preparation and Modelling :**
  
Here we derived some new attributes or KPIs
   
          - Monthly average purchase and cash advance amount
          - Purchases by type (one-off, instalments)
          - Average amount per purchase and cash advance transaction,
          - Limit usage (balance to credit limit ratio),
          - Payments to minimum payments ratio
          
 - concatenate with the original dataset 
 - normalized the data usiing min-max scale
 - by observations the dataset contains multicorrelated variables
 - So we used a PCA for the dimensionality reduction
 - we BUild a **kmeans clustring** on top of reduced variables.
 
 **Results :**
 - By using inter cluster and intra cluster metrics we got 4 clusters.
 
  
