**What is data validation for feature data?**
---------------------------------------------

***‍***ML [model training](http://www.hopsworks.ai/dictionary/model-training) or inference can crash if there are problems with input data, such as missing data or out-of-range data. Incorrect or out-of-distribution data can introduce the problem of [skew](https://www.hopsworks.ai/dictionary/skew) in the [inference](https://www.hopsworks.ai/dictionary/inference-data) or [[Training Data|training]] data. 

**Why is data validation important?**
-------------------------------------

Data validation for feature data is important to ensure the quality and consistency of the data used in machine learning models. Data validation also helps to maintain data integrity and avoid issues with [data quality](http://www.hopsworks.ai/dictionary/data-quality), reliability, and versioning. Note that there are some exceptions to the general data-must-be-clean rules. For example, you can have missing [feature values](http://www.hopsworks.ai/dictionary/feature-value) in a [[Feature Groups|feature group]], but you then impute those values in your training and inference pipelines. One way to do this would be to use [Scikit-Learn](https://scikit-learn.org/stable/) transformer pipelines that need to be consistently used in both training and inference to prevent skew.

**Example data validation rules for features**
----------------------------------------------

[**‍**Great Expectations](https://greatexpectations.io/) is a popular framework for defining “expectations” (declarative data validation rules) on feature values. Your [[Feature Pipeline|feature pipeline]] can apply expectations on all data that flows through it and apply a policy if an expectation fails, e.g., abort the current pipeline run, or log an alert. 

Here is an example code snippet of a Great Expectations rule for validating an age feature's value as within the range 0-120:


```python
{
  "expectation_type": "expect_column_values_to_be_between",
  "kwargs": {
    "column": "age",
    "min_value": 0,
    "max_value": 120,
    "parse_strings_as_datetimes": true
  }
}

```
This expectation will raise an error if any value in the “age” column is less than ‘0’ or greater than ‘120’ or if the value cannot be parsed as an integer.


LLM Tags:  #ml, #model_training, #inference, #skew, #training, #data-validation
LLM Tags:  #data-validation #data-integrity #ml  #hobbies
LLM Tags:  #expectations, #data-validation, #feature-pipeline