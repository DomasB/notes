**What is a feature vector?**
-----------------------------

A feature vector is a row of [feature values](http://www.hopsworks.ai/dictionary/feature-value). A training sample for a model includes a feature vector and the label(s). In [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline), a feature vector is the input values to a model that, in turn, returns a prediction. In [online inference pipelines](https://www.hopsworks.ai/dictionary/online-inference-pipeline), when you have a feature store, you can retrieve a precomputed feature vector. For this, your online application provides the *entity\_id* ( primary key(s)) that is used by the feature store to return a feature vector of [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) for the model. The precomputed feature vector may be joined with [on-demand features](https://www.hopsworks.ai/dictionary/on-demand-features) to produce the final (encoded) feature vector used by the model to make a prediction.

**Examples of feature vectors**
-------------------------------

Let's consider a dataset of houses with two features, the size of the house in square feet and the number of bedrooms, and a label, the price of the house. A feature vector for a specific house might look like:


```python
 # house-id '1': 1500 square ft, 3 bedrooms, price $1m
row = [1, 1500, 3, 1000000]  

# the features from the row 
feature_vector = [1500, 3] 

# label and entity_id for the row
label = [1500, 1000000] 
row_entity_id = [1]

```
Below is a tabular figure showing the same feature vector as in the above source code, along with names for the features (*area\_sq\_ft*, *number\_bedrooms*), the label (*price*), entity\_id (*house\_id*), timestamp (*valuation\_ts*):

![](https://assets.website-files.com/618399cd49d125734c8dec95/64b26b1a104d31b97a5ae157_PGcyi72jptXs6sEDnkO6DeZGdW_KKRl5YPMlNtZfVqtQD8YHBEa2qcot7IMk_J43xP5z9beY18o85aVLNylSpj8z2tCQuINuHJLPuc4N8kJsHbYpgFQwtwfSLx3EdUjJ8TF3VqjoBEGg4iFDIICyNmI.png)‍**Are feature vectors related to vector databases?**
-----------------------------------------------------

No. A feature vector is the input to a ML model for training or inference. A vector, stored in a vector database, is typically a compressed representation of high dimensional data, created with an embedding model. Feature vectors typically consist of numerical data, as most ML algorithms require numeric data as input, but some ML algorithms, such as CatBoost, support categorical data as input. Similarly, feature vectors input to Scikit-Learn pipeline for training or inference can take mixed input data (categorical features are typically encoded as numbers in the pipeline before being input to the model).

‍

**Read feature vectors from a Feature Store for Online Inference**
------------------------------------------------------------------

A feature store can be used to retrieve a single feature vector of precomputed features for an *entity\_id*. This enables online models to use historical and contextual precomputed features in their predictions, enabling higher quality predictions.

In this example, in [Hopsworks](https://www.hopsworks.ai/the-python-centric-feature-store), we use a feature view’s [**get\_feature\_vector**](https://docs.hopsworks.ai/feature-store-api/latest/generated/api/feature_view_api/#get_feature_vector) method to retrieve the feature vector:


```python
feature_view = fs.get_feature_view("house_prices", version=1)

# Retrieve the feature vector using the entity_id (primary key)
entry = {"house_id": 1}
feature_vector_array = feature_view.get_feature_vector(entry)

```
You can retrieve a batch of feature vectors of precomputed features for a batch of *entity\_ids* using the feature view’s [**get\_feature\_vectors**](https://docs.hopsworks.ai/feature-store-api/latest/generated/api/feature_view_api/#get_feature_vectors) method. In this case, we retrieve the feature vectors as a Pandas DataFrame:


```python
feature_view = fs.get_feature_view("house_prices", version=1)

# Retrieve feature vectors as a DataFrame using entity_ids
entries = {"house_id": [1, 32, 42]}
feature_vectors_df = feature_view.get_feature_vectors(entries, return_type="pandas")

```

 #ml, #data-analysis
LLM Tags:   #inference-pipeline, #online-inference
LLM Tags:  #data-science #mllib #pandas #data-analysis
LLM Tags:  #ml #ml-model #embedding #vector-database
LLM Tags:  #online-inference #feature-store #prediction
LLM Tags:  #data-analysis #ml #ai #housingprices