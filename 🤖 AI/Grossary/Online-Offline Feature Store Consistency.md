**What is online-offline consistency in a feature store?**
----------------------------------------------------------

**‍**[[Feature|Features]] that are stored in both the [online](https://www.hopsworks.ai/dictionary/online-store) and [offline stores](https://www.hopsworks.ai/dictionary/offline-store) should be consistent. A replication protocol with consistency guarantees (strong consistency, eventual consistency,...) that the feature data that should be stored in both online and offline stores is kept in sync.

**What is an example of an online-offline feature store consistency protocol?**
-------------------------------------------------------------------------------

[Hopsworks](https://www.hopsworks.ai/the-python-centric-feature-store) is an open-source feature store, where feature pipelines write features to a topic in Kafka. The topic in Kafka has an Avro schema and both the online and offline stores have the same [schema](https://www.hopsworks.ai/dictionary/schema). 

![architecture graph](https://assets.website-files.com/618399cd49d125734c8dec95/6436a794a43c9f21737da41c_qZ1g19_erZEoBTRfSfuOkB2gPEYeISOLmwLaZaNhVhY0wpKM5TgGIG6uDEo5WKwM_Ih97ihfoNXTG_tmCKoFORUVpLLVtJCgMoR9FFVlnYLEAc17ub0keIYxZOlo_yAMegjXmjT4zzQlij8xaW5VwQ.png)Internal services in Hopsworks copy the data in the Kafka topic to the tables in the online and offline stores, ensuring eventually consistent feature data in the online and offline stores. Correctness is ensured by Kafka providing at-least-once guarantees when the data is written to the Kafka topic. After the data has been acknowledged as written to Kafka, duplicates may have been introduced to the feature data. The [connector that writes to the online store](https://github.com/logicalclocks/clusterj-onlinefs) will overwrite duplicate values, ensuring[[Idempotent ML Pipelines|idempotent]]  updates, and updates will not arrive out-of-order as both Kafka and the connector provide ordering guarantees for events. The connector that writes to the offline store ([Apache Hudi Delta Streamer](https://hudi.apache.org/docs/hoodie_deltastreamer/)) ensures writes to the offline store are atomic and any duplicates are removed.

#kafka 
LLM Tags:  #onlineofflinestoresconsistency #feature-store #syncprotocol
LLM Tags:  #data-pipeline
LLM Tags:  #architecture, #ml, #web