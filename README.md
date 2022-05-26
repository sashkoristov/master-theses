# Master theses topics (Supervisor: `Sashko Ristov`)
A repository for available, active and closed topics for master theses supervised by Sashko Ristov.

As a result of several bachelor and master theses that I supervised, we have developed a prototype of the *xAFCL* enactment engine, which is able to run serverless workflows or function choreographies (*FCs*) across many widely-known cloud providers. *xAFCL EE* integrates the component [FTjFaaS](https://github.com/sashkoristov/FTjFaaS) for optional fault tolerant execution of FC functions (currently supported AWS Lambda and IBM Cloud Functions) and [jFaaS](https://github.com/sashkoristov/jFaaS/) for portable execution across many FaaS systems (AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, Microsoft Azure Cloud Functions, etc).

*xAFCL EE* is the core part of the [AFCL Environment](https://github.com/sashkoristov/AFCLEnvironment), a platform to develop, deploy, and fault tolerant execution of FCs developed in our Abstract Function Choreography Language ([AFCL](https://doi.org/10.1016/j.future.2020.08.012)).

Moreover, the AFCL Environment architecture includes FaaSifiers, FCfiers, agile development, and automatic deployment.

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

* Tentative requirements analyses February-March 2022
* Tentative start March-April 2022
* Tentative finish October-December 2022

The following topics for master theses are available for the summer semester 2022:


## *CardioHPC*

| Title | ***CardioHPC*: Serverless real-time heart monitoring centre** |
| ----- | ----- | 
| Description | The goal of this master thesis is to develop real-time monitoring centre of patients' sensor data.  Simulation of real-time monitoring centre includes experiment setup, simulation, and evaluation phases. CardioHPC should support both real-time stream of small messages (during wi-fi connection) or batch processing of offline files (e.g., when the mobile device connects to wi-fi after considerable time being offline). For this purpose, the messages should be calssified as small/big and high/low priority and handled accordingly. For the big and low priority, a set of actions should be performed in a form of an AFCL serverless workflow or function choreography (*FC*) after upload of patients' data. For the real-time stram, CardioHPC may use Kafka, where small messages and references to big messages will be placed. Afterwards, a set of serverless functions will handle patients'data, including noise intervals identification and elimination, heartbeat detection, detection of fibrillation, identification of segments and elevation, heart rate variability, statistical analysis, alerting, and reporting. A generator of a virtual patient ECG will be developed to simulate generated files. The evaluation metrics will include measuring of response times for different test cases varying the workload (e.g., from 1K to 20K virtual patients ECG data simultaneously and their length). The experiment will be executed with the existing *xAFCL* enactment engine ([xAFCL EE](https://github.com/sashkoristov/enactmentengine)). The target is to measure various performance indicatiors, such as response time, speedup, and throughput versus the number of cloud regions.
|Tasks| 1. Develop serverless functions. <br> 2. Develop AFCL FC that distributed the work.<br> 3. Develop the event-based pipeline.<br> 4. Evaluate *CardioAFCL* with various workload (weak and strong scaling).|
| Theoretical skills | Cloud Computing, Serverless, file management, ECG data management (existing libraries). | 
| Practical skills | FaaS, Cloud API, data streams.|
---


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



# Active master theses (SS2021)


## *AFCL-Sched*

| Title | ***AFCL-Sched*: Optimal execution of FCs across multiple FaaS systems** |
| - | - | 
| Student | Christian Hollaus | 
| Status | Defensio | 
| Description | The aim of this master thesis is to conduct a series of experiments to evaluate the properties and constraints of widely-known FaaS systems (e.g. AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, etc.). Based on the findings, a multi-objective scheduler will be developed for optimal execution of FCs across multiple FaaS systems.| |
---


##  *CrossFlow*

| Title | ***CrossFlow*: Cross-layered resource management in Cloud continuum** |
| - | - | 
| Student | Ahmet Aspir | 
| Status | Finalizing the master thesis | 
| Description | This thesis will research methods to develop CrossFlow, a federated platform to maange various types of resources in the cloud continuum.| |
---


# Closed master theses

1. "AFCL Environment - Development and Scalable Execution of Portable Function Choreographies Across Multiple Serverless Cloud Platforms", Stefan Pedratscher, SS2021 [details](./closed/AFCLEnvironment.md).
1. "VolatileSim: A simulation framework for cloud volatile resources", Christoph Schöpf, SS2020, `Among top four master theses for 2020` at the institute.
1. "Distributed GPGPU on Cloud GPU Clusters", Martin Schuchardt, SS2019.


Details for closed master theses can be found [here](./closed/README.md).



----

# Contact

If you need any additional information, please do not hesitate to contact me. 

My topics for bachelor theses may be found [here](https://github.com/sashkoristov/bachelor-theses), which could also be adapted as master theses.