---
title: The rise of the Python ecosystem for Data Processing 
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-17
---

# Data Science programming languages

## R

:::::::::::::: {.columns}
::: {.column width="50%"}

- Programming language and free software environment
- Open source
- Interactive
- Ecosystem
  - Statistical computing
  - Graphics, vizualisation
  - Data analysis

:::
::: {.column width="50%"}

![R Studio](https://www.rstudio.com/images/screenshots/rstudio-windows.png)

:::
::::::::::::::

## Julia

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://julialang.org/assets/infra/lorenz.gif)

:::
::: {.column width="50%"}

- Fast: designed for high performance
- Open source
- Dynamically typed, interactive use
- Ecosystem
  - Scientific and parallel computing
  - Visualisation and plotting
  - Data science and machine learning

:::
::::::::::::::

## Matlab and others

Matlab (and equivalent Scilab)
- Interactive
- With IDE and plotting
- Closed, not reproducible
- For some searchers

C/C++, Java
- Static languages
- Not much visualization
- For under layers of use libraries.

## Python

:::::::::::::: {.columns}
::: {.column width="50%"}

- Interpreted and so interactive language
- Really simple syntax (Code readability)
- General-purpose programming language
- Many, many (many) libraries
  - A lot of scientific ones!
- Ecosystem
  - Scientific and parallel computing
  - Visualisation and plotting
  - ML, DL
  - Web developement

:::
::: {.column width="50%"}

![](https://ipython.org/_static/ipy_0.13.png)

:::
::::::::::::::

## Python the most used language?

![](images/PythonTrends.png)

## Kaggle IDE Popularity

![](images/KaggleIDEPop.png)

# Python scientific ecosystem

## Overview{background-image=https://jupytearth.org/_images/python-stack.png}

# Core (SciPy, PyData ...)

## Pandas

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://pandas.pydata.org/static/img/pandas.svg){height=10%}

- Deal with Dataframes, e.g. tables
- Data manipulation and analysis
- Numerical tables and time series
- Statistics, transformations, joins...

```python
import pandas as pd
pd.read_csv('Myflie.csv')
pd.describe()
```

:::
::: {.column width="50%"}

![](images/PandasTrends.png)

:::
::::::::::::::
 
## Numpy

![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/NumPy_logo_2020.svg/2560px-NumPy_logo_2020.svg.png){height=10%}

- Manipulate N-dimensionnal arrays
- Numerical computing tools (math functions, linear algebra, Fourier transform, ...)
- Performant: core is well-optimized C code
- Easy and de facto standard syntax

> Nearly every scientist working in Python draws on the power of NumPy. 

```Python
# The standard way to import NumPy:
import numpy as np

# Create a 2-D array, set every second element in
# some rows and find max per row:

x = np.arange(15, dtype=np.int64).reshape(3, 5)
x[1:, ::2] = -99
x
array([[  0,   1,   2,   3,   4],
       [-99,   6, -99,   8, -99],
       [-99,  11, -99,  13, -99]])
x.max(axis=1)
array([ 4,  8, 13])

# Generate normally distributed random numbers:
rng = np.random.default_rng()
samples = rng.normal(size=2500)
```

## Matplotlib

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://matplotlib.org/stable/_static/logo2_compressed.svg){height=10%}

- Base/Reference plotting library
- For Python and Numpy
- Static, animated, and interactive visualizations
- Designed to be as usable as MATLAB

```python
fig, ax = plt.subplots(subplot_kw={"projection": "3d"})

# Plot the surface.
surf = ax.plot_surface(X, Y, Z, cmap=cm.coolwarm,
                       linewidth=0, antialiased=False)

# Customize the z axis.
ax.set_zlim(-1.01, 1.01)
ax.zaxis.set_major_locator(LinearLocator(10))
# A StrMethodFormatter is used automatically
ax.zaxis.set_major_formatter('{x:.02f}')

# Add a color bar which maps values to colors.
fig.colorbar(surf, shrink=0.5, aspect=5)

plt.show()
```

:::
::: {.column width="50%"}

![](https://matplotlib.org/stable/_images/sphx_glr_surface3d_001.png)

:::
::::::::::::::

## Jupyter (Lab and Notebook)

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://jupyter.org/assets/labpreview.png)

:::
::: {.column width="50%"}

![](https://jupyter.org/assets/main-logo.svg){height=10%}

- Open source web application
- Create and share documents that contain live code
- Equations, visualizations and narrative text
- Interactive programming and visualizing
- Usage: 
  - data cleaning and transformation, 
  - numerical simulation, 
  - statistical modeling, 
  - data visualization, 
  - machine learning
- Used by Google Colab or Kaggle

:::
::::::::::::::

# Distributed computing

## Built-in mutliprocessing

## Dask

## PySpark

## Ray

# Packaging

## Pip

## Conda

# Vizualisation

## Matplotlib, 

## Seaborn Leaflet

## Pyviz: Bokeh, Holowiews… 

# Others

## Binder?

https://pyviz.org/ 

# Machine and Deep Learning

## Sickit Learn

Every traditional ML algorithm.
Python.

## TensorFlow, Keras, Pytorch

Deep Learning on GPU with no knowledge
Python.

## Xgboost, Light GBM…

Other popular algorithms. Python.

# Scientific domain

## Astropy Sunpy

## GeoPandas...

# Exercice

## Pandas tutorial

https://github.com/jvns/pandas-cookbook 
