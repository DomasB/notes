---
aliases:
  - feature function
tags: "#ml #feature-engineering #pandas #data-frame"
---
## What are feature functions?

A feature function is a function that computes one or more [[Feature Value|feature values]] from input data. 

## Why is it important to write functions to compute features?

It is possible to write a notebook that computes [[Feature|features]] that are stored in [[Feature Groups|feature groups]]. However, by factoring your feature computations into functions, they can be independently tested, included in both a [[Feature Pipeline|feature pipeline]] and an [[online inference pipeline]] (if they compute [[on-demand features]]), reused in different feature pipelines, and independently developed.

## Example of a feature function
In a customer churn prediction model, a feature function might be created to calculate the average amount of time between a customer's purchases. This feature could be useful in predicting whether a customer is likely to churn, as customers who make more frequent purchases are less likely to churn. The feature function would take as input the customer's purchase history and return the average time between purchases as a feature value. The example is taken from the [Hamilton micro-framework](https://github.com/DAGWorks-Inc/hamilton) that helps structure and execute features as feature functions.


```python
import pandas as pd

def average_time_between_purchases(purchase_history):
    # Convert purchase_history to a pandas dataframe
    df = pd.DataFrame(purchase_history, columns=['timestamp', 'amount'])
    
    # Calculate the time between each purchase
    df['last_purchase_time'] = df['timestamp'] - df['timestamp'].shift(1)
    
    # Calculate the average time between purchases
    average_time_between_purchases = df['last_purchase_time'].mean()
    
    return average_time_between_purchases

```
In the above code snippet, the feature function takes as input a purchase history, which is a list of tuples containing the timestamp and amount of each purchase. The function first converts the purchase history to a pandas dataframe, then calculates the time between each purchase and the average time between purchases. The average time between purchases is returned as a feature value that can be used in a machine learning model. 