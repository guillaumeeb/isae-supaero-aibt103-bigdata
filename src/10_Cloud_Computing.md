---
title: Introduction to Cloud Computing
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-16
---

# Credits and thanks

## Didn't do this

Thanks to [Florient Chouteau](florient.f.chouteau@airbus.com>) and Dennis Wilson 

for their work on this subject.

I took most of the content [from theirs](https://supaerodatascience.github.io/OBD/1_1_overview.html).

# What is the Cloud?

## {background-image=https://nerds.net/wp-content/uploads/2018/02/cloud-computer-reality-750x646.jpg}

## But it's a bit bigger...

<img src="static/img/fb_datacenter.jpg" alt="" width="30%" height="30%" style="background:none; border:none; box-shadow:none; float:left;margin:0 10px 0 20px;"/>

<img src="https://www.datacenterknowledge.com/sites/datacenterknowledge.com/files/wp-content/uploads/2013/06/lulea-rows.jpg" alt="" width="25%" height="25%" style="background:none; border:none; box-shadow:none;"/>

<img src="https://www.datacenterknowledge.com/sites/datacenterknowledge.com/files/wp-content/uploads/2013/06/fb-lulea-external-fans.jpg" alt="" width="25%" height="25%" style="background:none; border:none; box-shadow:none;"/>

<img src="https://cdn.arstechnica.net/wp-content/uploads/2013/02/openrack2-640x426.jpg" alt="" width="25%" height="25%" style="background:none; border:none; box-shadow:none;"/>

<img src="https://engineering.fb.com/wp-content/uploads/2015/05/GM23qAAlFJW8xm4BABnMiwAAAAAAbj0JAAAD.png" alt="" width="25%" height="25%" style="background:none; border:none; box-shadow:none;"/>

(Facebook's data center & server racks)

## Google Cloud Data Center locations

![Data Centers](https://cloud.google.com/images/locations/regions.png)

## Cloud Definition

> The cloud is a real physical place - accessed over the internet - where a service is performed for you or where your stuff is stored. Your stuff is stoed in the cloud, not on your device because the cloud is not on any device; the cloud lives in datacenters. A program running on your device accesses the cloud over the internet. The cloud is infinite, accessible from anywhere, at any time

Todd Hoff in "Explain the Cloud like I'm 10"

## Cloud Computing

Using cloud resources for any purpose, web server, storage, computations.

- The cloud is a set of **cloud providers**
- Renting cloud **services**
- Increasingly **abstracted** from the physical hardware

. . .

Examples:

- "Renting a server" ... (this is pure "cloud computing")
- "Replicated & Secure storage space"
- "Autoscaling deployment of a microservice"

## A portion of AWS services

![](https://www.matthewb.id.au/cloud/images/AWS-Services.png){width=70%}

## How?

# Virtualization

## Definition

> In computing, virtualization refers to the act of creating a virtual (rather than actual) version of something, including virtual computer hardware platforms, storage devices, and computer network resources.

Wikipedia

> Basically we are running software on "abstract hardware" which is a "portion" of a real computer ("bare metal")

## Desktop virtualization

![](https://www.unixtutorial.org/images/posts/Hardware-Virtualization-Desktop-Virtualization-Example.png){width=75%}

## Server virtualization

![](https://www.researchgate.net/profile/Bashir-Mohammed-2/publication/269636339/figure/fig1/AS:295113902313473@1447372045341/illustration-of-the-concept-of-Virtualization-7.png)

## Virtualization evolution

![](https://miro.medium.com/max/10698/1*wE7TrQmFyRTDwh6VpbkbMQ.png)

## Definitions

- Hypervisor (VMWare, Virtualbox, KVM): A hypervisor is a program for creating and running virtual machines
- Virtual Machine: A virtual machine is the emulated equivalent of a computer system that runs on top of another system
- Containers: Isolated environments that share the same underlying OS (more this afternoon) & resources

## Opens up new possibilities

:::::::::::::: {.columns}
::: {.column width="50%"}

### Hardware abstraction

- Hardware Abstraction ("download more RAM")
- Fine-grained resource allocation / sharing
- Decouple maintenance of hardware from maintenance of software

:::
::: {.column width="50%"}

### Reliability, security...

![balancing](https://yogeek.github.io/enseignement/Introduction_Virtualisation_CloudComputing/img/vm_charge_repartition.gif)

:::
::::::::::::::

# Cloud history

## AWS

Once upon a time...

Amazon (the e-commerce store) has "scaling" issues

![](https://cdn.chiefmartec.com/wp-content/uploads/2016/11/jeff_bezos_big_mandate.jpg)

## Idea

2002-2003; The idea

> Building an infrastructure that is completely standardized, completely automated, and relied extensively on web services for things like storage 

http://blog.b3k.us/2009/01/25/ec2-origins.html

## So ...

So basically Amazon became very good at *running* scalable infrastructure as *services*

- For themselves...
- ... but also for other partners (target)

And that infrastructure is often there to answer peak load...

## Let's sell it !

![](https://fchouteau.github.io/isae-practical-gcp/static/img/ec2.png)

# The many layers of Cloud Computing

## Public, hybrid, private

![From Padok](https://lh5.googleusercontent.com/e-i1nyv49RP3F3ZCHSepEZ4k_qYhqqgk496wDcsOkHLBbaT7deOuXi3AxesN6LNbQMWXJreOzRqpRbUkNgpFMhX8oxQvbAzAsIi8DObI9xWwq0d5lUfZmAlSbJf5ry-Vmto7i2JL){width=50%}

## Different layers of abstractions

![From pakt](https://static.packt-cdn.com/products/9781789538519/graphics/faf54214-c5e7-4cc4-9594-9cf06dacc923.png)

## Abstraction examples

- Using data storage service like google cloud storage without managing the infrastructure
- Using google drive
- Renting a server with hard drive and storing data

. . . 

- Using data storage service like google cloud storage without managing the infrastructure **PaaS**
- Using google drive **SaaS**
- Renting a server with hard drive and storing data **IaaS**

# Cloud Engines

## Public

![Cloud Vendors](https://yogeek.github.io/enseignement/Introduction_Virtualisation_CloudComputing/img/cloud_vendors.jpg)

## Public (European)

![](https://www.comptoir-hardware.com/images/stories/_logos/ovhcloud.png)

![](https://cloud.orange.com/ui/app/static/assets/brand/logo_header_login.png)

![](https://open-telekom-cloud.com/resource/blob/data/594220/5aa8c4c54f7a8b90fe1256f26948fbe7/open-telekom-cloud-tsystems-logo.png)

Academic, public founded:

![gaiax](https://www.data-infrastructure.eu/GAIAX/Redaktion/EN/Bilder/gaia-x.jpg?__blob=normal&v=1&size=834w)

![EOSC](https://eosc-portal.eu/sites/all/themes/theme1/logo.png)

## Private/on premise

![](http://1.bp.blogspot.com/-1BuI8MUh498/Uc4BOPBpChI/AAAAAAAAGjk/XWA0iYO5drA/s1028/Screen+Shot+2013-06-28+at+12.03.11+PM.png)

## Leaders

![](https://cdn.statcdn.com/Infographic/images/normal/18819.jpeg)

## In France

![](https://i2.wp.com/datacenter-magazine.fr/contenus/uploads/2020/03/CORE_MARKESS_PRG_OPE_19-20_COMPETITIVE_ENVIRONMENT_PRESSE_MARS-2020.png?resize=600%2C340&ssl=1)

# Old slides

## Different approaches

IaaS, PaaS, CaaS, SaaS, Object Storage

## Economical models, Pay as you go

## Technical benefits

Infrastructure as Code, Continuous Deployment, Infinite resources, scalability

## Cloud engines
Google, AWS, OVH, Openstack

# New Data processing standard

## Object store vs posix file system

## Compute as a service

Using K8S or not.

# First interaction with Google Cloud

## TP Google Cloud

Everyone has its credits?

how to get a server? 

TP through Google console, account, princing, ressources… VMs and Kubernetes
