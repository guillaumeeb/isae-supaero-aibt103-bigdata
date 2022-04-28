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

## Quizz

What is the main used language (in Data Science)?

- Answer A: R
- Answer B: Go
- Answer C: Python
- Answer D: Matlab

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_921)

# Python scientific ecosystem{background-image=https://jupytearth.org/_images/python-stack.png}

# Core (SciPy, PyData ...)

## Pandas

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://pandas.pydata.org/static/img/pandas.svg){height=100px}

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

:::::::::::::: {.columns}
::: {.column width="60%"}

![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/NumPy_logo_2020.svg/2560px-NumPy_logo_2020.svg.png){height=100px}

- Manipulate N-dimensionnal arrays
- Numerical computing tools (math functions, linear algebra, Fourier transform, ...)
- Performant: core is well-optimized C code
- Easy and de facto standard syntax

> Nearly every scientist working in Python draws on the power of NumPy. 

:::
::: {.column width="40%"}

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

:::
::::::::::::::

## Xarray

:::::::::::::: {.columns}
::: {.column width="40%"}

![](http://xarray.pydata.org/en/stable/_static/dataset-diagram-logo.png){height=100px}

- Manipulate N-dimensionnal **labelled** arrays and **datasets**
- Introduce dimensions, coordinates and attributes on top of Numpy
- Borrows heavily from Pandas

:::
::: {.column width="60%"}

![](https://gdfa.ugr.es/python/climate_data/img/xarray2.png)

:::
::::::::::::::

## Matplotlib

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://matplotlib.org/stable/_static/logo2_compressed.svg){height=100px}

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

![](https://jupyterlab.readthedocs.io/en/1.2.x/_images/jupyterlab.png)

:::
::: {.column width="50%"}

![](https://jupyter.org/assets/homepage/main-logo.svgg){height=100px}

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

## Quizz

Which tools allows manipulating tabular data?

- Answer A: Numpy
- Answer B: Xarray
- Answer C: Pandas
- Answer D: Jupyter

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_120)

# Distributed and sctientific computing

## Built-in mutliprocessing

- Python core package
- Spawning processes using an API similar to the threading module
- Effectively side-steps the **Global Interpreter Lock** by using subprocesses instead of threads

```python
from multiprocessing import Pool

def f(x):
    return x*x

if __name__ == '__main__':
    with Pool(5) as p:
        print(p.map(f, [1, 2, 3]))
```

## Dask

:::::::::::::: {.columns}
::: {.column width="50%"}

![](https://dask.org/_images/dask_horizontal_white_no_pad.svg){height=100px}

- Provides advanced parallelism for analytics
- First designed as allowing to process datasets bigger than memory
- Now from local computer to clusters, to HPC or Cloud computing
- Scales Numpy and Pandas with same interfaces
- More low level APIs for distributing any algorithm
- More this afternoon

```python
import dask.dataframe as dd
df = dd.read_csv('2014-*.csv')
df.describe().compute()
```

:::
::: {.column width="50%"}

![](https://docs.dask.org/en/latest/_images/dask-dataframe.svg){width=40%}

:::
::::::::::::::

## PySpark

![](https://databricks.com/wp-content/uploads/2018/12/PySpark-1024x164.png){height=100px}

- Spark is Scala (JVM based), but for data scientists, provides Python and R interface
- This means some complexity and translation between languages

![](images/PySpark.jpg)


## Others

:::::::::::::: {.columns}
::: {.column width="50%"}

### [Ray](https://www.ray.io)

![](https://docs.ray.io/en/latest/_static/ray_logo.png){height=100px}

- Scale general Python apps
- And a lot of high-level libs oriented towards Machine and Deep Learning

:::
::: {.column width="50%"}

### [Vaex](https://vaex.io/docs/index.html)

![](https://user-images.githubusercontent.com/18574951/90343540-a1181f80-e011-11ea-8ff5-bb21e5fdc71c.png){height=100px}

- Lazy out-of-core Dataframes (similar to Pandas)
- Performance oriented on tabular datasets
- Vizualisation

:::
::::::::::::::

## Quizz

What Dask does better than Spark (multiple choices)?

- Answer A: Dataframes manipulation
- Answer B: N-dimensionnal Arrays manipulation
- Answer C: Low level parallelization
- Answer D: Scaling to Petabytes dataset
- Answer E: Reliability

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_618)

# Vizualisation (other than Matplotlib)

## Landscape

![Adaptation of Jake VanderPlas graphic about the Python visualization landscape, by Nicolas P. Rougier](https://rougier.github.io/python-visualization-landscape/landscape-colors.png)

## Seaborn

![](https://seaborn.pydata.org/_images/logo-wide-lightbg.svg){height=100px}

- Based on Matplotlib
- Integrates closely with Pandas
- Dataset oriented to produce informative plots

![](https://seaborn.pydata.org/_images/faceted_lineplot.png)

## Plotly

![](https://upload.wikimedia.org/wikipedia/commons/3/37/Plotly-logo-01-square.png){height=100px}

- Interactive, publication-quality graphs
- Make dashboard with Dash

![](https://raw.githubusercontent.com/cldougl/plot_images/add_r_img/anim.gif)

## Pyviz

![](https://miro.medium.com/max/518/1*Tw1LzNLwcmpJPVI0v1ZsVA.png)
![](https://miro.medium.com/max/2400/1*I-xXZpedIymi1cP3RRrhHw.png)

- **HoloViews**: Declarative objects for instantly visualizable data, building Bokeh plots from convenient high-level specifications
- **GeoViews**: Visualizable geographic data that that can be mixed and matched with HoloViews objects
- **Bokeh**: Interactive plotting in web browsers, running JavaScript but controlled by Python
- **Panel**: Assembling objects from many different libraries into a layout or app, whether in a Jupyter notebook or in a standalone serveable dashboard
- **Datashader**: Rasterizing huge datasets quickly as fixed-size images
- **hvPlot**: Quickly return interactive HoloViews or GeoViews objects from your Pandas, Xarray, or other data structures
- **Param**: Declaring user-relevant parameters, making it simple to work with widgets inside and outside of a notebook context

## Quizz

Matlplotlib is the only vizualisation library for Python.

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_672)

# Machine and Deep Learning

## Kaggle stats

![Machine Learning Frameworks usage](images/KaggleFrameworkUsage.png)

## Sickit Learn

![](https://scikit-learn.org/stable/_images/scikit-learn-logo-notext.png){height=100px}

- Simple and efficient tools for predictive data analysis
- Built on NumPy, SciPy, and matplotlib
- Every classical ML Algorithms
- Standard interface with Pipelines, estimators, transformers
- No GPU support (so not good for Deep Learning)

```python
from sklearn.ensemble import RandomForestClassifier
clf = RandomForestClassifier(random_state=0)
X = [[ 1,  2,  3],  # 2 samples, 3 features
     [11, 12, 13]]
y = [0, 1]  # classes of each sample
clf.fit(X, y)
```

## TensorFlow, Keras, Pytorch

![](https://camo.githubusercontent.com/906e661107a3bc03104ca5d88336d1f4b0e80fdcac65efaf7904041d371c747f/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6b657261732e696f2f696d672f6b657261732d6c6f676f2d323031382d6c617267652d313230302e706e67){height=100px}
![](https://camo.githubusercontent.com/aeb4f612bd9b40d81c62fcbebd6db44a5d4344b8b962be0138817e18c9c06963/68747470733a2f2f7777772e74656e736f72666c6f772e6f72672f696d616765732f74665f6c6f676f5f686f72697a6f6e74616c2e706e67){height=100px}
![](https://upload.wikimedia.org/wikipedia/commons/9/96/Pytorch_logo.png){height=100px}

- Deep Learning on GPU with no previous knowledge
- Keras on top of Tensorflow
- Tensorflow complete platform, with TensorBoard and other tools
- Always trolls about Keras/TF vs PyTorch

![](https://www.tensorflow.org/tensorboard/images/tensorboard.gif){width=50%}

## Gradient boosting algorithms

:::::::::::::: {.columns}
::: {.column width="50%"}

### [XGBoost](https://xgboost.readthedocs.io/en/latest/)

- Distributed gradient boosting library
- Efficient, flexible and portable
- XGBoost provides a parallel tree boosting
- Runs on major distributed environment (Hadoop, SGE, MPI, Spark)
- Solve problems beyond billions of examples

![](https://raw.githubusercontent.com/dmlc/dmlc.github.io/master/img/logo-m/xgboost.png){height=100px}

:::
::: {.column width="50%"}

### [LighGBM](https://lightgbm.readthedocs.io/en/latest/)

- Distributed gradient boosting framework
- Efficient, Faster, lower memory usage, better accuracy
- Support of parallel, distributed, and GPU learning
- Capable of handling large-scale data

![](https://lightgbm.readthedocs.io/en/latest/_images/LightGBM_logo_black_text.svg){height=100px}

:::
::::::::::::::

## Quizz

Which is the best Deep Learning library in Python?

- Answer A: Sickit-Learn
- Answer B: Keras
- Answer C: TensorFlow
- Answer D: PyTorch
- Answer E: XGBoost

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_72)

# Others

## Packaging: Pip / Conda

![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/PyPI_logo.svg/1200px-PyPI_logo.svg.png){height=100px}
![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/Conda_logo.svg/1280px-Conda_logo.svg.png){height=100px}

- Package libraries
- Make them available on repositories
- Build environments automatically

|     | conda | pip |
|-----|-------|-----|
| manages | binaries | wheel or source |
| can require compilers | no | yes |
| package types | any | Python-only |
| create environment | yes, built-in | no, requires virtualenv or venv |
| dependency checks | yes | no |

Difference between Conda and Pip according to Anaconda.

## Numba

![](https://numba.pydata.org/_static/numba-blue-horizontal-rgb.svg){height=100px}

> Numba makes Python code fast

- Translates Python functions to optimized machine code at runtime
- Use LLVM compiler library
- Python can approach the speeds of C or FORTRAN
- Just apply one of the Numba decorators

```python
from numba import jit
import random

@jit(nopython=True)
def monte_carlo_pi(nsamples):
    acc = 0
    for i in range(nsamples):
        x = random.random()
        y = random.random()
        if (x ** 2 + y ** 2) < 1.0:
            acc += 1
    return 4.0 * acc / nsamples
```

## Binder

![](https://mybinder.org/static/logo.svg?v=fe52c40adc69454ba7536393f76ebd715e5fb75f5feafe16a27c47483eabf3311c14ed9fda905c49915d6dbf369ae68fb855a40dd05489a7b9542a9ee532e92b)

> Turn a Git repo into a collection of interactive notebooks

![](https://binderhub.readthedocs.io/en/latest/_images/architecture.png)

# Exercise

## Pandas tutorial

[Let's try Pandas in Binder](https://github.com/jvns/pandas-cookbook)

Follow this first tutorial at least till chapter 6. Use the binder button!

[Pandas & Scikit-learn](https://github.com/INRIA/scikit-learn-mooc/)

If you have time, go through part "The predictive modeling pipeline". Notebook 01 to 03. With Binder too.
