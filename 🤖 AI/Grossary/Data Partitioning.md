**What is data partitioning and how does it relate to feature stores?**
-----------------------------------------------------------------------

When you create a [feature group](https://www.hopsworks.ai/dictionary/feature-groups), you can select one or more features (columns) as the partition key, storing data with the same partition key values in the same directory. Partitioning can enable faster queries using a feature store’s Offline API, by enabling you to pass partition key values, and only results with those partition key values will be read in the query. For example, in [Hopsworks](https://www.hopsworks.ai/the-python-centric-feature-store), the [offline store](https://www.hopsworks.ai/dictionary/offline-store) uses Hive-style partitioning to store feature group partitions in directories. If you only want to create training data for users in the location “USA”, you can pass a filter to your feature view, and only data in the feature group’s subdirectory “USA” will be read, skipping the rest of the data in the feature group: 


```
# If ‘location’ is a partition_key in its feature group, then the query 
# will be pushed down and only read data for users in “USA”
training_data = feature_view.training_data().filter("location", "USA")

```
[Data modeling](https://www.hopsworks.ai/dictionary/data-modeling) for [feature stores](https://www.hopsworks.ai/dictionary/feature-store) involves organizing your entities and features into feature groups. In data warehousing, [dimensional modeling](https://docs.getdbt.com/terms/dimensional-modeling) is a data modeling technique that identifies entities and then decomposes your data into “facts” and “dimensions” related to those [entities](http://www.hopsworks.ai/dictionary/entity). 

