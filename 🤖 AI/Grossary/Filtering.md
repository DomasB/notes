**What is data filtering?**
---------------------------

Data filtering is an operation on a dataset (such as a DataFrame) that defines which data to extract or remove from the dataset. For example, in a dataset containing all customers in the world, when creating [training data](https://www.hopsworks.ai/dictionary/training-data), you might only want to read the training data for customers resident in a particular geographical region (e.g., North America, Japan,...), Here, you would define a filter on a *region* feature when creating training data as shown below.


```
 feature_view = fs.get_feature_view(
name='customer_churn', version=1)

X_train, X_test, y_train, y_test = fv.train_test_split(test_ratio=0.2).filter("region==USA")

```
