# Subscription Box Retail Business Model - Personalize Assorment Optimization
## Context
The subscription box retail business model has been one of the fastest growing parts of e-commerce 
in the past decade (e.g., see here and here). This problem is inspired by the beauty subscription box 
company Birchbox (see https://www.birchbox.com/). Subscribers pay a fixed fee to receive a monthly 
package of 5 samples of beauty products. They then have the option to purchase the items they like 
most.  
  
At the heart of Birchbox’s business model is their personalized assortment algorithm – how do we 
decide which five samples to send to each customer every month? The real problem spans several 
analytics dimensions:  
  
**Descriptive:** How do we gather information about customers and then process that information to 
make it useful for the prediction algorithms?  
**Predictive:** How do we take the characteristic information about products and customers to predict the 
purchase probability of each customer-product match?  
**Prescriptive:** Which 5 products should we assign each customer to achieve our objectives while 
adhering to our constraints?  
  
Naturally, this problem will focus on the prescriptive part of the process – we will take the other parts 
as given and simplified in certain regards. I have also reduced the size of the problem considerably to 
reduce computation times (the real problem contains more than a million customers and over 800 
brand partners). Nevertheless, the underlying structure of the problem and the high-level processes 
involved to solve it remain realistic. 
## Data
The file “Birchbox_data.xlsx” contains 2 sheets.   

The “item info” sheet contains information about the samples Birchbox has in stock:  
* Item – an index number for the SKU
* Category – an integer denoting the type of sample (lotion, cleanser,…etc)
* Inventory – the number of sample units available to ship this month
* Sample cost – the cost to send the sample.
* Margin if purchase – the profit if a customer decides to purchase the sample product.
* PurchaseProb_X – the output of the proprietary prediction model that predicts the probability 
of purchase for a customer in segment X.   
The “cust info” sheet contains information about the customer subscriber base:  
* Cust – an index number for the customer
* Seg – the segment number to be used to determine the purchase probability
* Item X – a binary indicator for each item, where a 1 indicates that the customer has already 
received that sample in the past.
