---
title: Spark Introduction
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-15
---

# Spark Introduction

## Spark History

- Research project at the [UC Berkeley AMPLab](https://amplab.cs.berkeley.edu/), started in 2009
- Open sourced in early 2010:
  - 2013: Moved to Apache Software Foundation
  - 2014: 1.0 release, top level Apache project
  - 2016: 2.0 release
  - 2020: 3.0 release
- Now with 100s of developers

## Spark goal and key featyres

From [Spark Research homepage](https://spark.apache.org/research.html):

> Our goal was to design a programming model that supports a **much wider class** of applications than MapReduce, while maintaining its automatic **fault tolerance**. 
> In particular, MapReduce is **inefficient for multi-pass applications** (...). 

- Iterative algorithms (many machine learning algorithms)
- Interactive data mining
- Streaming applications that maintain aggregate state over time

## Spark vs Map Reduce

![Difference between MapReduce and Spark (Knoldus)](https://i0.wp.com/blog.knoldus.com/wp-content/uploads/2018/10/Difference-between-MapReduce-and-Spark_A.jpg?w=700&ssl=1)

- MapReduce alternative which provides in memory processing (100x faster)
- A lot of other things, tools, higher level API

## Tools and ecosystem

:::::::::::::: {.columns}
::: {.column width="70%"}

![Spark stack (Databricks)](https://databricks.com/wp-content/uploads/2016/02/Spark-Stack-1024x474.png){width=60%}

![Spark sources (Databrick)](https://databricks.com/wp-content/uploads/2015/02/Introducing-DataFrames-in-Spark-for-Large-Scale-Data-Science1.png){width=60%}

:::
::: {.column width="30%"}

![](https://www.python.org/static/community_logos/python-logo-master-v3-TM.png){width=40%}

![](https://www.r-project.org/logo/Rlogo.png){width=30%}

![](https://www.scala-lang.org/files/archive/spec/2.11/public/images/scala-logo-red-spiral-dark.png){width=40%}

![](https://www.oracle.com/a/ocom/img/cb71-java-logo.png){width=40%}

:::
::::::::::::::

## Quizz

What's the main difference between Spark and Hadoop Map Reduce?

- Answer A: Spark uses another algorithm at the heart of its computing model
- Answer B: Spark can work on memory and is much faster
- Answer C: Spark has a better name
- Answer D: Spark provides many more APIs

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_205) _Key: mw_

## APIs

![](https://databricks.com/wp-content/uploads/2018/05/rdd.png)

## Resilient Distributed Dataset (RDD)

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

## Dataframes and Datasets

:::::::::::::: {.columns}
::: {.column width="50%"}

- Also an immutable distributed collection of data
- Built on top of RDDs
- Structured data, organized in named columns
- Impose a structure, gives higher-level abstraction
- SQL like operations
- Dataset: strongly typed objects
- Catalyst optimizer, better performances

:::
::: {.column width="50%"}

![](https://databricks.com/wp-content/uploads/2016/06/Unified-Apache-Spark-2.0-API-1.png)

:::
::::::::::::::

## Transformations and Actions

:::::::::::::: {.columns}
::: {.column width="60%"}

### [Transformations](https://databricks.com/glossary/what-are-transformations)

- Create a new (immutable) dataset from an existing one
- Instruct Spark how you would like to modify the Data
- Narrow Dependencies: 1 to 1 input to output
- Wide Dependencies (shuffles, so MapReduce): 1 to N
- transformations in Spark are **lazy**
  - No computations
  - Just remember the transformations from input dataset

:::
::: {.column width="40%"}


### Actions

- Return a value to the driver program 
- After running a computation on the dataset

:::
::::::::::::::

## Transformations and Actions examples

:::::::::::::: {.columns}
::: {.column width="50%"}

### [Transformations](https://databricks.com/glossary/what-are-transformations)

| Transformations |
|---------|
| map* |
| filter |
| groupByKey |

:::
::: {.column width="50%"}

### Actions

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
::: {.column width="60%"}

```python
rdd1.map(splitlines).filter("ERROR")
rdd2.map(splitlines).groupBy(key)
rdd2.join(rdd1, key).take(10)
```

![](https://databricks.com/wp-content/uploads/2014/03/spark-devs1.png)

:::
::: {.column width="40%"}

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

![](https://spark.apache.org/docs/latest/img/ml-Pipeline.png){width=50%}

![](https://spark.apache.org/docs/latest/img/ml-PipelineModel.png){width=50%}

## Spark Application and execution

![](https://spark.apache.org/docs/latest/img/cluster-overview.png)
![](https://databricks.com/wp-content/uploads/2018/05/Spark-Applications.png)

## Dashboard

![Spark DAG](https://spark.apache.org/docs/3.0.0-preview/img/JobPageDetail2.png){width=20%}
![Spark stages details](https://spark.apache.org/docs/3.0.0-preview/img/AllStagesPageDetail3.png){width=70%}

## Dashboard 2

![Spark tasks](https://spark.apache.org/docs/3.0.0-preview/img/AllStagesPageDetail6.png){width=60%}

## Quizz

What's the main API of Spark?

- Answer A: MLLib
- Answer B: RDDs (Resilitent Distributed Datasets)
- Answer C: Datasets
- Answer D: Transformations

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_859) _Key: ho_

# Play with Map Reduce through Spark 

## Context

- Interactive notebook (developed some years ago...)
- Pre-configured
- Warm up on [Py computation](https://www.geeksforgeeks.org/estimating-value-pi-using-monte-carlo/)

![](https://camo.githubusercontent.com/e95b477d89032e6f4a7c7bc8fadaf4c8d185c900/687474703a2f2f7777772e706879736963732e736d752e6564752f66617474617275732f70692e706e67){width=20%}

- RDDs
- Dataframes

## Notebook

[Notebook is here](https://github.com/guillaumeeb/isae-supaero-aibt103-bigdata/blob/main/notebooks/IntroductionToSpark.ipynb)

Easiest:

[Run it on Binder](https://mybinder.org/v2/gh/guillaumeeb/isae-supaero-aibt103-bigdata/main?urlpath=lab)
