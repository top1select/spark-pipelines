# Model Deployment With Spark and MLeap

## Writing Spark ML Pipelines to Train Models

The Spark ML Pipelines API leverages the now standard scikit-learn components to create model uniformity and comparability. In this section, we cover the basics of DataFrame, Transformer, Estimator, Pipeline and Parameter and frame our price prediction challenge.

### DataFrame

A Spark DataFrame is a distributed collection of data that is organized into named columns. You can think of it as table in a relational database or a DataFrame in python pandas. In Spark, the DataFrame API allows you to access distributed data from Hive, HDFS, external tables, streams, as well as many other sources of data. When working with data in Spark, you will most often be working with a DataFrame.

![alt text](./static/slide1_dataframe.jpg "DataFrae")

### Transformer

A transformer is a function that can clean, reduce, expand or generate feature representations. In Spark, a transformer converts a DataFrame into another by appending one or more computed columns.

The four most common transformer types are:
* Classification: Binary/Multi-label classification models
* Clustering: Non-parametric classification models
* Feature: Compute/Transform dependent variables
* Regression: Linear and Tree-based regression models

![alt text](./static/slide2_pipelines.jpg "Pipelines")

### Estimator

An Estimator is a concept of learning from the data before transforming it. For example, to perform a Standard Scaler transformation, we first must learn from the data what the mean and standard deviation values are. Spark Estimators are implemented within the `.fit()` method. 

![alt text](./static/slide3_estimator.jpg "Estimator")

### Pipeline

A Pipeline is a sequential assembly of transformers and often a final Estimator (i.e. Linear Regression). The main purposes of a pipeline are:
* Well-organized workflow
* Cross-validation and parameter tuning of different inputs
* Deploying the sequence of transformers to production (as we'll cover later)

![alt text](./static/slide4_pipeline.jpg "Pipeline")

### Parameters

The Parameters API allows the user to specify settings for a given transformer. The more notable feature of Spark is the `ParamGridBuilder` which allows you to specify an array of parameters to test your pipeline and the final estimator (i.e. Linear Regression) with.

![alt text](./static/slide5_parameters.jpg "Parameters")
