---
title: Big Data Processing Course Introduction
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-15
---

# Welcome

## Course Overview

- Big Data Processing

Harnessing the complexity of large amounts of data is a challenge in itself. 

But Big Data processing is more than that: originally characterized by the 3 Vs of Volume, Velocity and Variety, 
the concepts popularized by Hadoop and Google requires dedicated computing solutions (both software and infrastructure), 
which will be explored in this module.

## Objectives

By the end of this module, participants will be able to:

- Understand the differences and usage between main distributed computing architectures (HPC, Big Data, Cloud, CPU vs GPGPU)
- Implement the distribution of simple operations via the Map/Reduce principle in PySpark
- Connect on a cloud computing engine (e.g. Google Cloud Platform) and  use it
- Understand the principle of containers (through Docker) and Kubernetes
- Deploy a Big Data Processing Platform on the Cloud
- Implement the distribution of data wrangling/cleaning and training machine learning algorithms using PyData stack, Jupyter notebooks and Dask

## Typical daily schedule

| Time slot | Content |
|-----------|---------|
| 9:00-10:30 | Slides, tutorial or exercises |
| 10:30-10:45 | Coffee Break |
| 10:45-12:15 | Slides, tutorial or exercises |
| 12:15-13:15 | Lunch (I know it's a bit short) |
| 13:15-15:15 | Slides, tutorial or exercises (not nap) |
| 15:15-15:45 | Coffee Break (we may also make two breaks of 15min) |
| 15:45-17:15 | Slides, tutorial or exercises (last session, at last) |

I'll try to propose some quizz to be sure you're following!

## About myself{background-image="images/HPC-blue.jpg" style="color:white"}

- Guillaume Eynard-Bontemps
- CNES (Centre National d'Etudes Spatiales - French Space Agency)
- Since 2016: 
  - 5 years on CNES Computing Center team
  - Technical lead of the team
  - 3 years of using Dask/Python on HPC and in the Cloud
  - A bit of Kubernetes and Google Cloud
- Before that: 5 years on Hadoop and Spark
- Originally: Software developer (a lot of Java)

## About yourselves

What are the previous courses you've followed in this master?

What are you familiar with in the big data, cloud, Python and machine learning subjects?

## First quizz

Let's try the Quizz mechanism.

What is this course module main subject?

- Answer A: Cloud computing
- Answer B: Big Data Processing
- Answer C: Machine Learning

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_852)

# Program

## Day 1: Big Data, Distributed Computing and Spark

- Introduction to Big Data and its ecosystem (1h)
  - What is Big Data?
  - Legacy “Big Data” ecosystem
  - Big Data use cases
  - Big Data to Machine Learning
- Big Data platforms, Hadoop & Beyond (2h)
  - Hadoop, HDFS and MapReduce,
  - Datalakes, Data Pipelines
  - From HPC to Big Data to Cloud and High Performance Data Analytics 
  - BI vs Big Data
  - Hadoop legacy: Spark, Dask, Object Storage ...
- Spark Introduction (1h)
- Play with MapReduce through Spark (Notebook on small datasets) (2h)

## Day 2: Cloud Computing and Kubernetes

- Introduction to Cloud Computing (2h)
  - What's the Cloud, Virtualization
  - Cloud history, layers, Engines
  - Usage revolution and new Data processing standard
  - Google Cloud Engine
- First interaction with Google Cloud, how to get a server? (1h)
  - Exercise through Google console or cloud CLI
- Container & Kubernetes (2h) 
  - Container & Docker
  - Play with Docker
  - Kubernetes & CaaS & PaaS (Databricks, Coiled)
  - Play with Kubernetes (if we have time)
- Deploy a Data processing platform on the Cloud based on Kubernetes and Dask (1.5h)
  - Exercise: DaskHub or Dask Kubernetes or Pangeo

## Day 3: Python ecosystem for data processing and Dask

- The rise of the Python ecosystem for Data Processing (1.5h)
  - Data Science programming languages
  - Pydata stack (Pandas, Numpy, Matlplotlib, Jupyter)
  - Distributed and sctientific processing (Dask, PySpark)
  - Data vizualisation (Seaborn, Plotly, Pyviz)
  - Machine and Deep Learning (Sickit Learn, TensorFlow, Pytorch)
  - Jupyter notebooks, Binder, Google Colab
- Pandas tutorial (1h)
- Dask Presentation (1h)
- Dask Tutorial (2h)
- Pangeo tutorial or finish deploying your computing platform (1h)

## Day 4: Evaluation

- Prerequisite: Pangeo platform deployed before (on day 2 and 3)
- Clean big amounts of data using Dask in the cloud (3h)
- Train machine learning models in parallel (hyper parameter search) (3h)
- Notebook with cell codes to fill or answers to give

## Quizz

What will we do today (multiple choices)?

- Answer A: Explain what's Big Data
- Answer B: See what's Hadoop
- Answer C: Dig into Cloud computing
- Answer D: Take a nap
- Answer E: Some Spark

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_81)

