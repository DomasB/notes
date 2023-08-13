**What are python UDFs?**
-------------------------

In [ML](https://www.hopsworks.ai/dictionary/ml), a Python UDF (user-defined function) is a function written by a user, typically to implement a [feature function](https://www.hopsworks.ai/dictionary/feature-function). Python UDFs are popular for [feature engineering](https://www.hopsworks.ai/dictionary/feature-engineering) as they can be applied to a Pandas DataFrame to transform it into one or more features. Python UDFs are flexible and allow users to define custom transformations, but they can be slower than vectorized Pandas UDFs due to the overhead associated with Python's interpreted nature.


```
 import pandas as pd

# Create a sample DataFrame
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# Define a UDF to add two numbers
def add_numbers(a, b):
    return a + b

# Apply the UDF to create a new column in the DataFrame
df['C'] = df.apply(lambda row: add_numbers(row['A'], row['B']), axis=1)

```
