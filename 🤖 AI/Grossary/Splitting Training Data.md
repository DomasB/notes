**What does splitting training data for ML mean?**
--------------------------------------------------

When you train a model, you would like your model to generalize and perform well on new, unseen data. You don’t want your model to overfit to [[Training Data|training data]]. A popular way to have an unbiased approach to measuring how well your model generalizes is to split your training data into [train](https://www.hopsworks.ai/dictionary/train-training-set), [validation](https://www.hopsworks.ai/mlops-dictionary#:~:text=V-,Validation%20Set,-The%20validation%20set), and [test](https://www.hopsworks.ai/mlops-dictionary#:~:text=T-,Test%20Set,-The%20test%20set) sets. They are sets because examples should be unique to each set, otherwise you may have [leakage](https://www.hopsworks.ai/dictionary/data-leakage).

**How should you split your training data?**
--------------------------------------------

The type of split you use should depend on the nature or distribution of the training data.

If you have a static dataset or a dataset drawn from a stationary distribution, a popular way to split your training data is to create **random splits**. Typical sizes for the different sets would be 70% for your train set, 15% for the validation set, and 15% for the test set. 

The splitting process should ensure that the distribution of data in each of the train/validation/test sets are representative of the overall dataset. If, however, some examples are at risk of being under-represented in one of your sets (for example, because you have only a few examples for a certain category in a categorical variable)  then you can use **stratified sampling**, In stratified sampling, the data is divided in such a way that the proportion of each class or category in the test set is the same as in the original dataset, ensuring a balanced representation of different classes or categories.

For **time-series data**, however, you typically create the train/validation sets from **non-overlapping time ranges of data**. The test set should be drawn from a time range after the train set (to evaluate if the model can generalize to work well in future unseen data). 

‍


LLM Tags:  #ml  #training-data #trainvaltestsplit #data-leakage
LLM Tags:  #ml #data-analysis #data-science 
LLM Tags:  #timeSeries, #trainValidationSet, #nonOverlappingTimeRanges, #testSet