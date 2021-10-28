---
title: Big Data Processing Course Introduction
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-15
---

# Welcome

## Course Overview

Title
- ARTIFICIAL INTELLIGENCE & BUSINESS TRANSFORMATION
- BLOC 1 : ARTIFICIAL INTELLIGENCE INTERNALS
- AIBT103_Big Data Processing

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
| 9:00-10:30 | Slides, tutorial or exercices |
| 10:30-10:45 | Coffee Break |
| 10:45-12:15 | Slides, tutorial or exercices |
| 12:15-13:15 | Lunch (I know it's a bit short) |
| 13:15-15:15 | Slides, tutorial or exercices (not nap) |
| 15:15-15:45 | Coffee Break (we may also make two breaks of 15min) |
| 15:45-17:15 | Slides, tutorial or exercices (last session, at last) |

I'll try to propose some quizz to be sure your following!

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

# Program

## Day 1: Big Data, Distributed Computing and Spark

- Introduction to Big Data and its ecosystem (1h)
  - What is Big Data?
  - Legacy “Big Data” ecosystem
  - Big Data use cases
  - Big Data to Machine Learning
- Big Data platforms (2h)
  - Hadoop, HDFS and MapReduce,
  - Datalakes
  - From HPC to Big Data to Cloud and High Performance Data Analytics 
  - BI vs Big Data
  - Hadoop legacy: Spark, Dask, Object Storage ...
- Spark Introduction (1h)
- Play with MapReduce through Spark (Notebook on small datasets) (2h)

## Day 2: Cloud Computing and Kubernetes

- Introduction to Cloud Computing (2h)
  - What's the Cloud, Virtualization
  - Cloud history, layers, Engines
  - Usage revolution an new Data processing standard
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
  - Pydata stack (Pandas, Numpy, Dask)
  - Machine and Deep Learning (Sickit Learn, TensorFlow Pytorch)
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

