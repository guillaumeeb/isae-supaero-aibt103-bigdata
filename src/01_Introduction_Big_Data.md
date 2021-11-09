---
title: Introduction to Big Data and its Ecosystem
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-15
---

# What is Big Data?

## Data evolution

1 ZB  
1,000,000 PB  
1,000,000,000,000 GB  
1,000,000,000,000,000,000,000 B  

![Evolution of the global datasphere size (IDC)](https://supaerodatascience.github.io/OBD/slides/static/img/datasphere.png)

## Some figures

![Volume of data produced in a day in 2019 (source www.visualcapitalist.com)](https://www.visualcapitalist.com/wp-content/uploads/2019/04/a-day-in-data.jpg){width="50%"}

## Some figures in sciences

:::::::::::::: {.columns}
::: {.column width="50%"}

### Earth Observation Data

![Volume of data per year (source The Australian Geoscience Data Cube — Foundations and lessons learned, A. Lewis)](https://www.researchgate.net/profile/Adam-Lewis-12/publication/316080947/figure/fig1/AS:621814552227846@1525263550337/The-estimated-volumes-EOS-data-produced-by-the-Landsat-8-Sentinel-1-2-3-and.png){width="60%"}

:::
::: {.column width="50%"}

### CERN

- The LHC experiments produce about 90 petabytes of data per year
- an additional 25 petabytes of data are produced per year for data from other (non-LHC) experiments at CERN

![CERN current data volumes](images/CERNVolumes.png)

[You can have a look](https://monit-grafana-open.cern.ch/d/000000884/it-overview?orgId=16)

:::
::::::::::::::

## 3V, 4V, 5V{background-image="https://www.lebigdata.fr/wp-content/uploads/2016/05/les-4-V-du-big-data-ibm.jpg"}

## What is Behind Big Data

:::::::::::::: {.columns}
::: {.column width="50%"}

### Data

Volume, variety, multiple sources, internal, external...

### Tools and technology

Store, Compute, Analyse: Calculators, Cloud, Hadoop, Spark, Dask

Visualize, Use: Applications, Web interfaces

:::
::: {.column width="50%"}

### Definition (Wikipedia)

> Big data is a field that treats ways to analyze, systematically extract information from, or otherwise deal with data sets that are too large or complex to be dealt with by traditional data-processing application software.

> Big data is where parallel computing tools are needed to handle data.

Not a technology.

:::
::::::::::::::

## Quizz

What is the estimated size of the global data sphere?

- Answer A: 175 Petabytes
- Answer B: 175 Exabytes
- Answer C: 175 Zetabytes

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_946)

## Quizz

Cite some V's of Big Data (multiple choices):

- Answer A: Validation
- Answer B: Volume
- Answer C: Velocity
- Answer D: Voldemort
- Answer E: Variety

![Answer](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAASwAAAEsCAIAAAD2HxkiAAAGpUlEQVR42u3d3ZKiOhQG0PaU7//KfS6sopwWEQ37J7LWzcx0qUDgm8Skk1x+f39/gDr/KQIQQji16+2Py+Wy/Ki2gXo7k+hzuL/e+6t+9vOcM3k81rPS6HO/OKYmXO70swfx8Mcu+hAvLRf75+/3P0koje2SX/65+vO0+0V4CP/8X1t+Xx8jUZvVuNLYLvlnSet2vzisObqzZfjnJ88aRXsae6sNreUFOxtgy4dsvLFtW3rjZY9JuzUfbplc/p7Weqdpx8zL/6ofG3XbjcCNh+lls61D2+xZ6/HwAC9XKoGnDuFbjaLBFubLYzVpm/05jbgq1HfCr22OfvDf6urtX9pLO5te3+Szy/wsgY8tVU/z9CFcDc9nz9zjNz1PyVsJ9MXvXM3R1dt8+8vql72NjpbbP99K8p4Xb3cP9ulo+Xl/9GXj85998SssDaIes9WvWPcV133H40bv6MbPf573gu5/13bv6LuxiRisf3cAfeMr9MvLMVj/hSGkpOYEIYQG3wkVAQghCCEghCCEgBCCEAJCCEIICCEIISCEIISAEIIQAkIIQggIIQghEOeac5iGq0SvLq6z/zw/W4Ut/zwHPzNtCaJZnhA1IWiOAkIIQggIIQghcJRr4bEbdn9HnFLaYMbg0SOufXDY4yQDJGpC0BwFIQSEEIQQEEI4p2u3E4qYHzB49ME5B/tfGTFhYnCQYHB0J23YI+0JUROC5igghCCEgBCCEAJHuSqCe2kjHGmnNHjy+0+pdp0oNSEghCCEgBCCEAJCCNMxRPGPwRkPg5/Z8Ipq53CoCQEhBCEEhBCEEBBC+GLthihq+68j1nRaFdF3nzaHI6JAZnlC1ISgOQoIIQghIIQghMBRKocoavco3n9KaXtRzPLKMz8hakIQQkAIQQgBIQQhBI6SNEQx9W++N+wobzi54cxPiJoQhBAQQhBCQAhBCIEPfNteFIN7Pkd06O/vfB88esTba2/cSWaQqAlBcxSEEBBCEEJACOGckoYoBruAB9/+fesape0wkVaeEXt7DBaImhA0RwEhBCEEhBCEEAh1yemcjeh8j1jXKO3oDQ80ePSI+562IJUhCtAcBYQQhBAQQhBCIF/lXhS1vyOf9plp3d8RB6odjYgYX1ETAkIIQggIIQghIITQxKXw98dnGXiIOPnBow+e0tR7aNfOiVETguYoIIQghIAQghACR6ncLnuwBzltDaLaYY+Gm2CnrWcVUSANR2LUhCCEIISAEIIQAkII51S5XfagtKkAEQeaZQ2iiFJafWXEBuBpb1cTguYoIIQghIAQghACH7jUds4OnXrWLIpBDTeXbriRRu09GrxxakLQHAWEEIQQEEIQQuAD124nFNEr3bDrXyFX3Q41ISCEIISAEIIQAkIITSTNophll4WIK0o7+v5SStuo3AwSNSFojgJCCEIICCEIIfBMu1kUg/3CtSMcs6w9lWZwL4rvKxA1IQghIIQghIAQghACizn2ooj4rf/Bo9cOPKTNjai9cWnXnlYgakLQHAWEEIQQEEIQQmDRbqGniAMNSlvXqHYGyeBiXLWLXKWtKKUmBM1RQAhBCAEhBCEEjlI5RBGh4bBH2hyOtPM887wQNSFojgJCCEIICCEIIXCUyr0oZtl1uXadqMHPrJ3tMcvaU7WDGWpC0BwFIQSEEIQQEEI4p+uXXU/tLIr9G0EPXtHqKe0/z4jFjtImynzf1Ao1IQghCCEghCCEgBDCOVUOUaQtYVR7RavSOsobjjGkHd1CT4AQghACQghCCAghdHaZpRs3qThKd7Fe1XAri4i3R5Rn7XmqCUFzFBBCEEJACEEIgW1JsygaToMYXJRpcDAjYvmmWXaYSCvPwYdBTQiao4AQghACQghCCIRqt112hMFNGqbeHXr/gWqHkWqnVqgJQXMUEEIQQkAIQQiBfO22y67t5Y/ou9//mWljIbWrP9VuO2GhJ0AIQQgBIQQhBIQQmrgqgs9ErKq0/5UN5xxEXGbDkRg1IWiOAkIIQggIIQghcBRDFEdKm28R8fbBA0XsG1FbIGpC0BwFhBCEEBBCEEIg1CVnNZvBdY0aHn3q1YpqV9OaetMLNSFojgJCCEIICCEIIXCUylkUDX+fff95pu0wkTbnIO0z9x8oopRqR8vUhKA5CgghCCEghCCEwOLS8JfKQU0ICCEIISCEIISAEIIQAkIIQggIIQghIIQghIAQghACQghCCAghCCEghCCEgBCCEAJCCEIICCEIISCEIISAEIIQAkIIQggIIUzjf7XdbVn1JBECAAAAAElFTkSuQmCC)

[Answer link](https://toreply.univ-lille.fr/reponse_208)

# Legacy “Big Data” ecosystem

## Blowing ecosystem{background-image=https://external-preview.redd.it/P6JcS17ECpmFF2si8KVnuoKpiabc5-pWTmgRt_YxTx4.png?auto=webp&s=3cbdbbe95112b6d6f5fb0bb59f6421b8e8be999e}

## Hadoop & Map Reduce

![Hadoop ecosystem](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2016/10/HADOOP-ECOSYSTEM-Edureka.png)

## NoSQL (Not only SQL)

:::::::::::::: {.columns}
::: {.column width="50%"}

![SQL vs NoSQL databases model (Sumit Singh)](https://eadn-wc03-4064062.nxedge.io/cdn/wp-content/uploads/2020/12/asesoftware-sql-nosql.png){width=50%}

:::
::: {.column width="50%"}

![Popular NoSQL Databases](https://eadn-wc03-4064062.nxedge.io/cdn/wp-content/uploads/2020/12/NoSQL-databases.jpg)

:::
::::::::::::::

## Logs, ETL, Time series

:::::::::::::: {.columns}
::: {.column width="50%"}

![Elastic stack](https://www.elastic.co/static-res/images/elk/elk-stack-elkb-diagram.svg){width=60%}

:::
::: {.column width="50%"}

![Grafana/Prometheus/InfluxDB](https://www.sqlpac.com/en/documents/images/influxdb-v2-getting-started-setup-preparing-migration-from-version-1.7-02.png)

![Dahboards](https://grafana.com/static/img/screenshots/Modal_dashboards.png){width=60%}

:::
::::::::::::::

## Dataviz

:::::::::::::: {.columns}
::: {.column width="50%"}

### BI (softwares)

![Classical BI tools](https://information4all.com/wp-content/uploads/2018/08/bi-logos.jpg){width=50%}

:::
::: {.column width="50%"}

### Python (libraries)

![Python data vizualisation landscape](https://www.anaconda.com/wp-content/uploads/2019/01/PythonVisLandscape.jpg){width=60%}

:::
::::::::::::::

## Data Science and Machine Learning

![Machine Learning tools (Azure)](https://azurecomcdn.azureedge.net/cvt-4487a6447cf1bf91e230713a05f34bad0db35c4f6fcd9ef40ec213488bd18749/images/page/services/machine-learning/value-prop-4.png)

## Quizz

Which technology is the most representative of the Big Data world?

- Answer A: Spark
- Answer B: Elasticsearch
- Answer C: Hadoop
- Answer D: Tensorflow
- Answer E: MPI (Message Passing Interface)

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_701)

# Big Data use cases

## Cost effective storage and processing

- Commodity hardware (standard servers, disks and network)
- Horizontal scalability
- Proximity of Storage and Compute
- Secure storage (redundancy or Erasure Coding)

Use cases:

- Archiving
- Massive volume handling
- ETL (Extract Transform Load)

## Data mining, data value, data cross processing

Extract new knowledge and value from the data:

- Statistics,
- Find new Key Performance Indicators,
- Explain your data with no prior knowledge (Data Mining)

Cross analyse internal and external data, correlation:

- Trends with news or social network and correlation to sales
- Near real time updates with Stream processing

## Scientific data processing

Data production or scientific exploration:

- Stream processing, or near real time processing from sensor data
- Distributed processing of massive volume of incomming data on computing farm
- Data exploration and analysis
- Data Science

![Gaia: 150TB input, 6PB generated](images/GaiaPlatform.png){width=40%}
![Iota2: 20-40TB of input data](images/Iota2.png)

## Other main use cases

:::::::::::::: {.columns}
::: {.column width="50%"}

- Digital twins
- Predictive maintenance
- Smart City
- Real time processing

:::
::: {.column width="50%"}

![Airplane Digital Twin](https://www.prolim.com/wp-content/uploads/2019/08/digital-twin.jpg)

:::
::::::::::::::

## Quizz

What is the typical volumes of scientific Datasets (multiple choices)?

- Answer A: MBs
- Answer B: GBs
- Answer C: TBs
- Answer D: PBs
- Answer E: EBs

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_513)

# Big Data to Machine Learning

## Big Data ecosystm allows (part of) machine learning to be effective

- More data = more precise models
- Deep Learning difficult without large (optionnaly generated) input datasets
- Tools to collect, store, filter, index, structure data
- Tools to analyse and visualize data
- Real time model learning

https://blog.dataiku.com/when-and-when-not-to-use-deep-learning

## Pre processing before machine learning

- Data wrangling and exploration
- Feature engineering: unstructured data to input features
- Cross mutliple data sources
- Get insights on the data before processing it (statistics, vizualisation)

## Distribute datasets and algorithms

- For preprocessing as seen above
- Means to load and learn on large volumes by distributing storage
- Distributed learning with data locality on big datasets
- Distributed hyper parameter search

![Lambda Architecture (Azure)](https://docs.microsoft.com/fr-fr/azure/architecture/data-guide/big-data/images/big-data-pipeline.png){width=60%}

## Quizz

Is Big Data and Machine Learning the same?

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_311)

