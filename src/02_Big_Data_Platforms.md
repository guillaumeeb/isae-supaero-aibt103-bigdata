---
title: Big Data Platforms, Hadoop and beyond
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-15
---

# Hadoop

## Introduction

What is Hadoop?

Open source framework supported by Apache foundation:

- Store and process massive amount of data
- In a distributed way
- On "commodity" hardware (i.e. not expensive)

## A complex ecosystem

:::::::::::::: {.columns}
::: {.column width="50%"}

![Hadoop ecosystem](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2016/10/HADOOP-ECOSYSTEM-Edureka.png){width=80%}

:::
::: {.column width="50%"}

Numerous Apache Software Foundation projects:

- Each covering a specific functionnality
- With their own developer community
- And their own development cycle

Hadoop distributions!
- Cloudera/Horthonworks (2018 fusion)
- MapR
- Others smaller

:::
::::::::::::::

## HDFS and MapReduce principles

### Two main components of Hadoop

- Distributed Software Defined Storage: HDFS (Hadoop Distributed File System)
![](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-hdfs/images/hdfs-logo.jpg){height=50px}
- Distributed Data Processing: MapReduce
![](https://www.pikpng.com/pngl/m/533-5331939_hadoop-apache-org-hadoop-map-reduce-logo-png.png){height=50px}

### Principles

- Split and store data on a cluster of servers (with local storage)
- Process data localy (on the server which owns it)
- Horizontal scalability: add or remove machines, on the fly, for compute or storage

## Hadoop cluster components{background-image=https://pbs.twimg.com/media/EKzU0wMWsAAkKLc.jpg data-background-opacity=0.4}

- CLuster of "commodity" servers
- **Shared Nothing** architecture: only shared component is _standard_ network
- Each machine is a node which own both storage and compute

Each cluster is composed of:

- Master nodes: handle metadata and knowledge of the whole infrastructure
- Worker nodes: 
  - Host distributed pieces of data
  - Execute data processing algorithm parts

## Hadoop story, from google to Spark

![Hadoop history (Packt)](https://static.packt-cdn.com/products/9781788999830/graphics/assets/4cf97ee3-8f90-4904-9094-dffd90bd066c.png){height=40%}

## Quizz

What are the **two** building blocks of Hadoop ecosystem (multiple choices)?

- Answer A: Oozie
- Answer B: HDFS
- Answer C: Map Reduce
- Answer D: Servers

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_638)

# HDFS 

## HDFS Basics

:::::::::::::: {.columns}
::: {.column width="50%"}

### Distributed File System

- Written in **Java**
- Allowing to **store** massive amounts of data, 
  - structured or not, 
  - on a machines cluster
- Extensible and portable
- One of the first **Software Defined Storage** 
  - (OK, Google was here first)
- In HDFS, data are of **writen-once** type (no inline modifications)

:::
::: {.column width="50%"}

### Data blocks

- Data is **splitted** and **distributed**
  -  among the Hadoop cluster
- Splitted into 128MB (default) **blocks**
- With a **replication** factor for preventing data loss 
  - (3 replicas default)
- Hadoop 3: **Erasure coding**
  - similar durability as replication 3, 
  - but **only 50%** volume increase
  - instead of 200%

:::
::::::::::::::

## HDFS blocks repartition

![](images/HDFSBlocks.png)

## HDFS Daemons

:::::::::::::: {.columns}
::: {.column width="60%"}

### Namenode

- Accountable for data locality and file system global namespace
- Daemon on a dedicated server
- Hosts metadata, create, remove, move files and folders
- Knows nodes wich own the parts of a file
- Needs to be replicated and secured (loss of metadata = loss of all data)

:::
::: {.column width="40%"}

### Datanode

- Stores and loads data blocks
- Daemon on every worker nodes
- Reading and writing of data
- Creation and Deletion of blocks

:::
::::::::::::::

## HDFS Architecture

![](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-hdfs/images/hdfsarchitecture.png)

## Quizz

What means HDFS?

- Answer A: Hadoop Distributed Functional Services
- Answer B: Hadoop Delayed File System
- Answer C: Hadoop Distributed File System
- Answer D: Hadoop Delayed Functional Services

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_5)

# Map Reduce

## Map Reduce Basics

- **Functional** language concept
- Heavily used by Google for **WWW indexing**
- **Colocate** data and processing (with Hadoop and others)
- Automatic process **ditribution** on pieces of data (eager distribution)
- Optimized for fast processing of **huge datasets**
- **Fault tolerant**: 
  - Data is replicated, 
  - Individual task can be restarted anywhere

## Wordcount (1. storage)

![](images/Wordcount1.png){style="background:white"}

## Wordcount (2. split)

![](images/Wordcount2.png){style="background:white"}

## Wordcount (3. map)

![](images/Wordcount3.png){style="background:white"}

## Wordcount (4. shuffle)

![](images/Wordcount4.png){style="background:white"}

## Wordcount (5. reduce)

![](images/Wordcount5.png){style="background:white"}

## Wordcount (6. result)

![](images/Wordcount6.png){style="background:white"}

## YaRN

- Yet Another Resource Negociator...
- Introduced in Hadoop v2
- Separation between
  - Resources scheduling and cluster state
  - Job execution and distribution

![](images/YARN.png){width=40%}
![](https://hadoop.apache.org/docs/stable/hadoop-yarn/hadoop-yarn-site/yarn_architecture.gif){width=40%}

## Quizz

What is the magical hidden step of distributed Map Reduce?

- Answer A: Map
- Answer B: Reduce
- Answer C: Shuffle
- Answer D: Split

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_167)

# Datalakes

## Toward a new data management model

:::::::::::::: {.columns}
::: {.column width="50%"}

### Process centric

- Structured Data
- Internal sources
- Important data only
- Multiple copies

![](images/ProcessCentric.png){height=30%}

:::
::: {.column width="50%"}

### Data centric

- Multiple types (structured, semi-structured, unstructured)
- Multiple sources (internal, external)
- Everything
- One copy

![](images/DataCentric.png){height=30%}

:::
::::::::::::::

## Host and process different kind of data

![](images/Datalake1.png){width=60%}

## Typical Architecture

![Oreilly's Datalake](https://www.oreilly.com/library/view/architecting-data-lakes/9781492042518/assets/ardl_0201.png){width=80%}

## CNES Datalake infrastructure example

![](images/CNESDatalake.png){width=50%}

## Quizz

What is the goal of a Datalake?

- Answer A: Host structured and filtered Data
- Answer B: Host any kind of Data, at any stages of processing
- Answer C: Standardizing Data structure

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_820)

# From HPC to Big Data to Cloud and High Performance Data Analytics

## HPC platform, story and use case

:::::::::::::: {.columns}
::: {.column width="50%"}

> HPC = High Performance Computing

- Firsts HPC platforms built in the 1960s
- Mainly compute bounds algorithms
- At first for Weather forcasting and Aerodynamic research
- Structure modeling and fluid mecanics by discretization
- Needs (needed?) high performance hardware (network, CPUs, storage)
- Compute and storage are separated
- Uses a resource scheduler

:::
::: {.column width="50%"}

![Jean-Zay supercomputer](http://www.idris.fr/media/images/jean-zay-annonce-01.jpg?id=web%3Aeng%3Ajean-zay%3Acpu%3Ajean-zay-cpu-hw-eng)

:::
::::::::::::::

## TOP500

| Rank | System | Cores | Rmax (TFlop/s) | Rpeak (TFlop/s) | Power (kW) |
|------| -------|-------|----------------|-----------------|------------|
| 1 | Supercomputer Fugaku - Japan  | 7,630,848 | 442,010.0 | 537,212.0 | 29,899 |
| 2 | Summit - United States | 2,414,592 | 148,600.0 | 200,794.9 | 10,096 |
| 3 | Sierra - United States | 1,572,480 | 94,640.0 | 125,712.0 | 7,438 |
| 8 | JUWELS Booster Module - Germany | 449,280 | 44,120.0 | 70,980.0 | 1,764 |
| 21 | PANGEA III - France | 291,024 | 17,860.0 | 25,025.8 | 1,367 |
| 92 | Jean Zay - France | 93,960 | 4,478.0 | 7,345.6 |

[Top 500 (june 2021)](https://top500.org/lists/top500/list/2021/06/)

## Big Data and Hadoop

- First platforms in the 2000's
- Mainly data bound algorithms
- Limitation in standard ethernet network performances = data locality
- At first for web indexing, or large amount of textual or tabular data analysis
- Web giant problem, then banking or IT stuf
- Use commodity hardware
- Compute and storage colocated

## HPDA convergence

![](images/HPDA.png){width=50%}

- Hadoop world step to HPC: YaRN, equivalent to HPC resources scheduler
- HPC step to Big Data: hardware not so specialized
- Hadoop big limitation: non standard File System and compute and storage colocation
- HPC big limitation: storage can be difficult to scale

## Cloud computing basics

Hence the cloud computing model...

- Compute resources separated from storage (but proximity is key)
- Can host anything, at first not compute oriented
- Object store model: Software Defined Storage as HDFS, specific interface (S3)
- Horizontal scalability of compute AND storage
- Resources on demand, mutualized between millions of users
- Infinite resources like for user

## Distributed programming: Hadoop vs HPC vs Cloud

:::::::::::::: {.columns}
::: {.column width="33%"}

### Hadoop

- Data bound algorithms
- Statistics
- Big volumes in input
- Often small outputs
- Can be used for computing problems, but not physical simulation

:::
::: {.column width="33%"}

### HPC (MPI)

- Compute bound algorithms
- Small or medium amount of inputs, 
- Medium or big outputs (big simulations)
- Can be used for data processing too (Dask)

:::
::: {.column width="33%"}

### Cloud

- Anything: services, storage bound, compute bound
- Object store limitations for some HPC workflow
- Or not anymore: HPC as a Service
- Big Data as a Service too...

:::
::::::::::::::

## Machine Learning Computations

### Machine learning

- Either lots of data in inputs
- Or lots of models to train (hyperparameter search)
- And of course data preprocessing
- Big Data or HPC or Cloud

### GPGPU

- Specific hardware (expensive)
- Really efficient for Deep Learning algorithms
- Image processing, Language processing

## Quizz

How Big Data processing differs from classical HPC (multiple choices)?

- Answer A: It is compute bound
- Answer B: It is data bound
- Answer C: It uses specialized hardware
- Answer D: It uses commodity hardware
- Answer E: It is fault tolerant

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_132)

# BI vs Big Data

## Business Intelligence

> Business intelligence (BI) comprises the strategies and technologies used by enterprises for the data analysis of business information.
>
> BI technologies provide historical, current, and predictive views of business operations. 

_Wikipedia_

Business Intelligence _can_ use Big Data ecosystems, but is more commonly considered something different.

https://medium.com/doctolib/data-engineers-are-no-longer-data-folks-d10d44712580
https://alphalyr.fr/blog/difference-bi-business-intelligence-big-data/

## Classical BI key points

- Build data systems from Business questions
- KPI and business decisions oriented
- Data warehouse, mainframe = Big server with closed technology
- Use structured data, like SQL databases, 
- Oriented towards Data Value

## Big Data key points

- Find insights from the data systems, 
- KPI and business of course, but many more use cases
- Distributed architecture, lot of Open Source
- Different toolset (Hadoop, Python), 
- Every data flavor, keep anything!
- Data Volume, Variety, Velocity

# Hadoop and Big Data legacy

## Is Hadoop dead?

Not quite yet. Still **used in many places**

. . .

It grew up with **web giants**, producing a really rich and **open source** ecosystem

. . .

But clearly the two main components (HDFS and MapReduce) are now **deprecated**

. . .

And have paved the way to better alternatives

## Future of Big Data

Infrastructure: Private or public cloud, and HPC(DA) in some cases.

. . .

HDFS? Object Storage!

. . .

MapReduce? Spark, Dask.

. . .

Chunked file format (SequenceFile)? Parquet, Zarr, Cloud optimized Geotiff.

. . .

YaRN? HPC job scheduler, or Kubernetes

. . . 

### Cloud Computing

## Quizz

What technologies are replacing Hadoop ecosystem (multiple choices)?

- Answer A: Map Reduce
- Answer B: MPI (Message Passing Interface)
- Answer C: Spark
- Answer D: Cloud computing and object storage

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_213)
