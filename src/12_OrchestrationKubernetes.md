---
title: Containers Orchestration, Kubernetes
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-16
---

# Credits and thanks

## Didn't do this

Thanks to [Florient Chouteau](mailto:florient.f.chouteau@airbus.com) and [Dennis Wilson](mailto:Dennis.WILSON@isae-supaero.fr)

for their work on this subject.

I took most of the content from theirs:

- [https://supaerodatascience.github.io/OBD/slides/1_5_orchestration.html](https://supaerodatascience.github.io/OBD/slides/1_5_orchestration.html)
- [https://supaerodatascience.github.io/OBD/slides/2_3_kubernetes.html#/](https://supaerodatascience.github.io/OBD/slides/2_3_kubernetes.html#/)

# Kubernetes

## Why orchestration?

Suppose I have a large pool of machines available

* How do I **deploy my container**?
* How do I **put the right containers at the right spot**?
* How do I **scale (up and down) to demand**?
* How do I **expose the http endpoints**?
* How do I **manage failure of containers**?
* How do I **update my model without downtime**?

## Tools example

:::::::::::::: {.columns}
::: {.column width="40%"}

Examples...

- Docker Swarm
- CoreOS Fleet
- [Apache Mesos](https://mesos.apache.org/) / [Marathon](https://github.com/mesosphere/marathon)

... and so many more !

:::
::: {.column width="60%"}

![ecosystem](https://img1.daumcdn.net/thumb/R800x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F996C7D4B5AF43B6C27)

:::
::::::::::::::

## Short Kubernetes history

Kubernetes (or k8s) comes from Google's internal systems [Borg](https://github.com/SupaeroDataScience/OBD/blob/master/readings/borg.pdf)

It is open source now <https://github.com/kubernetes> and used... everywhere ?

## Thanks to Dennis for the next part

[Slides](https://supaerodatascience.github.io/OBD/slides/2_3_kubernetes.html#/)

## Quizz

What allows container orchestration (multiple choices)?

- Answer A: Auto scaling of services
- Answer B: Making coffee
- Answer C: Ensuring container states and availability
- Answer D: Submitting finite jobs

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_922) _Key: hy_


# Processing platform on Kubernetes

## Kubeflow

[https://www.kubeflow.org/](https://www.kubeflow.org/)

![kubeflow](https://miro.medium.com/max/2446/1*ZQsFV3o1c3Amu26Z-IEd7w.png){width=55%}

## Jupyterhub/Binder

![](https://miro.medium.com/max/1400/1*F_jJ1nDSQgBhrkbsEXB93Q.png){width=70%}

## Databricks: Spark as a Service

![](https://docs.gcp.databricks.com/_images/databricks-architecture-gcp.png){width=40%}

## Coiled: Dask as a Service

![](images/Coiled.png)


## Quizz

How do you deploy containers through Kubernetes (mutliple choices)?

- Answer A: docker run
- Answer B: Helm charts and command
- Answer C: yaml configuration and kubectl
- Answer D: custom bash script

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_551) _Key: ju_

# Kubernetes tutorial

## Try some

[https://training.play-with-kubernetes.com/kubernetes-workshop/](https://training.play-with-kubernetes.com/kubernetes-workshop/)

[https://labs.play-with-k8s.com/](https://labs.play-with-k8s.com/) with [Voting App](https://training.play-with-docker.com/swarm-stack-intro/)
