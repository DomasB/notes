**What is feature selection?**
------------------------------

***‍***Feature selection is the process of finding existing [[Feature|features]], in potentially different [[Feature Groups|feature groups]], and joining them together along with the label(s) to define the set of features that will be used for training and inference for your model. Feature selection is performed with respect to a prediction problem that you want your model to solve. The selected features should not be redundant, should also not be prohibited for use, and should be feasible to compute in training and serving.

**When do I perform feature selection?**
----------------------------------------

When you want to train a model to solve a prediction problem, you select the features that you think you need for your model and include them in a [[Feature View|feature view]]. With the feature view, you can create a training dataset for training your model, and [feature vectors](https://www.hopsworks.ai/dictionary/feature-vector) for online models, and a batch of inference data for offline models. Over time, as your production model degrades in performance, you may need to change the set of selected features to train an improved version of your model. This involves creating a new version of your feature view and connecting it to your [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline) for use with the new model.

**Example of feature selection**
--------------------------------

In a customer churn prediction model, the feature selection process may involve evaluating various features such as customer age, account balance, and transaction history to determine which ones have the greatest predictive power for the model. The selected features would then be used in the training and inference pipelines for the model.

Here's an example of feature selection for churn prediction using a feature view in [Hopsworks](https://www.hopsworks.ai/the-python-centric-feature-store), that, in turn, is used to create training data for our churn prediction problem:


```python
 # select features from different feature groups
selected_features = customer_fg.select_all() \
    .join(transactions_fg.select_except(["cust_id"]))

fv = fs.create_feature_view(
    name='customer_churn',
    query=selected_features,
    label=['churn_status']
)

# create training data using the selected features in the feature view
X_train, X_test, y_train, y_test = fv.train_test_split(test_size=0.2)

```

LLM Tags:  #feature-selection, #ml
LLM Tags:  #ml, #prediction, #feature-view
LLM Tags:  #ml 