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
- Fault tolerant

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
- Fault tolerant

## Hadoop cluster components{background-image=https://pbs.twimg.com/media/EKzU0wMWsAAkKLc.jpg data-background-opacity=0.2}

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

[Answer link](https://toreply.univ-lille.fr/reponse_483) _Key: ye_

## Map Reduce exercise

[Learning Python](https://www.learnpython.org/en/Map%2C_Filter%2C_Reduce)

# HDFS 

## HDFS Basics

:::::::::::::: {.columns}
::: {.column width="50%"}

### Distributed File System

- Written in **Java**
- Allowing to **store** massive amounts of data, 
  - structured or not, 
  - on a cluster of machines
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
  - similar or better durability as replication 3, 
  - but **only 50%** volume increase (can be less or more)
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

[Answer link](https://toreply.univ-lille.fr/reponse_33) _Key: ny_

# Map Reduce

## Map Reduce Basics

- **Functional** language concept
- Heavily used by Google for **WWW indexing**
- **Colocate** data and processing (with Hadoop and alikes)
- Automatic process **ditribution** on pieces of data (eager distribution)
- Optimized for fast processing of **huge datasets**
- **Fault tolerant**: 
  - Data is replicated, 
  - Individual tasks can be restarted anywhere

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

[Answer link](https://toreply.univ-lille.fr/reponse_755) _Key: ew_

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

[Answer link](https://toreply.univ-lille.fr/reponse_533) _Key: ql_

# Data pipelines and associated tools

## Data manipulation is complex

You won't usually achieve what you want with a single MapReduce or Spark job.

Let's say you want to train a ML model every time a text file is updated on a website and evaluate it next.

You'll need to:

::: incremental

- Periodically poll the website for new data
- Launch your model training when new text file is availaible
- Evaluate your new model on a reference dataset
- Push the evaluation result somewhere you can see it

:::

## Processing pipelines

This is called a Pipeline or a workflow.

It mainly means chaining tasks or jobs together to automatically produce a result from an input.

Tasks are typically either:

- Triggered based on a date, periodicity (like Linux crontab for those who knows).
- Triggered by an external event: data availability.
- Triggered by the end of the previous task or tasks.

It is usually represented by Direct Acyclic Graphs (DAGs).

## Example in Satellite ground segment

![Iota2 Pipeline](images/Iota2Pipeline.png)

## Some tools

![Airflow](https://airflow.apache.org/docs/apache-airflow/stable/_images/airflow.gif)

Plenty others from Apache or in Python ecosystem.

# HPC Platforms

## Overview and Use cases

:::::::::::::: {.columns}
::: {.column width="40%"}

> HPC = High Performance Computing

- HPC were built to solve compute bound problems
- Some early fields of research:
  - Weather forecasting
  - Atmospheric and climate research
  - Rockets and Aeronautics design
  - Computational Fluid Dynamics in general
- High performance infrastructure: compute, CPU, storage, Network

:::
::: {.column width="60%"}

<iframe src="https://player.vimeo.com/video/300943265?h=ef84e12ec0" width="640" height="362" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
<p><a href="https://vimeo.com/300943265">Current speed in eNATL60 simulation with explicit tidal motion.</a> from <a href="https://vimeo.com/oceannumerique">Oc&eacute;an Num&eacute;rique</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

- number of processors in parallel required: 18000
- Model time step: 40s
- Model integration speed: 45 minutes for 1 model day
- 40 million cpu-hour allocation

:::
::::::::::::::

## CNES typical use cases

Take slide from Roadmap.

## Architecture, big picture

Just a schema with all elements: login nodes, job scheduler, compute nodes, storage, IB network...

## Job scheduler

- Job Queuing System
- Resources management
- SLURM, PBS, SGE, LSF, etc.
- Priority, fairshare partition, QoS

Example resources reservation
Some schema?

## High Performance Storage

- POSIX file system
- Usually based on powerfull SAN storage infrastructure
- High performance and capacity: millions IO/s, undreds GB/s, undreds PB capacity.
- Spectrum Scale (GPFS) and Lustre
- Other players: WekaIO, BeeGFS

Schema IO nodes and SAN 

## Software technologies

- Classical HPC: C and Fortran
  - Compile languages, hardware optimized
  - MPI
  - OpenMP
  - CUDA, OpenACC
- More and More: Python, Julia
  - Interpreted Languages, easyer to use
  - Lots of performant libraries to reuse (e.g. Numpy, Scipy, Pandas, etc.)
  - Parallel and distributed computations:
    - Multiprocessing
    - MPI4Py : Python over MPI
    - Dask, Ray, etc.

Some MPI Code?

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

- Hadoop world step towards HPC: YaRN, equivalent to HPC resources scheduler
- HPC step towards Big Data: hardware not so specialized
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

[Answer link](https://toreply.univ-lille.fr/reponse_143) _Key: mq_

# BI vs Big Data

## Business Intelligence

> Business intelligence (BI) comprises the strategies and technologies used by enterprises for the data analysis of business information.
>
> BI technologies provide historical, current, and predictive views of business operations. 

_Wikipedia_

Business Intelligence _can_ use Big Data ecosystems, but is more commonly considered something different.

[https://medium.com/doctolib/data-engineers-are-no-longer-data-folks-d10d44712580](https://medium.com/doctolib/data-engineers-are-no-longer-data-folks-d10d44712580)
[https://alphalyr.fr/blog/difference-bi-business-intelligence-big-data/](https://alphalyr.fr/blog/difference-bi-business-intelligence-big-data/)

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

[Answer link](https://toreply.univ-lille.fr/reponse_943) _Key: tw_
