---
title: Introduction to Cloud Computing
author: Guillaume Eynard-Bontemps, CNES (Centre National d'Etudes Spatiales - French Space Agency)
date: 2020-11-16
---

# Credits and thanks

## Didn't do this

Thanks to [Florient Chouteau](mailto:florient.f.chouteau@airbus.com) and [Dennis Wilson](mailto:Dennis.WILSON@isae-supaero.fr)

for their work on this subject.

I took most of the content from theirs: 

- [https://supaerodatascience.github.io/OBD/1_1_overview.html](https://supaerodatascience.github.io/OBD/1_1_overview.html)
- [https://supaerodatascience.github.io/OBD/slides/1_1_cloud_computing.html](https://supaerodatascience.github.io/OBD/slides/1_1_cloud_computing.html)
- [https://supaerodatascience.github.io/OBD/slides/1_2_cloud_usage.html](https://supaerodatascience.github.io/OBD/slides/1_2_cloud_usage.html)
- [https://supaerodatascience.github.io/OBD/slides/1_3_gcp.html](https://supaerodatascience.github.io/OBD/slides/1_3_gcp.html)

# What is the Cloud?

## 

![](https://nerds.net/wp-content/uploads/2018/02/cloud-computer-reality-750x646.jpg)

## But it's a bit bigger... 

:::::::::::::: {.columns}
::: {.column width="30%"}

![](https://supaerodatascience.github.io/OBD/slides/static/img/fb_datacenter.jpg)

:::
::: {.column width="70%"}

![](https://www.datacenterknowledge.com/sites/datacenterknowledge.com/files/wp-content/uploads/2013/06/lulea-rows.jpg){width="35%"}
![](https://www.datacenterknowledge.com/sites/datacenterknowledge.com/files/wp-content/uploads/2013/06/fb-lulea-external-fans.jpg){width="35%"}

![](https://cdn.arstechnica.net/wp-content/uploads/2013/02/openrack2-640x426.jpg){width="35%"}
![](https://engineering.fb.com/wp-content/uploads/2015/05/GM23qAAlFJW8xm4BABnMiwAAAAAAbj0JAAAD.png){width="35%"}

(Facebook's data center & server racks)

:::
::::::::::::::

## Google Cloud Data Center locations

![Data Centers](https://cloud.google.com/images/locations/regions.png)

## Cloud Definition

> The cloud is a real physical place - accessed over the internet - where a service is performed for you or where your stuff is stored. Your stuff is stored in the cloud, not on your device because the cloud is not on any device; the cloud lives in datacenters. A program running on your device accesses the cloud over the internet. The cloud is infinite, accessible from anywhere, at any time

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

## A portion of AWS services{background-image=https://www.matthewb.id.au/cloud/images/AWS-Services.png data-background-size=contains}

## Quizz

What's the Cloud?

- Answer A: Still don't know...
- Answer B: A magic place where my photos and likes are
- Answer C: Someone else computer
- Answer D: Several big Data centers around the world that host data and service

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_631)

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

- **Hypervisor** (VMWare, Virtualbox, KVM): A hypervisor is a program for creating and running virtual machines
- **Virtual Machine**: A virtual machine is the emulated equivalent of a computer system that runs on top of another system
- **Containers**: Isolated environments that share the same underlying OS (more this afternoon) & resources

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

## Quizz

Virtualization allows... (multiple choices)

- Answer A: Hardware abstraction, download a machine with more ram
- Answer B: Resources sharing optimization
- Answer C: Building immersive video games
- Answer D: Reliability
- Answer E: Reproducibility

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_710)

# Cloud history

## AWS

Once upon a time...

Amazon (the e-commerce store) has "scaling" issues

![](https://cdn.chiefmartec.com/wp-content/uploads/2016/11/jeff_bezos_big_mandate.jpg)

## Idea

2002-2003; The idea

> Building an infrastructure that is completely standardized, completely automated, and relied extensively on web services for things like storage 

[http://blog.b3k.us/2009/01/25/ec2-origins.html](http://blog.b3k.us/2009/01/25/ec2-origins.html)

## So ...

Basically Amazon became very good at *running* scalable infrastructure as *services*

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

- Using data storage service like google cloud storage without managing the infrastructure ?aaS
- Using google drive ?aaS
- Renting a server with hard drive and storing data ?aaS


. . . 


- Using data storage service like google cloud storage without managing the infrastructure **PaaS**
- Using google drive **SaaS**
- Renting a server with hard drive and storing data **IaaS**

## Quizz

What means IaaS?

- Answer A: I am a Sociopath
- Answer B: Information as a System
- Answer C: Information as a Service
- Answer D: Infrastructure as a Service

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_526)

# Cloud Engines

## Public

![Cloud Vendors](https://yogeek.github.io/enseignement/Introduction_Virtualisation_CloudComputing/img/cloud_vendors.jpg)

## Public (European)

![](https://www.comptoir-hardware.com/images/stories/_logos/ovhcloud.png){width=20%}
![](https://cloud.orange.com/ui/app/static/assets/brand/logo_header_login.png){width=20%}
![](https://open-telekom-cloud.com/resource/blob/data/594220/5aa8c4c54f7a8b90fe1256f26948fbe7/open-telekom-cloud-tsystems-logo.png){width=20%}

Academic, public founded:

![gaiax](https://www.data-infrastructure.eu/GAIAX/Redaktion/EN/Bilder/gaia-x.jpg?__blob=normal&v=1&size=834w){width=20%}
![EOSC](https://eosc-portal.eu/sites/all/themes/theme1/logo.png){width=20%}

## Private/on premise

![](http://1.bp.blogspot.com/-1BuI8MUh498/Uc4BOPBpChI/AAAAAAAAGjk/XWA0iYO5drA/s1028/Screen+Shot+2013-06-28+at+12.03.11+PM.png)

## Leaders

![](https://cdn.statcdn.com/Infographic/images/normal/18819.jpeg){width=50%}

## In France

![](https://i2.wp.com/datacenter-magazine.fr/contenus/uploads/2020/03/CORE_MARKESS_PRG_OPE_19-20_COMPETITIVE_ENVIRONMENT_PRESSE_MARS-2020.png?resize=600%2C340&ssl=1)

# Cloud computing: usage revolution

## A technical evolution

- More Virtualization
- More API
- More Managed Services

## Access and operating computing power

- Outsourcing infra, maintenance, security, development of new services
  - Less (?) operation cost (or at least less burden)
- Pay-per-use, pay as you go, change of economical model
- "Infinitely scalable" for common folks
- "No need to plan out" infrastructure
  - Enabling innovation
  - Power in the hands of developpers/builders

## Technical benefits

- Infrastructure as Code
- Continuous Deployment
- Infinite resources
- On demand scalability and resources

## Changing the way we interact with hardware

We interact with cloud providers using APIs...

```bash
gcloud compute --project=deeplearningsps instances create ${INSTANCE_NAME} \
    --zone=${ZONE} \
    --machine-type=n1-standard-8 \
    --scopes=default,storage-rw,compute-rw \
    --maintenance-policy=TERMINATE \
    --image-family=ubuntu-1804-lts \
    --image-project=ubuntu-os-cloud \
    --boot-disk-size=200GB \
    --boot-disk-type=pd-standard \
    --accelerator=type=nvidia-tesla-p100,count=1 \
    --metadata-from-file startup-script=startup_script.sh
```

## Infrastructure as Code

- Infrastructure is now managed via text files
- Data is securely stored on storage
- So we store code + urls on git... and everything is reproducible ! (not _that_ simple)
- We use automated deployment tools (terraform, gcp deployment manager...)

## Pet vs Cattle

![](https://blog.octo.com/wp-content/uploads/2016/12/image01-e1482225268205-1024x827.png)
![](https://blog.octo.com/wp-content/uploads/2019/07/pet_vs-cattle-1024x636.png)

## Quizz

Why Cloud computing is a usage revolution (multiple choices)?

- Answer A: Infinite resources (CPU, memory, storage)
- Answer B: It's cheaper
- Answer C: Infrastructure managed as Code
- Answer D: Pay per use
- Answer E: It gives all our data to Google and Amazon

![Answer](data:image/png;base64,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)

[Answer link](https://toreply.univ-lille.fr/reponse_983)

# New Data Processing standard

## Object store

High througput storage system with horizontal scalability

![](images/FileStorage.png)
![](images/ObjectStorage.png)

## Compute as a service

- Start and stop compute resources when needed
  - IaC tools like Terraform, Ansible
  - Mesos/Nomad and other tools.
- Kubernetes as a Service
  - With autoscaling features: add VMs if needed
  - Dask, Spark and other processing tools plugged in
- Function as a Service
  - Just put a bit of code, everything else is handled.
- HPC as a Service
  - With POSIX filesystem (sometimes over Object store)
  - And high performance network.

# Discussions and Troll

## Is using cloud computing less expensive?

- ![+1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44d.svg){height=20px} Depend on your {normal / peak} utilization
- ![+1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44d.svg){height=20px} Access to latest hardware without investment
- ![-1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44e.svg){height=20px} Fully utilized hardware is more expensive on the cloud
- ![-1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44e.svg){height=20px} CLOUD HYGIENE !
  - Watch for unused services / storage
  - Shutdown machines when not used
  - Services stack up...

## Is using cloud computing more secure / safer.

- ![+1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44d.svg){height=20px} The best engineers in the world working on it
- ![+1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44d.svg){height=20px} Secure regions / private cloud...
- ![-1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44e.svg){height=20px} Your data somewhere in some datacenter...
- ![-1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44e.svg){height=20px} "Dependency" towards your cloud provider...
- ![-1](https://github.com/twitter/twemoji/blob/master/assets/svg/1f44e.svg){height=20px} Still need to handle security inside you resources

![OVHCloud burning](https://cdn.searchenginejournal.com/wp-content/uploads/2021/03/fire-ovh-data-center-60488d3b150d6-760x400.jpg)

# Google Cloud Platform

## Presentation

- One of the main cloud provider
- Behind AWS in SaaS (serverless...)
- More "readable" product line (for a Cloud Provider...)
- Very good "virtual machine" management  
  * per second billing
  * fine-grained resource allocation

## Services

![](https://static.packt-cdn.com/products/9781788837675/graphics/ee72c164-888d-4cec-b3f9-efd3b8e8e4cb.png)

## {background-image=https://raw.githubusercontent.com/gregsramblings/google-cloud-4-words/master/Poster-medres.png}

## Concepts: Zones and regions

![](https://cloud.google.com/docs/images/overview/regions-zones.svg)

## Concepts: Projects

![](https://cloud.google.com/docs/images/overview/console-ids.png)

- Access (Enabling API/Services)
- Ressources (Quota by project)
- Networking
- Billing

## Concepts: Identity and Access Management (IAM)

![IAM](https://miro.medium.com/max/638/0*kGyUfNWZCk78hmPU.)

## Interacting with GCP: The Console

![https://console.cloud.google.com](https://cloud.google.com/docs/images/overview/console.png){width=60%}

## Interacting with GCP: SDK & Cloud Shell

- Using the gcloud CLI: [https://cloud.google.com/sdk/install](https://cloud.google.com/sdk/install)
- Using Google Cloud Shell: A small VM instance you can connect to with your browser

# First interaction with Google Cloud (Exercise)

## Objectives

Everyone has its credits/coupons?

- Create your GCP account, configure your credentials, ensure everything is working
- With the coupons you got, you should see $50 of credits (in the billing tab)
- Interact with Google cloud console: check all the services
- Start a first VM instance through the console, watch prices and all the options
- Create a Google Storage bucket and upload content
- Connect to google cloud shell and interact with it
- Follow [this Google codelabs](https://codelabs.developers.google.com/codelabs/cloud-compute-engine#2) to deploy a Website!

We'll do more this afternoon!
