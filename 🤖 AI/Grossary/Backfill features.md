---
tags: "#back-filling #featurere-use #historical-data #training-data #data-model"
---
## What does backfilling features mean?
Backfilling is the process of recomputing datasets from raw, historical data. For [[Feature Reuse|reusable features]] in a [[Feature Store|feature store]], backfilling involves running a [[Feature Pipeline|feature pipeline]] with **historical data** to populate the feature store. 

## Implementation Notes
The same feature pipeline used to backfill features should also process “live” data. You just point the feature pipeline at the data source and the range of data to backfill (e.g., backfill the daily partitions with all users for the last 180 days). Both batch and [[Streaming Feature Pipeline|streaming feature pipelines]] should be able to backfill features.

## Why is backfilling features useful?
Backfilling features is important because you may have existing historical data that can be leveraged to create [[Training Data|training data]] for a model. If you couldn’t backfill features, you could start logging features in your production system and wait until sufficient data has been collected before you start training your model.

## Example of backfilling features
The historical data for backfilling could be user clicks on a website, purchases on an ecommerce site, or any data that is systematically collected, curated, and typically stored in a [[Data Lakehouse|lakehouse]] or data warehouse. The data you are backfilling should include in its data model a timestamp for each event/row, so that you can specify a range of time to backfill data with.

## Steps for backfilling

1. **Raw Data Identification**: First, identify the raw data sources required to compute the "average spending per month" feature. These could include tables that store user purchase history, timestamps of purchases, and amounts spent.
2. **Feature Pipeline Creation**: Create a feature pipeline that reads from these raw data sources and performs the necessary calculations to output the new feature.
3. **Initial Pipeline Testing**: Test this pipeline on some sample current ("live") data to make sure it’s creating the feature correctly.
4. **Backfill Execution**: Point the pipeline to the historical data source and specify the time range you want to backfill, such as the past 12 months. Execute the pipeline, and it will populate the feature store with the "average spending per month" for existing users over the last year.
5. **Validation**: Once backfilling is complete, validate the newly calculated features for quality and correctness.
6. **Integration**: Integrate the same pipeline into the production workflow to continuously calculate the "average spending per month" feature for new data.
