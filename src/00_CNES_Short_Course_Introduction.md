---
title: CNES Big Data Processing & Distribution Course
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2022-04-08
---

# Welcome

## Course Overview

- Big Data Processing & Distribution

Harnessing the complexity of large amounts of data is a challenge in itself. 

But Big Data processing is more than that: originally characterized by the 3 Vs of Volume, Velocity and Variety, 
the concepts popularized by Hadoop and Google require dedicated computing and storage solutions (both software and infrastructure), 
which will be explored in this module.

## Objectives

By the end of this module, participants will be able to:

- Understand the differences and usage between main distributed computing architectures (HPC, Big Data, Cloud, CPU vs GPGPU)
- Implement the distribution of simple operations via the Map/Reduce principle in PySpark
- Understand the principle of Kubernetes and object storage
- Deploy a Big Data Processing Platform (Pangeo) on the Cloud
- Either implement the distribution of data wrangling/cleaning and training machine learning algorithms using Dask
- Or implement a NDVI processing at scale using Pangeo platform.

## About myself{background-image="images/HPC-blue.jpg" style="color:white"}

- Guillaume Eynard-Bontemps
- CNES (Centre National d'Etudes Spatiales - French Space Agency)
- Since 2016: 
  - 6 years in CNES Computing Center team
  - Technical lead of the team
  - 3 years of using Dask/Python on HPC and in the Cloud
  - A bit of Kubernetes and Google Cloud
- Before that: 5 years on Hadoop and Spark
- Originally: Software developer (a lot of Java)

## First quizz

I'll try to propose some quizz to be sure you're following!

Let's try it.

What is this course module main subject?

- Answer A: Cloud computing
- Answer B: Data Distribution & Processing
- Answer C: Machine Learning

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_315) _Key: do_

# Program

## Big Data & Distributed Computing (3.5h)

- [Introduction to Big Data and its ecosystem (45min)](01_Introduction_Big_Data.html)
  - What is Big Data?
  - Legacy “Big Data” ecosystem
  - Big Data use cases
  - Big Data to Machine Learning
- [Big Data platforms, Hadoop, HPC & Beyond (1h45min)](02_Big_Data_Platforms.html)
  - Hadoop, HDFS and MapReduce
  - Datalakes, Data Pipelines
  - HPC Platforms Architecture
  - From HPC to Big Data to Cloud and High Performance Data Analytics 
  - BI vs Big Data
  - Hadoop legacy: Spark, Dask, Object Storage ...
- [Spark](03_Spark_Introduction.html)
  - Spark Introduction (30min)
  - Exercise: Play with MapReudce through Spark (30min)

## Cloud, Kubernetes & Object stores (3.5h)

- [The Cloud in 30 minutes (30min)](10_Cloud_Computing.html)
  - What's the Cloud, Virtualization
  - Cloud history, layers, Engines
  - Usage revolution and new Data processing standard
- [Containers Orchestration (1h)](12_OrchestrationKubernetes.html)
  - Container orchestration and Kubernetes
  - Processing Platform over Kubernetes (Databricks, Coiled)
- [Object storage (30min)](14_ObjectStorage.html)
  - Object storage concepts: POSIX vs Object
  - Object storage architecture
  - Processing tools interfaces, Cloud Optimized files
- [Deploy a Data processing platform on the Cloud based on Kubernetes and Dask (1.5h)](13_Dask_On_Cloud.html)
  - Exercise: DaskHub or Dask Kubernetes or Pangeo

## Python ecosystem for data processing and Dask at scale (3.5h)

- [The rise of the Python ecosystem for Data Processing (1h)](21_Python_Data_Processing.html)
  - Data Science programming languages
  - Pydata stack (Pandas, Numpy, Matlplotlib, Jupyter)
  - Distributed and sctientific processing (Dask, PySpark)
  - Data vizualisation (Seaborn, Plotly, Pyviz)
  - Machine and Deep Learning (Sickit Learn, TensorFlow, Pytorch)
  - Jupyter notebooks, Binder, Google Colab
- [Dask Presentation (30min)](22_Dask_Pangeo.html)
- Dask/Pangeo practice:
  - Either play with Pangeo notebooks ([in the cloud](https://gallery.pangeo.io/) or [on HAL cluster](https://gitlab.cnes.fr/inno/pangeo-jupyter-demo)
  - [Or try to answer Supaero evaluation notebook!](30_Evaluation.html)

## Quizz

What will we do today (multiple choices)?

- Answer A: Explain what's Big Data
- Answer B: See what's Hadoop
- Answer C: Dig into Cloud computing
- Answer D: Take a nap
- Answer E: Some Spark

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_972) _Key: qp_

