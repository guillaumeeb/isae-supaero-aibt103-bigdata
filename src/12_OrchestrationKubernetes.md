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

[Answer link](https://toreply.univ-lille.fr/reponse_108)


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

[Answer link](https://toreply.univ-lille.fr/reponse_651)

# Kubernetes tutorial

## Try some

[https://training.play-with-kubernetes.com/kubernetes-workshop/](https://training.play-with-kubernetes.com/kubernetes-workshop/)

[https://labs.play-with-k8s.com/](https://labs.play-with-k8s.com/) with [Voting App](https://training.play-with-docker.com/swarm-stack-intro/)
