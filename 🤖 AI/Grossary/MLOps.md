**What is MLOps?**
------------------

Machine learning operations (MLOps) describes processes for automated testing of [ML pipelines](https://www.hopsworks.ai/dictionary/ml-pipeline) and [ML artifact](https://www.hopsworks.ai/dictionary/ml-artifacts) versioning that helps improve both developer productivity through faster iteration speed and the quality of ML systems.  MLOps processes include best practices for the development of features/models, deployment of models, testing of features/models, and the monitoring of features/models in production environments. 

The key principles underlying MLOps are the **automated testing and versioning of ML artifacts**, and integration into a [CI/CD](https://www.hopsworks.ai/dictionary/ci-cd-for-mlops) (continuous integration, continuous deployment) development process. The testing hierarchy and versioning of ML artifacts is shown in the two figures below.

![machine learning apps](https://assets.website-files.com/618399cd49d125734c8dec95/64369e0574b03f117f3f32e6_P7mDFfNH6t3sv6tC9XqMeMuKTDo-Aw4wZXVDCeOA1yO9cEibgw_hTsLlRYA3h0xnAA9nH1guccsVEvLoWd02GtbmNvJpTE9gvbQ7sDIRJz-co8oyIO7FeW0XJ3W64SurXN3RBvT0k_w5eNWGdImiig.png)In the above figure, we can see the hierarchy of testing involved in building ML systems. Features input data and logic can be tested, making it easier to depend on models trained on those features. Similarly, ML systems can build with more confidence on models that have been tested for performance, bias, and [data compatibility](http://www.hopsworks.ai/dictionary/data-compatibility).

![graph about models in ML production](https://assets.website-files.com/618399cd49d125734c8dec95/64369e0552823ed98c65313c_CloUn_JrsnlnL-C5EGQZLiUZBt_kUryVSee67i6JX8iMQ5-YzcvPdoJecaMQVuGAIkkDj5_VgCrt4nCpkihzcOppAd-WF5WlU3v4sVscDxD1pa5m9xu82PctPfHab5c9nuEutHS59p8Pcz5pblpU4g.png)ML artifacts should be versioned to enable smooth upgrading/downgrading of ML systems. In the above figure, we can see that the fraud\_v1 and fraud\_v2 models are dependent on different versions of the transaction features: v1 and v2, respectively. When you upgrade your deployed model that uses [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) from a feature store, you may need to make sure that it is connected to the new feature version. You should keep both the old model version and feature versions available and keep the old feature pipeline updating v1, so that you can seamlessly downgrade to v1 without any problems.

**How is MLOps different from DevOps?**
---------------------------------------

The development and operation of ML systems has both familiar software engineering challenges (that have been addressed by automated software testing and versioning as part of the DevOps paradigm) as well as novel challenges related to data validation, feature/model drift, ML artifact versioning, ML pipeline orchestration, and infrastructure management. There are familiar unit tests from DevOps that can be used on feature functions, as well as new types of tests such as [data validation](https://www.hopsworks.ai/dictionary/data-validation-for-features), model validation, and end-to-end feature/training/inference tests.

**How can you leverage MLOps in a project?**
--------------------------------------------

To leverage MLOps in a project, adopt a ML pipeline-first approach focusing on [[Feature Pipeline|feature pipelines]], [training pipelines](https://www.hopsworks.ai/dictionary/training-pipeline), and [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline), producing versioned features and models as outputs, stored in a [feature store](https://www.hopsworks.ai/dictionary/feature-store) and [model registry](https://www.hopsworks.ai/dictionary/model-registry), respectively. This approach decomposes building ML systems into more manageable ML pipelines that can be independently developed and tested, their outputs can be versioned, the ML pipelines can be easily composed into a working ML system.


LLM Tags:  #mlops #ml #testing #versioning
LLM Tags:  #ml #testing #mlsystems
LLM Tags:  #mlops #devops #versioning #dependencymanagement
LLM Tags:  #mlops #devopstesting #data-validation #modelvalidation #pipelinestruc
LLM Tags:  #ml-pipeline #hopsworksai #versioning #training-pipeline #inference-pipeline #feature-store #model-registry