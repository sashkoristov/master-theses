# Master theses topics (Supervisor: `Sashko Ristov`)
A repository for available, active and closed topics for master theses supervised by Sashko Ristov.

As a result of several bachelor and master theses that I supervised, we have developed a prototype of the *xAFCL* enactment engine, which is able to run serverless workflows or function choreographies (*FCs*) across many widely-known cloud providers. *xAFCL EE* integrates the component [FTjFaaS](https://github.com/sashkoristov/FTjFaaS) for optional fault tolerant execution of FC functions (currently supported AWS Lambda and IBM Cloud Functions) and [jFaaS](https://github.com/sashkoristov/jFaaS/) for portable execution across many FaaS systems (AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, Microsoft Azure Cloud Functions, etc).

*xAFCL EE* is the core part of the [AFCL Environment](https://github.com/sashkoristov/AFCLEnvironment), a platform to develop, deploy, and fault tolerant execution of FCs developed in our Abstract Function Choreography Language ([AFCL](https://doi.org/10.1016/j.future.2020.08.012)).

Moreover, the AFCL Environment architecture includes FaaSifiers, FCfiers and a automatic deployer.

The following paragraphs present the available and recently started topics for master theses directly connected with the AFCL Environment. It also presents the active and closed master theses. 

You can find a latex template for the master thesis which includes some hints [here](https://github.com/sashkoristov/master-theses/tree/main/template).


# Available master theses

* Tentative requirements analyses: January-February 2021
* Tentative start: February - April 2021
* Tentative finish: October 2021 - April 2022

The following three topics for master theses are available for the given period above.

## 1. *fTemplate*

| Title | ***fTemplate*: Agile development of serverless functions with portable function templates (*FTs*)** |
| ----- | ----- | 
| Description |  Porting a serverless function from one to another FaaS system is a complex task as it may require a huge development effort to rewrite all cloud services that the function uses. For example, a user may prefer the migrated function from IBM Cloud Functions to AWS Lambda to use AWS S3 rather than IBM Cloud Storage in order to reduce latency. This requires that the function developer should rewrite the function to use AWS S3 instead of IBM storage. The goal of this master thesis is to research methods to simplify the portability of serverless functions by developing a dependency aware faasifier that allows developers to develop “function templates” (*FTs*) with annotations, independently from FaaS systems. The student will explore and learn how to model cloud service types that an *FT* uses in order to abstract them from a FaaS system. Once an *FT* is developed, the faasifier will adapt the code of the *FT* into function implementations for the cloud FaaS providers where function implementations should be deployed and run. Finally, the deployer will deploy the function implementation on specific region of the selected FaaS system. *fTemplate* may be implemented for *FTs* in various programming languages (e.g., Java, Python, Node.js, etc.).
|Tentative tasks| 1. Create an “annotation schema” for *FTs* and cloud service types.<br> 2. Develop a convertor from an *FT* into a function implementation for various FaaS Systems (e.g. AWS, Google, IBM, Alibaba, Microsoft).<br> 3. Develop a deployer for function implementations for the cloud providers.<br> 4. Develop *FTs* and multiple function implementations and build an FC for a real-life application.<br> 5. Evaluate the system with real life applications and optimal selection of the proper function implementation.|
| Theoretical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Cloud Computing, Serverless. | 
|Practical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Java, Python, or Node.js; Cloud APIs.|
|References| 1. (`FaaSification annotation`) S. Ristov, S. Pedratscher, J. Wallnöfer, and T. Fahringer, “DAF: Dependency-Aware FaaSifier for Node.js Monolithic Applications,” in IEEE Software, doi: 10.1109/MS.2020.3018334, [DAF](https://github.com/qngapparat/daf).<br> 2. (`Portable invocation`) Middleware services to support workflow execution in a Multi-FaaS environment student: Jakob Wallnöfer, supervisor: Sashko Ristov, [js2faaS](https://github.com/qngapparat/js2faas), [java2faaS](https://github.com/qngapparat/java2faas), [X2FaaS](https://github.com/qngapparat/X2FaaS).<br> 3. (`Automatic function deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF).<br> 4. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 5. (`Node2FaaS Framework`) [Node2FaaS *FCifier*](https://github.com/node2faas/framework). | |
---


## 2. *DxAFCL*

| Title | ***DxAFCL*: Decentralized xAFCL ** |
| ----- | ----- | 
| Description | All widel-known serverless control-flow-based workflow management systems (FC systems) are centralized with "click-clack" approach, i.e., repeatedly running fetch input data, process and store output data. The aim of this master thesis is to develop a decentralized FC system which will distribute the xAFCL enactment engine across the available FaaS systems. The centralized xAFCL engine should chunk the FC into subFCs such that each of them will have an input, AFCL file and expected output. It is expected that this approach will minimize the latency and reduce the risk of a single point of failure. We will research both the synchronous and asynchronous approaches for decentralization.
|Tentative tasks| 1. Design a parser that will create subFCs out of the FC.<br> 2. Automatic deployment of distributed xAFCL across multiple cloud providers (e.g. VM, container, serverless function).<br> 3. Execution of experiments on multiple widely-known FaaS systems.<br> 4. Evaluation of *DxAFCL*.<br> 5. Monitoring and fault tolerance.|
| Theoretical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Cloud Computing, Serverless. | 
|Practical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Java, Cloud APIs.|
|References| 1. (jFaaS)[https://github.com/sashkoristov/jFaaS].<br> 2. (`Automatic function deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. Abstract Function Choreography Language ([AFCL paper](https://doi.org/10.1016/j.future.2020.08.012))], [AFCL git](https://github.com/sashkoristov/AFCL).| |
---



## 3. *AFCL-Sched*

| Title | ***AFCL-Sched*: Optimal execution of FCs across multiple FaaS systems** |
| ----- | ----- | 
| Description | The aim of this master thesis is to conduct a series of experiments to evaluate the properties and constraints of widely-known FaaS systems (e.g. AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, etc.). Numerous function implementations of serverless applications represented as functions choreographies (*FCs*) will be tested for various configurations (concurrency, assigned memory, latency, region, programming language, etc). The times for the functions and *FCs* are measured and then evaluated, which include: time until a function request is submitted and function is started, time for the execution of the function and the whole FC (with measurement of memory and CPU consumption), time to receive the response from the FaaS system, and much more. A large number of experiments are started. The measured data will be stored and then statistically evaluated and visualized. A special feature is the consideration of highly scalable FCs, which run e.g. tens of thousands functions. The evaluation may be triggered on-demand or after developing or deploying a function implementation. The aim of this work is a better understanding of serverless computing for different FCs and FaaS systems. The trade-off between performance and costs will be examined more closely. The applications are built with the existing AFCL language developed by the DPS group and run with the existing enactment engine. Based on the findings, a novel FaaS model will be developed. Finally, a multi-objective scheduler will be developed for optimal execution of FCs across multiple FaaS systems. The initial xAFCL FaaS model for parallel loops that we developed can be shared on demand. The student will be cordially invited as a co-author in a scientific paper based on this research work. 
|Tentative tasks| 1. Design a common data model for measurement data from various FaaS systems<br> 2. Develop scripts for parsing logs from FaaS systems and storing measurement data.<br> 3. Execution of experiments on multiple widely-known FaaS systems.<br> 4. Evaluation and visualization of the measured data.<br> 5. Develop a multi-objective scheduler for FC execution<br> 6. Automatic conversion of AFCL into intermediary representation (CFCL).|
| Theoretical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Cloud Computing, Serverless. | 
|Practical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Java, Cloud APIs.|
|References| 1. (jFaaS)[https://github.com/sashkoristov/jFaaS].<br> 2. (`Automatic function deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. (`Node2FaaS Framework`) [Node2FaaS *FCifier*](https://github.com/node2faas/framework).<br> 5. Abstract Function Choreography Language ([AFCL paper](https://doi.org/10.1016/j.future.2020.08.012))], [AFCL git](https://github.com/sashkoristov/AFCL).<br> 6. Enactment engine to run serverless workflows [xAFCL](https://github.com/sashkoristov/enactmentengine). | |
---


# Recently started master theses for the AFCL Environment (SS2021)

## 1.  *xFlow* (read CrossFlow)

| Title | ***xFlow*: Cross-layered resource management in Cloud continuum** |
| ----- | ----- | 
| Student | Ahmet Aspir | 
| Status | Requirements analysis | 
| Description | Cloud continuum offers a variety of heterogeneous computing resources, each with specific properties in terms of scalability, latency, performance, capacity, provisioning delay, economic costs, flexibility, portability, etc. For example, VMs are cheaper and more flexible, but with much higher provisioning delay compared to serverless functions. Many of the existing computing engines use resources of a single Cloud provider or of a single resource type, which locks the user with their pros and cons. This thesis will research methods to develop CrossFlow, a scalable and portable platform to run complex applications across various types of cloud continuum resources. This will allow the user to obtain maximum features of each resource type. The applications are built with the existing AFCL language developed by the DPS group and run with the existing enactment engine for serverless applications, which should be extended for cross-layered resources.
|Tasks| 1. Analyze the existing languages for “infrastructure as code”<br>. 2. Develop an abstract and cross-layered language for cloud resources (which will support the master thesis “*fTemplates*”)<br> 3. Develop a fault-tolerant resource manager for recommendation, provisioning, monitoring, accounting, billing, and terminating of cross-layered cloud continuum resources<br> 4. Evaluate the system (cost-performance trade-off) with real life applications.|
| Theoretical skills |  2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Cloud Computing, Serverless. | 
|Practical skills | 2020W703832 VU Distributed Applications in the Edge-Cloud Continuum, Cloud APIs, Java.|
|References| 1. S. Ristov, S. Pedratscher, T. Fahringer, “AFCL: An Abstract Function Choreography Language for serverless workflow specification,” Future Generation Computer Systems, Volume 114, 2021, Pages 368-382, ISSN 0167-739X, https://doi.org/10.1016/j.future.2020.08.012.<br> 2. Enactment engine to run serverless workflows [xAFCL](https://github.com/sashkoristov/enactmentengine).<br> 3. A multi-FaaS toolkit for portable execution of serverless functions [jFaaS](https://github.com/sashkoristov/jFaaS)| |
---


# Active master theses

1. "AFCL Environment – Development and Scalable Execution of Portable Function Choreographies Across Multiple Serverless Cloud Platforms", Stefan Pedratscher. Status - Advanced development.

Details for active master theses can be found [here](./blob/main/active/readme.md).


# Closed master theses

1. "VolatileSim: A simulation framework for cloud volatile resources", Christoph Schöpf, SS2020, `Among top four master theses for 2020` at the institute
1. "Distributed GPGPU on Cloud GPU Clusters", Martin Schuchardt, SS2019


Details for closed master theses can be found [here](./blob/main/closed/readme.md).



----

# Contact

If you need any additional information, please do not hesitate to contact me on sashko@dps.uibk.ac.at. 

My topics for bachelor theses may be found [here](https://github.com/sashkoristov/bachelor-theses).