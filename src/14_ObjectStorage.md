---
title: Object Storage and Cloud Optimized Datasets
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2022-04-26
---

# Object Storage

## Object Storage concepts

> Object storage is a computer data storage that manages data as objects, as opposed to other storage architectures like file systems which manages data as a file hierarchy, and block storage which manages data as blocks within sectors and tracks. 
> Each object typically includes the data itself, a variable amount of metadata, and a globally unique identifier. (Wikipedia)

But Why?

- Scalability. Scale-out, infinitly. 
- Security/Reliability/Availability. Erasure Coding.
- Cost. Commodity hardware.
- Performance (bandwith). Just need good network, and scale.

## POSIX vs Object Storage

![](https://blog.scaleway.com/content/images/2019/12/schema_storage.svg)

## Object store Architecture

![](https://www.glennklockwood.com/data-intensive/storage/object-store-schematic.png)

## Ceph @CNES

![](images/Ceph-CNES.png)

## Quizz

What makes object storage efficient? (multiple choices)

- Answer A: The use of high-end and complex harware for storage solutions
- Answer B: The multiplication of standard servers with JBOD storage
- Answer C: High performance network
- Answer D: POSIX API
- Answer E: Dedicated API developed for simple transactions

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_716) _Key: hl_

# Processing and Cloud Optimized datasets

## Object storage interface and libraries

- Just HTTP Rest Calls: GET, PUT
- With authentification and authorizations: Access key and secret access key.
- Easier with AWS CLI or alike:

```bash
# Needs a keys file in your $HOME dir, or to dynamically obtain a key
aws s3 cp /tmp/foo/ s3://bucket/ --recursive --exclude "*" --include "*.jpg"
```

Interfaces and libraries for major programming languages:

- [Boto3 for Python](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html): not just S3, all AWS services
- Higher level for Python: [s3fs: Pythonic file interface for S3](https://s3fs.readthedocs.io/en/latest/)
- Other languages:
  - [Java SDK](https://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/services/s3/AmazonS3.html)
  - [C++ SDK](https://aws.amazon.com/fr/sdk-for-cpp/)
- Other Object storage interfaces:
  - [Google Cloud Storage](https://cloud.google.com/storage/docs/reference/libraries)
  - [Azure Blob Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-directory-file-acl-python)

## Processing framework and Object store

All Major Data processing framework are compatible with S3 like interfaces.

- [Pandas dataframes](https://pandas.pydata.org/docs/user_guide/io.html)
- [Spark](https://spark.apache.org/docs/latest/cloud-integration.html)
- [Dask](https://docs.dask.org/en/stable/how-to/connect-to-remote-data.html)

Just replace */* or *file://* by *s3://*.

```python
import dask.dataframe as dd
df = dd.read_csv('s3://bucket/path/to/data-*.csv')
df = dd.read_parquet('gcs://bucket/path/to/data-*.parq')
```

More on the next part of the course.

## ARCO Data

**A**nalysis **R**eady **C**loud **O**ptimized Data.

Thanks to Ryan Abernathey.

:::::::::::::: {.columns}
::: {.column width="50%"}

What is Analysis Ready?

- Think in Datasets, not data files
- No need for tedious homogenizing, cleaning steps
- Curated and cataloged

:::
::: {.column width="50%"}

![How do data scientists spend their time (Crowdflower Data Science Report, 2016)](images/What-data-scientists-spend-the-most-time-doing-7.ppm.png)

:::
::::::::::::::

## ARCO Data (2)

**A**nalysis **R**eady **C**loud **O**ptimized Data.

Thanks to Ryan Abernathey.

:::::::::::::: {.columns}
::: {.column width="50%"}

What is Cloud Optimized?

- Compatible with object storage (access via HTTP)
- Support lazy access and intelligent subsetting
- Integrates with high-level analysis libraries and distributed frameworks

:::
::: {.column width="50%"}

![](images/ARCOData.png)

:::
::::::::::::::

## Cloud Optimized Geotiff

## Zarr

## Parquet

## See more

Cloud outreach link
https://www.youtube.com/playlist?list=PLQsQNjNIDU87yUFyKy1seaiRps389RPwk


## Quizz

What allows container orchestration (multiple choices)?

- Answer A: Auto scaling of services
- Answer B: Making coffee
- Answer C: Ensuring container states and availability
- Answer D: Submitting finite jobs

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_922) _Key: hy_
