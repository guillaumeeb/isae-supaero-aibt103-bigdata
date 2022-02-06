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

[Answer link](https://toreply.univ-lille.fr/reponse_968) _Key: lu_

## Quizz

Cite some V's of Big Data (multiple choices):

- Answer A: Validation
- Answer B: Volume
- Answer C: Velocity
- Answer D: Voldemort
- Answer E: Variety

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_132) _Key: eb_

# Legacy “Big Data” ecosystem

## Blowing ecosystem{background-image=https://external-preview.redd.it/P6JcS17ECpmFF2si8KVnuoKpiabc5-pWTmgRt_YxTx4.png?auto=webp&s=3cbdbbe95112b6d6f5fb0bb59f6421b8e8be999e}

## Hadoop & Map Reduce

![Hadoop ecosystem](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2016/10/HADOOP-ECOSYSTEM-Edureka.png)

## NoSQL (Not only SQL)

:::::::::::::: {.columns}
::: {.column width="50%"}

![SQL vs NoSQL databases model (altitudetvm)](https://altitudetvm.com/images/komputer/apa-itu-nosql-berikut-ini-pengertian-nosql-beserta-kelebihannya_2.png){width=50%}

:::
::: {.column width="50%"}

![Popular NoSQL Databases](https://miro.medium.com/max/800/1*Sz73n23vbZ_Gtsx2FU3Otg.jpeg)

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

![Python data vizualisation landscape](https://rougier.github.io/python-visualization-landscape/landscape-colors.png){width=60%}

:::
::::::::::::::

## Data Science and Machine Learning

![Machine Learning tools (Azure)](https://i1.wp.com/neptune.ai/wp-content/uploads/MLOps-platforms-azure-2.png?resize=1024%2C578&ssl=1)

## Quizz

Which technology is the most representative of the Big Data world?

- Answer A: Spark
- Answer B: Elasticsearch
- Answer C: Hadoop
- Answer D: Tensorflow
- Answer E: MPI (Message Passing Interface)

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_326) _Key: qm_

# Big Data use cases

## Typical Dataset (originally)

Huge amount of small objects:

- Billions of records
- KB to MB range

Think of:

- Web pages, and words into it
- Tweets
- Text files, where each line is a record
- IoT and everyday life sensors: a record per second, minute or hour.

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

Cross analysis of internal and external data, correlations:

- Trends with news or social network stream and correlation to sales
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

[Answer link](https://toreply.univ-lille.fr/reponse_263) _Key: mn_

# Big Data to Machine Learning

## Big Data ecosystem allows (part of) machine learning to be effective

- More data = more precise models
- Deep Learning difficult without large (possibly generated) input datasets
- Tools to collect, store, filter, index, structure data
- Tools to analyse and visualize data
- Real time model learning

[https://blog.dataiku.com/when-and-when-not-to-use-deep-learning](https://blog.dataiku.com/when-and-when-not-to-use-deep-learning)

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

[Answer link](https://toreply.univ-lille.fr/reponse_525) _Key: vm_

