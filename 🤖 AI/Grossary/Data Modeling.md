**What does Data Modeling for ML mean?**
----------------------------------------

Data modeling describes how the tables in a data warehouse are structured to create a simplified, intuitive, and easy-to-understand layout that enables efficient, ad-hoc querying and analysis of large datasets by business intelligence (BI) users.

**Star/Snowflake Schema**
-------------------------

[Dimensional modeling](https://www.hopsworks.ai/dictionary/dimensional-modeling-and-feature-stores)  involves designing star or snowflake schemas where there is one central fact table connected to one or more dimension tables through foreign key relationships. Dimension tables are denormalized to enable faster query performance.  The Snowflake Schema extends the star schema to normalize dimension tables into multiple related tables to reduce redundancy. This can lead to more complex query structures and slightly slower query performance compared to star schemas. 

**One Big Table**
-----------------

One big table (OBT) refers to a data model where all the relevant dimensions and facts are combined into one single, large, denormalized table, often with redundant data. You can design your data model as OBT where you need simplicity and ease of querying, rather than efficient storage or maintenance.

[According to Kimball](https://www.kimballgroup.com/wp-content/uploads/2013/08/2013.09-Kimball-Dimensional-Modeling-Techniques11.pdf), you should avoid fact-to-fact table Joins:


> “A BI application must never issue SQL that joins two fact tables together across the fact table’s foreign keys. It is impossible to control the cardinality of the answer set of such a join in a relational database, and incorrect results will be returned to the BI tool. For instance, if two fact tables contain customer’s product shipments and returns, these two fact tables must not be joined directly across the customer and product foreign keys. Instead, the technique of drilling across two fact tables should be used, where the answer sets from shipments and returns are separately created, and the results sort-merged on the common row header attribute values to produce the correct result.”

**Use Label-to-Fact Joins in a Feature Store**
----------------------------------------------

In the case of creating [training data](https://www.hopsworks.ai/dictionary/training-data) from features in a feature store, you need to first identify the table(s) containing labels (targets), the event-time for the label, and the corresponding entity or entities. Only then, can you perform a [point-in-time Join](https://www.hopsworks.ai/mlops-dictionary#:~:text=Point%2Din%2DTime%20Correct%20Joins) to pull in features from the feature groups containing facts/dimension using a join on the [entity](https://www.hopsworks.ai/mlops-dictionary#:~:text=improve%20model%20performance.-,Entity,-In%20a%20feature) ID(s) and the event timestamp.

