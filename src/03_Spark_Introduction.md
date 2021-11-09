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

- MapReduce alternative wihch provides in memory processing (100x faster)
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

![Answer](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAASwAAAEsCAIAAAD2HxkiAAAGgElEQVR42u3d0ZLyKBAGULPl+7+yezFVbtaJGRS7G+Scm93f0QmJ+QYEge12u12AOv+4BCCEsLTrz3+2bbs/VNtA/SlJdBn257s/62ePJ5/y72KM8NYQGML9TbBt27ZtoW92TszO7SP3uyT3R9Kuxp9hexZLvqE5+nAjPqsQMuMxzt/76KshWvzXHH2pmbSvKA7/eLc09g5rofsTzquChwLcbreTF47clm4M+QhtBwJrwv4b7uFO2j/+8NN9LXdY4z27z54d6/7TZz/KT+DHyyCBQth0Z5wHoLOF+eexBmlLPxRDAnm5OfrG+/2sU+GnP6Olivsynz1NCVwuhIfhee+e+/1JL7qP8ftI4ELN0cPO+p//Ofywd9LR8vPPl5Lc8uRnnzkHTMKrf8UkkMvlsh1+xNpXXPuOx5Pe0ZPHL897Qdtfdd47+urtGzFY/8YXHs6LIYRrhRBtSIQQVv1M6BKAEIIQAkIIQggIIQghIIQghIAQghACQghCCAghCCEghCCEgBCCEAJxrjmHGXDnk8PFddrL2bk2T+NmTEEXecCFhWa5Q9SEoDkKCCEIISCEIITAp1wLj53WBVw78NB+oIhu+hH2D3+7SAPeIWpC0BwFhBCEEBBCEELgU66jFaizszhtckPnM9sL33mgiHK2Fz5ijKH2DlETguYoIIQghIAQghACn3J1CfYGXL4p7UC1IzFqQkAIQQgBIQQhBIQQVmOI4n/ae+Rn6WdPW8IobekqNSEghCCEgBCCEAJCCN9huCGK2q7/zpkE7SI2aYhYpaqz8BHv5vdNwlATghCCEAJCCEIICCGsqXKIYsCv2KftRTH1MyOu5yx3iJoQhBAQQhBCQAhBCIFPSRqimPqb7wN2lEeMMQw4L0RNCAghCCEghCCEgBDCF9u+rGs4YtPm2o2gO49eOzdi5RkkakLQHAWEEIQQEEIQQuBc0iyK2l7+zl7ptI2gI0Yjao8esbtGZ+HT7jo1IWiOAkIIQggIIQghcC5pFkVED/LU+zFEnGb70WtnUXSeewRDFKA5CgghCCEghCCEQL7KvSgG7IC2O/TbZzTLglRqQkAIQQgBIQQhBIQQBnEdrUAR0yDSynmoc0WpdrMMkNQuSBVx6dSEoDkKCCEIISCEIITAGyqHKGoXZUrrlY4oUm2Xetq5RwxNDTi1Qk0IQghCCAghCCEghLCmObbLrp1FMct6Qd+3J3nn0dNeriYEzVFACEEIASEEIQTesI321fuIjbU7DzTgRtCLzMyIGBwa8NzVhKA5CkIICCEIISCEsKYlhihql4SqnQIy4N7UsxxITQiao4AQghACQghCCIS6rnCSaasA1e5vkbadQ/sZ1U5qmWUGiZoQNEdBCAEhBCEEhBDWNMdeFFMfqFPE+EraxI7OvShm2QVETQhCCAghCCEghCCEwBu2KRbDqf2Se8RCT51q14nqvHSLnLuaEDRHASEEIQSEEIQQODfHLIrajvIB942o1Tk3Iu3oETeDmhA0RwEhBCEEhBCEEPiUpFkUU3/JPWKEY+pyzjI8Y7tsQAhBCAEhBCEEhBBGVjlEUbtNQsS2yWk7YURc+YiXp/3OWY6uJgTNUUAIQQgBIQQhBO6uK5zkLDtjd2ovZ9pKTRGX7vumVqgJQQhBCAEhBCEEhBDWVDlEETFhYuqXt1+ldmkTJmpPs/Pc1YSgOQoIIQghIIQghEC+pCGKzs7itJenrQIUsSTU4e8ccF2j2pkZAy7GpSYEzVEQQkAIQQgBIYQ1JQ1RDLhWUvu6Rmmd2hGTMNrfjojNOSKKlHbl1YSgOQoIIQghIIQghECoyoWeandI7nxm2pJQaXtT1863SJtaYS8KQAhBCAEhBCEEhBAGMdx22bWbIUfMY4iYCpA2FtK5sXb72lOd0i6dmhA0RwEhBCEEhBCEEPiUq0vwp7Re/ogiRYyv1A6QtEs7kJoQNEcBIQQhBIQQhBB4gyGKv0X0dEf8zoiNtTsP1PnytAESNSFojgJCCEIICCEIIZBvuCGKAbcKSDvNznGLtAWUOueFpG0APssNpiYEIQQhBIQQhBAQQljTltNjO+BX19O61Gv3pp5lzkHn25H2cjUhaI4CQghCCAghCCHwKdsisxZATQgIIQghIIQghIAQghACQghCCAghCCEghCCEIISAEIIQAkIIQggIIQghIIQghIAQghACQghCCAghCCEghCCEgBCCEAJCCEIIhPgXIawrZ8ew6ikAAAAASUVORK5CYII=)

[Answer link](https://toreply.univ-lille.fr/reponse_17)

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
  - Just remember the transformations to base dataset

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

[Answer link](https://toreply.univ-lille.fr/reponse_592)

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
