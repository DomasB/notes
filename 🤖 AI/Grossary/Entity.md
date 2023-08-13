**What is an entity in a Feature Store?**
-----------------------------------------

In a [feature store](https://www.hopsworks.ai/dictionary/feature-store), an entity is represented as rows in a [feature group](https://www.hopsworks.ai/dictionary/feature-groups), where each row corresponds to a single instance of the object or concept. 

For example, a *customer\_id* could be a unique identifier for a customer in a *customer\_profile* feature group. In the [online store](https://www.hopsworks.ai/dictionary/online-store), the *customer\_id* (entityID) is a primary key to retrieve the latest [feature values](http://www.hopsworks.ai/dictionary/feature-value) for that customer. However, in the [offline store](https://www.hopsworks.ai/dictionary/offline-store), there may be many updates to the customer’s features over time, and we typically want to store those historical values, so we have a timestamp column identifying what the customer feature values were as of the point-in-time of the timestamp. In this case, the entityID can retrieve all the historical observations of feature values for that customer, while the primary key for each row is the (entityID, timestamp) pair.

