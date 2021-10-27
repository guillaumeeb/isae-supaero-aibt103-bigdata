---
title: Spark Introduction
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-15
---

# Spark Introduction

## Spark History

:::::::::::::: {.columns}
::: {.column width="50%"}

- Research project at the [UC Berkeley AMPLab](https://amplab.cs.berkeley.edu/), started in 2009
- Open sourced in early 2010:
  - 2013: Moved to Apache Software Foundation
  - 2014: 1.0 release, top level Apache project
  - 2016: 2.0 release
  - 2020: 3.0 release
- Now with 100s of developers

:::
::: {.column width="50%"}

From [Spark Research homepage](https://spark.apache.org/research.html):

> Our goal was to design a programming model that supports a **much wider class** of applications than MapReduce, while maintaining its automatic **fault tolerance**. 
> In particular, MapReduce is **inefficient for multi-pass applications** that require low-latency data sharing across multiple parallel operations. 

- Iterative algorithms (many machine learning algorithms)
- Interactive data mining
- Streaming applications that maintain aggregate state over time

:::
::::::::::::::

## Spark vs Map Reduce

![Difference between MapReduce and Spark (Knoldus)](https://i0.wp.com/blog.knoldus.com/wp-content/uploads/2018/10/Difference-between-MapReduce-and-Spark_A.jpg?w=700&ssl=1)

- MapReduce alternative wihch provides in memory processing (100x faster)
- A lot of other things, tools, higher level API

## Tools and ecosystem

:::::::::::::: {.columns}
::: {.column width="70%"}

![Spark stack (Databricks)](https://databricks.com/wp-content/uploads/2016/02/Spark-Stack-1024x474.png)

![Spark sources (Databrick)](https://databricks.com/wp-content/uploads/2015/02/Introducing-DataFrames-in-Spark-for-Large-Scale-Data-Science1.png)

:::
::: {.column width="30%"}

![](https://www.python.org/static/community_logos/python-logo-master-v3-TM.png)

![](https://www.r-project.org/logo/Rlogo.png)

![](https://www.scala-lang.org/files/archive/spec/2.11/public/images/scala-logo-red-spiral-dark.png)

![](https://www.oracle.com/a/ocom/img/cb71-java-logo.png)

:::
::::::::::::::

## APIs

![](https://databricks.com/wp-content/uploads/2018/05/rdd.png)

## APIs (detailed)

:::::::::::::: {.columns}
::: {.column width="50%"}

### Resilient Distributed Dataset (RDD)

- Was primary user-facing API in Spark
- An RDD is an 
  - **immutable** 
  - **distributed** 
  - **collection** of elements of your data
- partitioned across nodes in your cluster
- operated in parallel with a low-level API
- Offers **transformations** and **actions**
- Unstructured datasets
- Functional programming constructs
- In memory, **fault tolerant**
- No schema, less optimization

:::
::: {.column width="50%"}

### Dataframes and Datasets

- Also an immutable distributed collection of data
- Built on top of RDDs
- Structured data, organized in named columns
- Impose a structure, gives higher-level abstraction
- SQL like operations
- Dataset: strongly typed objects
- Catalyst optimizer, better performances

![](https://databricks.com/wp-content/uploads/2016/06/Unified-Apache-Spark-2.0-API-1.png)

:::
::::::::::::::

## Transformations and Actions

:::::::::::::: {.columns}
::: {.column width="50%"}

### [Transformations](https://databricks.com/glossary/what-are-transformations)

- Create a new (immutable) dataset from an existing one
- Instruct Spark how you would like to modify the Data
- Narrow Dependencies: 1 to 1 input to output
- Wide Dependencies (shuffles, so MapReduce): 1 to N
- transformations in Spark are **lazy**
  - No computations
  - Just remember the transformations to base dataset

| Transformations |
|---------|
| map* |
| filter |
| groupByKey |

:::
::: {.column width="50%"}


### [Actions](https://databricks.com/glossary/what-are-transformations)

- Return a value to the driver program 
- After running a computation on the dataset

| Actions |
|---------|
| reduce |
| collect |
| count |
| first |
| take |
| saveAs... |

:::
::::::::::::::

## Some code

```python
lines = sc.textFile("data.txt")
lineLengths = lines.map(lambda s: len(s))
totalLength = lineLengths.reduce(lambda a, b: a + b)
```

## Execution Plan and DAGS

:::::::::::::: {.columns}
::: {.column width="70%"}

```python
rdd1.map(splitlines).filter("ERROR")
rdd2.map(splitlines).groupBy(key)
rdd2.join(rdd1, key).take(10)
```

![](https://databricks.com/wp-content/uploads/2014/03/spark-devs1.png)

:::
::: {.column width="30%"}

- Job: each action triggers a job
- Stages:
  - Group of Narrow transformation
  - Can be processed in one go
  - **Shuffling** (Wide transformations) split stages
- Task: unitary transformation on a data chunk

:::
::::::::::::::

## Streaming

![](https://spark.apache.org/docs/latest/img/streaming-arch.png)

![](https://spark.apache.org/docs/latest/img/streaming-flow.png)

## MLLib

- Uses Dataframe API as inputs
- Pipeline made of
  - Transformers (analogy to transformation)
  - Estimator (can be actions)

![](https://spark.apache.org/docs/latest/img/ml-Pipeline.png)

![](https://spark.apache.org/docs/latest/img/ml-PipelineModel.png)

## Spark Application and execution

![](https://spark.apache.org/docs/latest/img/cluster-overview.png)
![](https://databricks.com/wp-content/uploads/2018/05/Spark-Applications.png)

## Dashboard

![Spark DAG](https://spark.apache.org/docs/3.0.0-preview/img/JobPageDetail2.png)

![Spark stages details](https://spark.apache.org/docs/3.0.0-preview/img/AllStagesPageDetail3.png)

## Dashboard 2

![Spark tasks](https://spark.apache.org/docs/3.0.0-preview/img/AllStagesPageDetail6.png)

# Play with Map Reduce through Spark 

## Context

- Interactive notebook (developed some years ago...)
- Pre-configured
- Warm up on [Py computation](https://www.geeksforgeeks.org/estimating-value-pi-using-monte-carlo/)

![](https://camo.githubusercontent.com/e95b477d89032e6f4a7c7bc8fadaf4c8d185c900/687474703a2f2f7777772e706879736963732e736d752e6564752f66617474617275732f70692e706e67)

- RDDs
- Dataframes

## Notebook

[Notebook is here](https://github.com/guillaumeeb/isae-supaero-aibt103-bigdata/blob/main/notebooks/IntroductionToSpark.ipynb)

Easiest:

[Run it on Binder](https://mybinder.org/v2/gh/guillaumeeb/isae-supaero-aibt103-bigdata/main?urlpath=lab)
