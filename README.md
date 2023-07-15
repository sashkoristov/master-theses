# Master theses topics (Supervisor: `Sashko Ristov`)
A repository for available, active and closed topics for master theses supervised by Sashko Ristov.

Master theses topics are closely related with my current research areas:

- Cloud computing 
    - serverless computing and federated FaaS
    - modeling and simulation 
    - interoperability, portability, and federation
    - scheduling workflow applications
- Energy efficiency with cloud-based applications
    - Digital twins (Azure Twins, AWS IoT TwinMaker)
    - IoT
    - BIM

# Research tracks


## Modeling and simulation

Federated FaaS (AWS, Google, Microsoft, Alibaba, IBM) is a challenging heterogeneous environment. My goal is to create a mathematical model that estimates performance of serverless functions with minimum effort.

With our recent paper SimLess, the first step was moved by modeling the round trip time of a function to each FaaS provider (from university of Innsbruck).

Work in progress models:
- deployment time of functions
- storage access time
- Backend-as-a-Service (BaaS) (Object recognition, Speecht2Text, Text2Speech)


New models that are to be researched
- cold/warm start
- Backend-as-a-Service (e.g., NLP, Prediction, ...)
- performance variability


## Interoperability, portability, and federation

This track researches libraries to abstract BaaS services that are used by functions. The libraries offer developers to develop functions with abstract BaaS services, while the specific provider and region is selected during runtime.

Already developed such libraries are:
- fRecognition (Java)
- fStorage (Java, Python, Go)

Work in progress
- Speech2Text, Text2Speech


## xAFCL Serverless Workflow Management System

As a result of several bachelor and master theses that I supervised, we have developed a prototype of the *xAFCL* serverless workflow management system , which is able to run serverless workflows or function choreographies (*FCs*) across many widely-known cloud providers. FCs are developed in our Abstract Function Choreography Language ([AFCL](https://doi.org/10.1016/j.future.2020.08.012)).

*xAFCL EE* integrates the component [FTjFaaS](https://github.com/sashkoristov/FTjFaaS) for optional fault tolerant execution of FC functions (currently supported AWS Lambda and IBM Cloud Functions) and [jFaaS](https://github.com/sashkoristov/jFaaS/) for portable execution across many FaaS systems (AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, Microsoft Azure Cloud Functions, etc).


## Scheduling

This broad research topic receives as input the first two topics, provides an optimal FC, and then runs it on xAFCL.

### Published schedulers:

- xAFCL
- rAFCL
- FaaSt


### Work in progress:
- data-aware pyStorage
- data-aware matchmaking
- DeployLess
- SpeechLess
- MO in Federated FaaS

## BIM & Digital Twins

Will be provided details very soon.

TOPICS:
- FeDT: Federated Digital Twins in Federated Clouds 



# Other Information

The following paragraphs present the available and recently started topics for master theses directly connected with the AFCL Environment. It also presents the active and closed master theses. 

You can find a latex template for the master thesis which includes some hints [here](https://github.com/sashkoristov/master-theses/tree/main/template).


# Milestones for a successful master thesis

- Requirements analysis
- Review the related work
- System architecture
- Development
- Evaluation
- Finalizing the master thesis
- Defensio
- `Farewell party` :blush:

# Available master theses

* Tentative requirements analyses August-September 2023
* Tentative start September 2023 - January 2024
* Tentative finish June - September 2024

The following topics for master theses are available for the winter semester 2023:


## *HolisticFaaS*

| Title | ***HolisticFaaS*: A web-based platform for management of serverless applications in Federated FaaS** |
| ----- | ----- | 
| Description |  Each FaaS provider offer management console where their customers can view and manage serverless functions. Unfortunately, users need to use multiple management consoles when their serverless applications are deployed across different FaaS provider, e.g., due to better performance, lower cost, increased resilience, better service offer, etc. In this master thesis, the student will develop a web-based platform for holistic view of all user serverless applications across different providers. Moreover, the platform will offer migration / replication of applications from one to another user, from one to another cloud region, one to another providers, etc. The system has a holistic view of all source codes (e.g., github), deployment packages, inputs to the applications (e.g., input.json), yaml file of the applications (e.g., AFCL yaml file), etc. <br> *Use case 1*: students do some project and have functions on their own accounts / providers / cloud regions. The lecturer has a hard time to replicate the environment. <br> *Use case 2* The research team comprises multiple users, each with different accounts and need to share / run / replicate serverless applications in federated FaaS.
|Tasks| 1. Develop a module for migration / replication per user / region / workflow application / function / provider. <br> 2. Develop web-based application for user and serverless application management. <br> 3. Integrate automatic deployer for various FaaS providers (e.g. TerraForm, Serverless Framework, GoDeploy, TestOps).<br> 4. Evaluate migration / replication of serverless applications.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs, git.|
| Related work | 1. (`Automatic function packaging and deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF). This tools can be used for wrappers and deployment scripts for various programming languages and FaaS providers. <br> 2. (`Node.js FaaSifier`) S. Ristov, S. Pedratscher, J. Wallnöfer, and T. Fahringer, “DAF: Dependency-Aware FaaSifier for Node.js Monolithic Applications,” in IEEE Software, doi: 10.1109/MS.2020.3018334, [DAF](https://github.com/qngapparat/daf).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. (`Automatic function deployment`) [Serverless](https://www.serverless.com/).<br>  5. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking.|
---

## *xAFCL2* (xAFCLStream)

| Title | ***xAFCL2*: A microservices-based serverless workflow management system in Federated FaaS** |
| ----- | ----- | 
| Description |  I plan to migrate the existing xAFCL serverless workflow management system on a new platform based on microservices, including <br> - *workflow parser(s)* microservice(s), (AFCL or Step Functions.) <br> - *static scheduler(s)* service(s) (e.g., random, FaaSt, etc.); <br> - *invoker service* to run functions across multiple providers; <br> - *deployer service* to deploy functions across multiple providers; <br> - *resilience service* (e.g., for fault tolerance); <br> - *monitoring service* (status of each function), <br> - *dynamic scheduler* before execution, still check the status of cloud regions, etc. <br> The system should support both synchronous and asynchronous serverless workflows, as well as multiple serverless workflows simulatenaously.   
|Tasks| 1. Develop the core microservices (parser, invoker, monitor, resilience). <br> 2. Develop at least one scheduler microservice. <br> 3. Integrate automatic deployer for various FaaS providers (e.g. TerraForm, Serverless Framework, GoDeploy, TestOps).<br> 4. Evaluate latencies of the system. 5. Evaluate the system with state-of-the-art.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. Ideally the student attended the course "Serverless Cloud Automation Application" SS23. <br> 2. Books regarding microservice patterns.<br> 3. *xAFCL* enactment engine with integrated simulator SimLess [*xAFCL EE*](https://doi.org/10.1109/TSC.2021.3128137).<br> 4. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking.|
---


## *xAFCLSim3*

SLO-based Simulation Framework for AFCL Serverless Workflows  


## *WarmFaaS*

Model the Cold Start Effect and Warm Serverless Functions




## *fOps*

| Title | ***fOps*: A pipeline for one-touch development, deployment, and testing of serverless functions across multiple providers** |
| ----- | ----- | 
| Description |  The goal of this master thesis is to develop a CI/CD pipeline for development, deployment, and testing of serverless functions across multiple providers. The main approach is to minimize the development effort and automatize the deployment and testing of the code for multiple FaaS providers (e.g., AWS, IBM, Google, Azure, Alibaba). The developer needs to develop the function locally only once (*function template*) and after pushing the code on git (eg. github), *fOps* pipeline will conduct a series actions. First, *fOps* will encapsulate the code (*function implementation* - *FI*) for the selected programming language (e.g., Java, Python, Node.js, Go) for each supported FaaS provider including all dependencies. Second, *fOps* will deploy the code (FI) for each specified *function deployment* - *FD* (e.g. in MariaDB AFCL metadata database), which may include deploy the code on various cloud regions of multiple FaaS providers and determine the minimum needed memory, run the code with some predefined data inputs and test whether the code runs successfully on each FaaS provider. Finally, *fOps* will run functional and non-functional tests and store deployment times, package size, resource link, round trip time, and minimum memory in the existing AFCL metadata database for all FDs. *fOps* may consider to deploy multiple functions from a single code with multiple handlers and functions may be developed with fService and then also tests should check if the function may use all enumerated services. *fOps* will be evaluated with a real life workflow for various FaaS providers.
|Tasks| 1. Develop a module for pipeline scripts. <br> 2. Develop wrappers for serverless function handlers for the selected programming languages for various FaaS providers (e.g. AWS, IBM, Google, etc). <br> 3. Develop interfaces with AFCL metadata DB. <br> 4. Develop an automatic deployer for various FaaS providers (e.g. AWS, IBM, Google, etc).<br> 5. Evaluate *fOps* with real life applications.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs, git.|
| Related work | 1. (`Automatic function packaging and deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF). This tools can be used for wrappers and deployment scripts for various programming languages and FaaS providers. <br> 2. (`Node.js FaaSifier`) S. Ristov, S. Pedratscher, J. Wallnöfer, and T. Fahringer, “DAF: Dependency-Aware FaaSifier for Node.js Monolithic Applications,” in IEEE Software, doi: 10.1109/MS.2020.3018334, [DAF](https://github.com/qngapparat/daf).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. (`Automatic function deployment`) [Serverless](https://www.serverless.com/).<br>  5. (`Node2FaaS Framework`) [Node2FaaS *FCifier*](https://github.com/node2faas/framework).|
---


## *fServiceX*

| Title | ***fServiceX*: Agile development of serverless applications with abstract cloud services** |
| - | - | 
| Description | Development of serverless functions that use multiple cloud services is a complex task as it may require huge development effort to integrate various libraries for each cloud service that the function uses. Recently, I supervised the bachelor thesis *fService: Configurable abstraction for serverless development* in which we established the main abstraction of cloud services through abstraction of AWS's and Google's storages and object recognition cloud services for java serverless functions. The library can be added as Maven dependency in Java functions. Further on, two other bachelor theses are active (*pyStorage* and *portableGo*), which extend the concept of *fService* for abstract storage in Python and Go. This master thesis extends *fService* to support various programming languages (e.g., Java, node.js, Python, etc.) and various cloud services (e.g., storage, object recognition, prediction, speech2text, text2speech, etc) of multiple cloud providers (e.g., AWS, Google, etc). Heuristics may be added to determine which specific cloud service to be used (e.g., Amazon Transcribe or Google SpeechtoText) based on the storage location of the audio file. 
|Tasks| 1. Define interfaces and methods for the selected cloud storages. For instance, copy(sourceURL, destURL), voice2text(sourceAudio, destText).<br> 2. Develop implementations of interfaces for various cloud providers (e.g., AWS, Google, etc) and their abstracted services in selected programming language(s). <br> 3. Build portable function choreography (*FC*) for a real-life application with dynamic inputs of serverless functions to specify the specific cloud service that they use (e.g. location of the input audio files).<br> 4. Develop a model for portable cloud services used by FC functions.<br> 5. Based on the model, develop a scheduler that updates the FC (function deployments and service deployments as data inputs).<br> 6. Evaluate the system with the developed FC and optimal selection of the proper cloud service.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | programming languages; Cloud APIs.|
---

## *SLO-AFCL*

| Title | ***SLO-AFCL*: FaaScinating resilience for function choreographies using service level objectives (SLOs)** |
| - | - | 
| Description |  ([xAFCL EE](https://github.com/sashkoristov/enactmentengine)) may run alternative *function deployments* (*FDs*) of a serverless workflow or function choreography (*FC*) in AFCL across the top five FaaS providers. It also can log various cost, performance, and fault tolerance parameters of functions and entire FCs. However, having a proactive component that will dynamically adapt which FDs and alternatives to run will improve its resilience. An example of SLO (service level objectives) for an FC would be minimum 99% of all executions will succeed, with maximum cost of 5$ and finish within 2 seconds. Thresholds may be failure rate of each function is maximum 0.5%. This master thesis will adaptively determine which FD and which alternatives to run for each FC function based on specified SLOs, which can be defined for different parameters of functions (round trip time, cost, failure rate), for the FC (makespan, cost), for specific cloud region, and for different time period (in the last minute, hour, day, etc). *SLO-AFCL* can create and select new FDs in other cloud regions (twins), in the same cloud region with more or less memory (siblings), more FDs in parallel to increase availability, etc. *SLO-AFCL* will be evaluated with a real life workflow for various FaaS providers.
|Tasks| 1. Research parameters that can be used to define SLOs ranges and thresholds including parameters of functions, time periods, FC, cloud providers and their regions, etc.<br> 2. Develop interfaces with AFCL metadata DB.<br> 3. Develop / adapt monitoring for SLOs.<br> 4. Develop an AFCL adaptor that will adapt resource FDs and alternatives.<br> 5. Visualize SLO parameters.<br> 6. Evaluate *SLO-AFCL* with the real-life FCs and specific scenarios that try to breach SLOs.|
| Theoretical skills | Cloud Computing, Serverless, AFCL, fault tolerance. | 
| Practical skills | Algorithms, Cloud APIs.|
| Related work | 1. [Google SRE](https://sre.google/)



# Active master theses (WS2022)


##  *CORE*

| Title | ***CORE*: Code Once, Run Everywhere. Engineering Serverless Workflow Applications with High-Level of Abstraction** |
| - | - | 
| Student | Thomas Larcher | 
| Status | System architecture | 
| Description | All cloud providers offer SDKs to easily code applications with their services. While on the one hand, these SDKs simplify developers' effort, they lock users to use other cloud services from the same cloud provider. Such codes (e.g., serverless functions), are neither *portable* (to migrate them on another cloud provider), nor *interoperable* (switch cloud service from another cloud provider). This vendor lock-in prevents users to switch the same service from other providers or to mix services from arbitrary providers. For instance, one cloud provider may reduce storage price, while another cloud provider may introduce more accurate OCR service for preferred language. To bridge this gap, this master thesis introduces CORE (Core Once Run Everywhere), an abstraction library that allows developers to code portable functions that can use interoperable cloud services within serverless workflows (text2speech and OCR). Moreover, heuristics will be researched to select the appropriate service based on user objectives.||
---


##  *AccessLess*

| Title | ***AccessLess*: Data-aware scheduler in Federated FaaS** |
| - | - | 
| Student | Mika Hautz | 
| Status | System architecture | 
| Description | The aim of this master thesis is create a data-aware scheduler that aims to minimize the overall makespan of a serverless workflow in federated FaaS. *AccessLess* analyzes ephemeral data transfers between functions of the workflow and considers network locality. Unlike the related work, which schedules functions only, *AccessLess* schedules where ephemeral data should be stored in federated FaaS.||
---



# Closed master theses

1. "*CrossFlow*: Cross-layered resource management in Cloud continuum", Ahmet Aspir, WS2022 [details](./closed/CrossFlow.md)
1. "*AFCL-Sched*: Optimal execution of FCs across multiple FaaS systems", Christian Hollaus, SS2022 [details](./closed/AFCL-Sched.md).
1. "AFCL Environment - Development and Scalable Execution of Portable Function Choreographies Across Multiple Serverless Cloud Platforms", Stefan Pedratscher, SS2021 [details](./closed/AFCLEnvironment.md).
1. "VolatileSim: A simulation framework for cloud volatile resources", Christoph Schöpf, SS2020, `Among top four master theses for 2020` at the institute.
1. "Distributed GPGPU on Cloud GPU Clusters", Martin Schuchardt, SS2019.


Details for closed master theses can be found [here](./closed/README.md).



----

# Contact

If you need any additional information, please do not hesitate to contact me. 

My topics for bachelor theses may be found [here](https://github.com/sashkoristov/bachelor-theses), which could also be adapted as master theses.