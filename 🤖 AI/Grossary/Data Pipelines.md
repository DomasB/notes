What are data pipelines?
------------------------

Data pipelines are orchestrated programs that move data from one system to another while also performing [transformations](https://www.hopsworks.ai/dictionary/transformation) on the data either before it has been copied to the target system ([ELT](https://www.hopsworks.ai/dictionary/elt)) or after it has been copied ([ETL](https://www.hopsworks.ai/dictionary/etl)). Data pipelines are a key building block in data engineering, as they enable data to flow from operational databases, where the data is generated, to analytical data warehouses, [lakehouses](https://www.hopsworks.ai/dictionary/data-lakehouse), and data lakes where the data is analyzed and used for machine learning. The primary goal of a data pipeline is to automate and streamline the data flow, making it more efficient and reliable.

Without data pipelines (i.e., batch or streaming feature pipelines) machine learning systems can only work on static data and a model cannot be automated to generate value through automating predictions on new (inference) data. Compared to batch data pipelines, streaming data pipelines can produce fresher data (features), which is important for [real-time ML](https://www.hopsworks.ai/dictionary/real-time-machine-learning).

![](https://assets.website-files.com/618399cd49d125734c8dec95/6438005bdb85a4c3de771494_SS5okSODBwMPVDKfNh3JkoH6u8-3sdwEq8yzVksWExqexQUV9gWTkVbbgaITWOjUucD8Qlzv6AC2WSnlR4esUTEdEWAf7d0PjtCmGxZGvPTvqG936HSq_uPWOABhlu8asKRMDFEklAj0iy5Nnn91Pg.png)
LLM Tags:  #data-pipeline #ETL #ELT #transformation 
LLM Tags:  #ml, #streamingdatapipelines