---
title: Deploy Data processing platform on the Cloud
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-16
---

# Context

Dask

- #1 Distributed processing tool in Python
- Distributed Dataframe and Arrays
- We'll see more of it tomorrow

Pangeo

- Community of (geo)scientists and developers
- Tackling big data problems: analysing simulations or sensor data
- Providing recipes to build a Pangeo platform:
  - Jupyterhub
  - Dask
  - Xarray
  - on Kubernetes or HPC

# Exercise

We will focus on getting a data processing platform on the Cloud:

- Dask cluster running in Kubernetes, 
- With Pangeo libraries available,
- Which we will then use in the final evaluation.

[Documentation notebook](https://github.com/SupaeroDataScience/OBD/blob/master/notebooks/Kubernetes_Daskhub.ipynb)
