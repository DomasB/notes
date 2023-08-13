**What is an on-demand transformation?**
----------------------------------------

**‍**An on-demand transformation is a [feature function](https://www.hopsworks.ai/dictionary/feature-function) that is used to compute an [on-demand feature](https://www.hopsworks.ai/dictionary/on-demand-features). It is run both in an [online inference pipeline](https://www.hopsworks.ai/dictionary/online-inference-pipeline) and in a [feature pipeline](https://www.hopsworks.ai/dictionary/feature-pipeline). In the online inference pipeline, the on-demand feature function takes as input data only available at request-time (it may also use pre-computed features from the feature store), while in the feature pipeline the on-demand feature function takes as input historical data.

**Examples of on-demand transformations:**
------------------------------------------

1. Calculate the time since the last user interaction.
2. Compute the current temperature based on a live sensor data reading.
3. Derive the current zipcode of a user from their GPS coordinates.

Here is a short snippet showcasing an on-demand transformation that calculates the time since the last user interaction in an online inference pipeline:


```
 import time

def time_since_last_interaction(last_interaction_timestamp):
    current_time = time.time()
    time_diff = current_time - last_interaction_timestamp
    return time_diff

precomputed_features=feature_view.get_feature_vector({"id": 123})
time_since_last = time_since_last_interaction(
precomputed_features[0]) # 'last_interaction' at offset '0'
print("Time since last interaction (seconds):", time_since_last)

```
This example demonstrates a simple on-demand transformation (feature function) that computes the time since the last user interaction based on the current time and the timestamp of the last interaction (a [lag feature](https://www.hopsworks.ai/dictionary/lagged-features)). 

This feature function can also be applied both in the feature pipeline using historical data, as shown below:


```
 # import the same code for the on-demand feature fn as
# used in the online inference pipeline
import time_since_last_interaction

# read Pandas DataFrame from historical store
user_logins_df = pd.read_csv("user_logins.csv")

# Use the on-demand feature function to compute the feature 
user_logins_df['time_since_last'] = 
user_logins_df.apply(lambda x: time_since_last_interaction(
user_logins_df['last_login']), axis=1)

```
