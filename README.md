# Master theses topics (Supervisor: `Sashko Ristov`)
A repository for available, active and closed topics for master theses supervised by Sashko Ristov.

As a result of several bachelor and master theses that I supervised, we have developed a prototype of the *xAFCL* enactment engine, which is able to run serverless workflows or function choreographies (*FCs*) across many widely-known cloud providers. *xAFCL EE* integrates the component [FTjFaaS](https://github.com/sashkoristov/FTjFaaS) for optional fault tolerant execution of FC functions (currently supported AWS Lambda and IBM Cloud Functions) and [jFaaS](https://github.com/sashkoristov/jFaaS/) for portable execution across many FaaS systems (AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, Microsoft Azure Cloud Functions, etc).

*xAFCL EE* is the core part of the [AFCL Environment](https://github.com/sashkoristov/AFCLEnvironment), a platform to develop, deploy, and fault tolerant execution of FCs developed in our Abstract Function Choreography Language ([AFCL](https://doi.org/10.1016/j.future.2020.08.012)).

Moreover, the AFCL Environment architecture includes FaaSifiers, FCfiers and a automatic deployer.

The following paragraphs present the available and recently started topics for master theses directly connected with the AFCL Environment. It also presents the active and closed master theses. 

You can find a latex template for the master thesis which includes some hints [here](https://github.com/sashkoristov/master-theses/tree/main/template).

Milestones for a successful master thesis:
- Requirements analysis
- Review the related work
- System architecture
- Development
- Evaluation
- Finalizing the master thesis
- Defensio
- `Farewell party` :blush:

# Available master theses

* Tentative requirements analyses January-March 2022
* Tentative start March-April 2022
* Tentative finish October-December 2022

The following topics for master theses are available for the summer semester 2022.

Will be published soon!


# Recently started master theses for the AFCL Environment (SS2021)


## *AFCL-Sched*

| Title | ***AFCL-Sched*: Optimal execution of FCs across multiple FaaS systems** |
| ----- | ----- | 
| Student | Christian Hollaus | 
| Status | Evaluation | 
| Description | The aim of this master thesis is to conduct a series of experiments to evaluate the properties and constraints of widely-known FaaS systems (e.g. AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, etc.). Based on the findings, a multi-objective scheduler will be developed for optimal execution of FCs across multiple FaaS systems.| |
---


##  *CrossFlow*

| Title | ***CrossFlow*: Cross-layered resource management in Cloud continuum** |
| ----- | ----- | 
| Student | Ahmet Aspir | 
| Status | Development | 
| Description | This thesis will research methods to develop CrossFlow, a federated platform to maange various types of resources in the cloud continuum.| |
---


# Closed master theses

1. "AFCL Environment – Development and Scalable Execution of Portable Function Choreographies Across Multiple Serverless Cloud Platforms", Stefan Pedratscher, SS2021 [details](./closed/AFCLEnvironment.md).
1. "VolatileSim: A simulation framework for cloud volatile resources", Christoph Schöpf, SS2020, `Among top four master theses for 2020` at the institute.
1. "Distributed GPGPU on Cloud GPU Clusters", Martin Schuchardt, SS2019.


Details for closed master theses can be found [here](./closed/README.md).



----

# Contact

If you need any additional information, please do not hesitate to contact me. 

My topics for bachelor theses may be found [here](https://github.com/sashkoristov/bachelor-theses).