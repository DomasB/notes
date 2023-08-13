**What does backfilling training data mean?**
---------------------------------------------

***‍***Backfilling [training data](https://www.hopsworks.ai/dictionary/training-data) from a [feature store](https://www.hopsworks.ai/dictionary/feature-store) means creating a point-in-time consistent snapshot of feature data that will be used to train one or more models. Some of the feature data that is used for backfilling may be materialized in the feature store, while some of the feature data may need to be read and computed from external data sources. 

**Why is backfilling training data useful?**
--------------------------------------------

Backfilling training data is important because it enables the fast creation of training data from [reusable features](#) in the feature store. Backfilling training data also enables reproducibility in [model training](http://www.hopsworks.ai/dictionary/model-training). When a feature store supports consistently re-creating point-in-time consistent training data, the same training data can be deleted and recreated when needed, for example, to reproducibly train a model.

‍**Example of backfilling training data**
-----------------------------------------

***‍***A data scientist would like to train three models for three different regions (US, Europe, Asia), and needs to backfill training data for each of the models. In [Hopsworks](https://www.hopsworks.ai/the-python-centric-feature-store), they could create one [feature view](https://www.hopsworks.ai/dictionary/feature-view), including all the needed features, and call create training data 3 times, but each time with a different filter for the target region (US, Europe, Asia).

