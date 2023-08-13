What are data types for features?
---------------------------------

***‍***A [feature value](http://www.hopsworks.ai/dictionary/feature-value) is a data value. In programming languages, a [feature](https://www.hopsworks.ai/dictionary/feature) is represented as a primitive data type, such as an *int*, *string, array,* or *boolean*. Features are ultimately transformed into a numerical input format when they are used by [ML](https://www.hopsworks.ai/dictionary/ml) models for training or inference.

‍**Why are data types for features important?**
-----------------------------------------------

Data types for features are important because they determine how the feature values can be encoded and represented in a machine learning model. Choosing the appropriate data type for each feature can impact the accuracy and performance of the model. For example, if you have a numerical feature that a downstream model may want to normalize, you probably should use a float or double data type instead of an int data type as the normalized numerical feature values will lie in the range 0 to 1.

