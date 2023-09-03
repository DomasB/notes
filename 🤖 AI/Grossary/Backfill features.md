**What does backfilling features mean?**
----------------------------------------

Backfilling is the process of recomputing datasets from raw, historical data. For [reusable features](https://www.hopsworks.ai/dictionary/feature-reuse) in a [feature store](https://www.hopsworks.ai/dictionary/feature-store), backfilling involves running a [[Feature Pipeline|feature pipeline]] with **historical data** to populate the feature store. 

**Implementation Notes**
------------------------

The same feature pipeline used to backfill features should also process “live” data. You just point the feature pipeline at the data source and the range of data to backfill (e.g., backfill the daily partitions with all users for the last 180 days). Both batch and streaming feature pipelines should be able to backfill features.

**Why is backfilling features useful?**
---------------------------------------

Backfilling features is important because you may have existing historical data that can be leveraged to create [[Training Data|training data]] for a model. If you couldn’t backfill features, you could start logging features in your production system and wait until sufficient data has been collected before you start training your model.

‍**Example of backfilling features**
------------------------------------

The historical data for backfilling could be user clicks on a website, purchases on an ecommerce site, or any data that is systematically collected, curated, and typically stored in a [lakehouse](https://www.hopsworks.ai/dictionary/data-lakehouse) or data warehouse. The data you are backfilling should include in its data model a timestamp for each event/row, so that you can specify a range of time to backfill data with.


LLM Tags:  #back-filling, #featurere-use, #historicaldata, #liveData
LLM Tags:  #back-filling #trainingdata #historicaldata #data-model