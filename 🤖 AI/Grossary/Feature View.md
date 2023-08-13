**What is a feature view?**
---------------------------

A feature view is a selection of [features](https://www.hopsworks.ai/dictionary/feature) (and labels) from one or more [feature groups](https://www.hopsworks.ai/dictionary/feature-groups). You create a feature view by joining together features from existing feature groups and optionally performing following steps: defining one or more of the selected features as labels, declaring a transformation ([feature encoding](https://www.hopsworks.ai/dictionary/encoding-for-features)) for one or more selected features, and returning only certain [feature values](http://www.hopsworks.ai/dictionary/feature-value) by applying a user-supplied filter condition.  

![feature view](https://assets.website-files.com/618399cd49d125734c8dec95/64367172260fae25f816fea7_T_CvT2tdDXkwmzUm_SRkdKveojnHNWR9mp8joCFNPp1rFlhgXRGyZZPpt16DIFlOeajTEav02t-mFy_CMbQdBPK0lwUDpA7dQ93szIv_e0BWQGgAhD_86yJdqEt4U9Adc7FiMOmSX91u12Wk5Gaz0w.png)As a feature view can include model-dependent transformation functions for features, it can be said to be aware of each feature’s feature type. The feature view also knows about the *entity\_id* (primary key) and *event\_time* columns for each feature in the feature view.  

![feature group example](https://assets.website-files.com/618399cd49d125734c8dec95/64367172b18c492619f34adf_FPY5oswLzyyzrZnK_SSQ4QqjoJ4dVU9q0rayiVQiaa5BrQ-R_xpNWXkNPO9JLlS0YF0wyKJqDF7ShfzSbmzmQ8j7UJg81mJ7SM_zPRRRoGt90T3mybL35D3EAvL7zCQ27Bah9ZBl4FtsTHPFfZr86g.png)**Why are feature views important?**
------------------------------------

The feature view is a representation of the features (and labels) used by one or more models. As such, it is a model-specific view of features/labels in the feature store. The feature view: 

* provides a unified interface for features used by a model for training and inference;
* prevents [data leakage](https://www.hopsworks.ai/dictionary/data-leakage) when [training data](https://www.hopsworks.ai/dictionary/training-data) by creating point-in-time consistent snapshots;
* prevents training/inference [skew](https://www.hopsworks.ai/dictionary/skew) for model-dependent transformations by providing declarative support for specifying transformations, and executing model-dependent transformations when reading feature data for training and inference;
* supports filters when creating training data and batch inference data, enabling support specialized models that share the same set of features. For example, if you want to train a model for users in different regions (e.g., USA, Europe, Asia), you can create training data with a filter for the geographic region, returning only training data for users in that geographic region.

**Example of a feature view**
-----------------------------

Suppose you have two feature groups for an e-commerce platform: **customer\_information** and **purchase\_history**. You want to create a feature view for predicting customer churn that combines relevant features from both feature groups.


```
 #connect to the feature store
import hopsworks
project = hopsworks.login()
fs = project.get_feature_store()

# get the feature group instances
fg1 = fs.get_or_create_feature_group(
        name="customer_information",
        version=1
      )

fg2 = fs.get_or_create_feature_group(
        name="purchase_history",
        version=1
      )
# select the features that will be used by the model
query = fg1.select_all().join(fg2.select_all())

# get the standard_scalar transformation function
standard_scaler = fs.get_transformation_function(name='standard_scaler')

# dictionary of "feature - transformation function" pairs
transformation_functions = {col_name: standard_scaler for col_name in df.columns}

feature_view = fs.create_feature_view(
    name='customer_churn',
    version=1,
    label = ['has_churned'],
    transformation_functions=transformation_functions,
    query=query
)

```
