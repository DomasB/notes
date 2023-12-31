---
tags: "#ml #data-vizualization #data-pipeline #streaming-features #feature-group #feature-pipeline #feature-validation #transformation"
---
## What is a feature pipeline in machine learning?

A feature pipeline is a program that [[Orchestration|orchestrates]] the execution of a dataflow graph of [[Feature function|feature functions]] ([[Transformation|transformations]]) on input data to create unencoded feature data), where the computed features are written to one or more [[Feature Groups|feature groups]]. A feature pipeline can also include reading the input data from data sources, [[Data validation (for features)|data validation]], and any other steps needed when computing features.

## Why do I need a feature pipeline?
Feature pipelines are needed to enable features to be computed on a schedule, or if they are [[Streaming Feature Pipeline|streaming feature pipelines]], run 24x7. The feature pipeline encapsulates the logic for computing features in feature groups, defines the data validation logic, and writes the features to feature groups. A batch feature pipeline needs to be run on a schedule by an orchestration engine, such as Airflow, Dagster, or, for simple cron-based scheduling, Modal.

## What are the data sources for feature pipelines?
Feature pipelines read their input data from data sources such as data warehouses, message buses, databases, object stores, and Http APIs. The data sources can provide input live data, during scheduled executions, or historical data when backfilling feature groups. Feature pipelines should scale to handle the largest expected input volume size.

## An example of the steps in feature pipeline might include:
1. **Data ingestion**: Raw data is read from various data sources for processing.
2. **Data/feature validation**: The raw data and/or feature data is validated to ensure that it is accurate, complete, and consistent.
3. **Feature extraction/transformation**: Relevant features are extracted from the raw data and transformed into a format that is optimized for machine learning models using techniques such as filtering, aggregation, dimensionality reduction (embeddings, PCA), binning, and feature crossing.
4. **[[Feature Store|Feature storage]]**: The features are stored in feature groups in the feature store for access training and inference pipelines.