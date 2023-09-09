---
tags: "#versioning #ml-artifacts #MLOps  #feature-store  #architecture"
---
## What is versioning of ML artifacts and why is it important for MLOps?
Versioning of models, [[Feature|features]], [[Feature Groups|feature groups]], [[Feature View|feature views]], and [[Train (Training) Set|training datasets]] enables the management of dependencies between ML artifacts. For example, in the figure below, we can see that when the *fraud* mode upgraded from version 1 to version 2, the [[precomputed features]] used by *fraud\_v2* have changed to *transactions\_v2*. This means when you deploy the new model, you need to connect it to the correct new versions of the feature in the online [[feature store]]. If there is a problem with *fraud\_v2* and you rollback to *fraud\_v1*, you need to connect *fraud\_v1* to *transactions\_v1*, so the [[Feature Pipeline|feature pipeline]] feeding *transactions\_v1* should not be turned off until you are sure you will never have to downgrade from *fraud\_v2*. Here, we can see that versioning enables smooth upgrading and downgrading of model versions and their dependent features.
![[Pasted image 20230903235427.png]]
