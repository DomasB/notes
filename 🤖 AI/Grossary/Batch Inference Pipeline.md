**What is a batch inference pipeline?**
---------------------------------------

**‍**A batch inference pipeline is a program that takes as input a batch of data and a model, and outputs predictions that are typically written to some sink, such as a database.

‍

![Graph](https://assets.website-files.com/618399cd49d125734c8dec95/64356540cf26455bb19672e4_XIH-lGYLhrOven3lpAGaPmF1V0Vj4FbYuA1FFAmgCuvI_KB0x28Vc6OOLgsshfwgOxu0Rqm67gUFPc0RnKo3xOKZ0GhuUdqz1viGrC0OGxyTcELU7bcwCJURlQdzqqXOu39a-Vbyer5goPf0BKbxvg.png)**Why are batch inference pipelines important?**
------------------------------------------------

**‍**Batch inference pipelines are important because they allow for efficient and scalable inference on large volumes of data using a trained model. Batch inference pipelines are typically run on a schedule (e.g., daily or hourly) and are used to drive dashboards and operational ML systems (that use the predictions for intelligent services).

‍**Example of a batch inference application**
---------------------------------------------

**‍**A Spark program reads all of the new inference data that has arrived in the previous 24 hours as a DataFrame. The Spark program downloads the model from the [model registry](https://www.hopsworks.ai/dictionary/model-registry), broadcasts it to all executors, and then a map function calls predict on the model for each row in the DataFrame, returning the predictions as a DataFrame. The predictions DataFrame is then stored in a database from where it is consumed by a Dashboard or operational [ML](https://www.hopsworks.ai/dictionary/ml) system.

