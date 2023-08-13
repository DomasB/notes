**What is training data?**
--------------------------

**‍**Training data refers to the data set that is used to train and evaluate a ML model. Training data consists of a large number of input examples, which include the features as well as the corresponding output or target values. 

**When is training data created by a feature store?**
-----------------------------------------------------

A [feature store](https://www.hopsworks.ai/dictionary/feature-store) enables the reproducible creation of training data from [feature groups](https://www.hopsworks.ai/dictionary/feature-groups). Training data is an immutable snapshot of feature data from the feature store and it is typically read by clients as either a DataFrame or as files (a materialized snapshot from the feature groups).

**How does training data relate to the train/validation/test splits?**
----------------------------------------------------------------------

Training data in machine learning refers to the unsplit training data that is created by the feature store, see the image below. The training data is typically split into partitions: [train](https://www.hopsworks.ai/dictionary/train-training-set), [validation](https://www.hopsworks.ai/dictionary/validation-set), and [test sets](https://www.hopsworks.ai/dictionary/test-set). The train set is used to train the model. The validation set is used to evaluate [model performance](http://www.hopsworks.ai/dictionary/model-performance) for different [hyperparameters](https://www.hopsworks.ai/dictionary/hyperparameter). The test set is used as a holdout set to evaluate model performance on unseen data.

![Metrics graph](https://assets.website-files.com/618399cd49d125734c8dec95/6436ae82d29c9dffd2959c52_WrD3BIkC86qiiakVqwHnZaK_kHZwFk-kv0PnSMbb1wjF8n8U5pXgJJl6F4zZBw0bi_HSrBGutin5rN9_pzgChzKkYXVEYuTVWRP8Tx2AU_5IrB45Ma4SGv0kyJWgKxV4RoeEG4I9DKn-QrdlXdv-Vg.png)