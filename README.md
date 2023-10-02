# Master theses topics (Supervisor: `Sashko Ristov`)

`New topics for winter semester 2023/2024.`

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

The following paragraphs show the current research topics that I work on. Other topics from the two main areas (cloud computing and energy efficiency) are also possible. Please prepare a teaser (ca. 1 page) regarding the recommended topic.

## Modeling and simulation

Federated FaaS (AWS, Google, Microsoft, Alibaba, IBM) is a challenging heterogeneous environment. My goal is to create a mathematical model that estimates performance of serverless functions with minimum effort.

With our recent paper SimLess, the first step was moved by modeling the round trip time of a function to each FaaS provider (from university of Innsbruck).

Work in progress models (can be extended to define a master thesis):
- deployment time of functions, cloud provider, network proximity to cloud regions
- storage access time
- Backend-as-a-Service (BaaS) (Object recognition, Speecht2Text, Text2Speech)


New models that are to be researched (can be defined as a master thesis)
- cold/warm start, caching vs. cold start vs. scalability
- deployment package size of the function, build time, layers, by reference / zipped, etc
- Backend-as-a-Service (e.g., NLP, Prediction, ...) - runtime, cost, concurrency, throughput, accuracy, etc.
- Predict FaaS performance variability and schedule the functions in federated FaaS


## Interoperability, portability, and federation

This track researches libraries to abstract BaaS services that are used by functions. The libraries offer developers to develop functions with abstract BaaS services, while the specific provider and region is selected during runtime.

Already developed such libraries are:
- fRecognition (Java)
- fStorage (Java, Python, Go)
- Speech2Text, Text2Speech (Java, Go)
- OCR, Translate (Java)

Work-in-progress:
- fRecognition (Python)
- fStorage (Node.js)
- Speech2Text, Text2Speech (Python)

Both for AWS and GCP. 

## xAFCL Serverless Workflow Management System

As a result of several bachelor and master theses that I supervised, we have developed the *xAFCL* serverless workflow management system, which is able to run and simulate serverless workflows or function choreographies (*FCs*) across many widely-known cloud providers. FCs are developed in our Abstract Function Choreography Language ([AFCL](https://doi.org/10.1016/j.future.2020.08.012)). Several *scentific* (Montage, 1000Genome, BWA, Monte Carlo Pi approximation) and *business* FCs (celebrityDetection) are already publicly available ([AFCL Workflows](https://github.com/AFCLWorkflows/)).

*xAFCL EE* integrates the component [FTjFaaS](https://github.com/sashkoristov/FTjFaaS) for optional fault tolerant execution of FC functions (currently supported AWS Lambda and IBM Cloud Functions) and [jFaaS](https://github.com/sashkoristov/jFaaS/) for portable execution across many FaaS systems (AWS Lambda, IBM Cloud Functions, Google Cloud Functions, Alibaba Function Compute, Microsoft Azure Cloud Functions, etc).


## Scheduling serverless workflows in federated FaaS

### Published schedulers:

- xAFCL
- rAFCL
- FaaSt


### Work in progress:
- data-aware pyStorage (schedule both ephemeral data and serverless functions)
- DeployLess (deployment time vs. scalability)
- BaaSLess (schedule both BaaS services and serverless functions - using the fService libraries)
- MO in Federated FaaS (optimize cost, performance)

### Future work
- data-aware matchmaking
- MO in Federated FaaS (optimize other metrics BaaS accuracy, resilience, trustworthiness, etc)


## Energy efficiency, Digital Twins, BIM

Work in progress:

- two bachelor theses started with cloud-based management and automated creation of cloud-based digital twins
- energy efficiency of green prosumers (producers + consumers)


# Other Information

The following paragraphs present the available topics for master theses, as well as the active and closed master theses. 

You can find a latex template for the master thesis which includes some hints [here](https://github.com/sashkoristov/master-theses/tree/main/template).


# Available master theses

Tentative timeline for the available topics:

* Requirements analyses October-November 2023
* Start October 2023 - January 2024
* Finish April - September 2024

The given timeline is tentative and can be adapted before starting the master thesis.

The following topics for master theses are available to start in the winter semester 2023/24:


## *ServerlessIntent*

| Title | ***ServerlessIntent*: A novel programming model to code portable serverless applications with interoperable cloud services in federated clouds** |
| ----- | ----- | 
| Description | Developers increasingly deploy Backend-as-a-Service (BaaS)-enabled serverless functions across various cloud providers to exploit the variety of BaaS offerings to reduce costs or enhance performance. However, the dependence on specific provider features and configurations still leads to challenges in terms of portability, underlying platform heterogeneity, and vendor lock-in. Developers still largely face a choice to either use BaaS services from a single provider or code many versions of their serverless functions to support multiple cloud providers. This master thesis would investigate the potential for a novel programming model for serverless applications that allows developers to code portable functions with interoperable BaaS services in a uniform manner, based on a novel approach with *serverless intents*. Serverless intent abstracts heterogeneous BaaS services, including their provider, region, features scope, and input and output data access types. The developer specifies `WHAT` is the *intent* (e.g. *SpeechRecognition*), `WHICH` *features* of the intent (e.g., *srtSubtitles*) including their *values* (e.g., *true* or *false*) will be applied, to `WHOM` *input* should the intent and features be applied, and `WHERE` the output should be stored. One serverless intent may represents a single BaaS service that should be executed on multiple providers to achieve a union of features of all providers or a composition of multiple BaaS services to create complex composite BaaS services. For example, no single BaaS service exist for the following *intent*: Blind people in Germany to read pdf files written in English. The programming model should automatically implement this intent with a composition of three BaaS services *OCR* → *translate* → *T2S*. Additionally, the programming model should automatically generate a serverless workflow to implement the required intent, including helper built-in intents to split, merge, and distribute the inputs to intents to overcome limitations and constraints of a each cloud provider. 
|Tasks| 1. Develop a data model (features, values, providers, BaaS, constraints, range, etc.) for serverless intents, which includes BaaS services and storage access of at least two cloud providers. <br> 2. Develop an intelligent system that will find a sequence of simple intents (BaaS services) to create the required intent <br> 3. Develop an API to automatically create a serverless workflow. <br> 4. Evaluate the system. 5. Evaluate the system with state-of-the-art.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. *xAFCL* enactment engine with integrated simulator SimLess [*xAFCL EE*](https://doi.org/10.1109/TSC.2021.3128137).<br> 2. Abstract Function Choreography Language [AFCL](https://doi.org/10.1016/j.future.2020.08.012). <br> 3. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as CORE for interoperable BaaS services.|

### Architecture of serverless intents

| <img src="figures/intent.pdf" /> | <img src="figures/ServerlessIntent.pdf" /> |


---


## *AFCL-Throughput*

| Title | ***AFCL-Througput*: Optimize AFCL serverless workflows with limited throughput in federated FaaS** |
| ----- | ----- | 
| Description | Many scheduling techniques exist that optimize workflow applications in federated clouds. They map workflow tasks to the existin set of resources based on some heuristics or genetic algortihms. In either case, they use the constraint of maximum allowed concurrent tasks based on the amount of resources, assuming that the number of tasks is much larger than the number of available resources. For instance, in our papers xAFCL and FaaSt, we used earliest finish time list-based schedulers to map functions of the workflow across multiple regions of federated FaaS. We considered the concurrency limit of cloud providers up to 1,000 concurrent functions. However, cloud providers have another constraint in terms of throughput, that is, the amount of invocations within a given time frame. Unfortunately, this parameter is often ignored by existing serverless and other workflow management systems. To bridge this gap, in this master thesis, the student will extend the existing xAFCL system with a scheduler that monitors the number of invocations and optimize the workflow execution in federated FaaS. 
|Tasks| 1. Develop the scheduler *AFCL-Througput*. <br> 2. Develop a monitoring module in the xAFCL serverless workflow management system. <br> 3. Adapt AFCL with throughput constraint, apart from concurrency.<br> 4. Develop a mathematical model for *AFCL-Througput* and validate it. <br> 5. Evaluate the *AFCL-Througput* scheduler with state-of-the-art schedulers and real-life workflows.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. *xAFCL* enactment engine [*xAFCL*](https://doi.org/10.1109/TSC.2021.3128137).<br> 2. Abstract Function Choreography Language [AFCL](https://doi.org/10.1016/j.future.2020.08.012). <br> 3. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking. <br> 4. Various AFCLWorkflows on our github organization [*AFCLWorkflows*](https://github.com/AFCLWorkflows), such as Montage, BWA, 1000Genome, etc, which run on AWS and GCP with dynamic selection of function location and storage during runtime. <br> 5. Various AFCLWorkflows on our github organization [*AFCLWorkflows*](https://github.com/AFCLWorkflows), such as Montage, BWA, 1000Genome, etc, which run on AWS and GCP with dynamic selection of function location and storage during runtime.||
---



## *AFCL2`ABOL`*

| Title | ***AFCL2`ABOL`*: An `A`bstract `B`ackend-as-a-service `O`rchestration `L`anguage for serverless workflows in federated clouds** |
| ----- | ----- | 
| Description | The existing serverless workflow management systems for federated FaaS (e.g., xAFCL, FuncX, Hyperflow, TriggerFlow, LithOps, etc.) orchestrate serverless functions in a workflow. Unfortunately, the orchestration languages are mainly focused on the data and control flow, seeing the functions as a black box computing nodes. However, the recent [report](https://doi.org/10.1109/TSE.2021.3113940) have shown that up to 60 % of functions access to BaaS services. This master thesis would investigate the potential for a novel abstract language, based on our AFCL language (Abstract Function Choreography Language) to orchestrate not only serverless functions, but also BaaS services directly, without being wrapped in the serverless function. We can expand definition of BaaS services to any type of atomic task, including function on local docker container, or any other isolated sandbox, such as WebAssembly. The student will create ABOL-serverless workflows and evaluate its benefits. Note: this thesis can closely collaborate with *HolisticFaaS* and *xAFCL2* master theses, especially with the existing interoperable fService libraries.
|Tasks| 1. Develop the MVP of the new ABOL language and schema to describe a workflow of BaaS services. <br> 2. Develop MVP ABOL-core API to build and validate ABOL serverless workflows. <br> 3. Migrate existing xAFCL / develop new MVP *xABOL enactment engine* (*ABOL-parser* that uses ABOL-core and *ABOL BaaS-invoker*).<br> 4. Evaluate latencies of the system. 5. Evaluate the system with state-of-the-art.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. *xAFCL* enactment engine with integrated simulator SimLess [*xAFCL EE*](https://doi.org/10.1109/TSC.2021.3128137).<br> 2. Abstract Function Choreography Language [AFCL](https://doi.org/10.1016/j.future.2020.08.012). <br> 3. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking.|
---


## *GreenifyProsumers*

| Title | ***GreenifyProsumers*: A cloud-based optimization framework for maximize efficiency of prosumers** |
| ----- | ----- | 
| Description |  Energy efficiency is an important area for todays life, not only to reduce the overall energy consumption, but also to replace the "brown" with the "green" sources of energy. For this purpose, many contries and the European Union create communities that merge together energy producers and consumers, known together as *prosumers* into a local self-sustainable systems. Within these communities, the larger challenge is when to spend energy, rather than how much each prosumer spends, in order to reduce the losses of green energy transformation and the need of brown energy to compensate. This master thesis will explore the existing platforms that model energy efficiency, together with optimization frameworks. Based on that, the student will integrate / develop / extend a module that optimizes green energy consumption, considering controlable (e.g., electric car batteries, batch processing) and non-controlable (lightning in a building) prosumers. The focus will be given on [GEA](https://energiegemeinschaften.gv.at/gemeinschaftliche-erzeugungsanlagen/) buildings (Gemeinschaftlichen Erzeugungsanlagen) and [EEGs](https://energiegemeinschaften.gv.at/erneuerbare-energie-gemeinschaften-eeg/) (Erneuerbare-Energie-Gemeinschaft), including specifics of large office buildings, schools, villages, and local districts. 
|Tasks| 1. Develop cloud-based web framework that can add / import settings of all prosumers <br> 2. Develop optimization framework and one optimization algorithm <br> 3. Integrate the framework with cloud services for digital twins (e.g., Azure Digital Twins)<br> 4. Evaluate the developed algorithm for a given dataset <br>5. Evaluate scalability of the system.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. EnergyPlus (as a source for energy consumption models). <br> 2. https://doi.org/10.1016/j.scs.2022.104289 various models for home-based procumers with empirical values. <br> 3. Optimization frameworks, e.g., jMetal or Opt4j. <br>4. https://www.energyplan.eu/|
---

## *xAFCLBaaSSim*

| Title | ***xAFCLBaaSSim*: Simulation Framework for BaaS-enabled AFCL Serverless Workflows** |
| ----- | ----- | 
| Description | The initial version of the [*SimLess*](https://doi.org/10.1145/3542929.3563478) simulation framework, which is included in the xAFCL serverless workflow managent system, introduced a mathematical model to simulate `twins` (functions in other regions with the same memory) and `siblings` (functions in the same region with different memory) of a function. In the meantime, we extended SimLess with a mathematical model to simulate `cousins` (twins or siblings that access storage in other cloud regions than the original function). This master thesis will extend SimLess even further, to simulate BaaS-enabled serverless workflows, which run functions, BaaS services, and input/output data on any location in the federated FaaS. For instance, a function runs on AWS Frankfurt, which runs a BaaS service GCP Vision in Frankfurt, with input data is stored in AWS London, and the output data should be stored in GCP North Virginia.  
|Tasks| 1. Develop a mathematical model for BaaS services in general <br> 2. Validate the mathematical model in federated FaaS. <br> 3. Evaluate *xAFCLBaaSSim* with real life workflows. <br> 4. Run sensitivity analysis to determine the accuracy / cost trade-off for simulation setup. |
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. [*xAFCL*](https://doi.org/10.1109/TSC.2021.3128137) enactment engine with integrated simulator  [*SimLess*](https://doi.org/10.1145/3542929.3563478) .<br> 2. Abstract Function Choreography Language [AFCL](https://doi.org/10.1016/j.future.2020.08.012). <br> 3. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking. <br> 4. Various BaaS-enabled AFCLWorkflows on our github organization [*AFCLWorkflows*](https://github.com/AFCLWorkflows), such as pdf2Speech and speechTranslate, which run on AWS and GCP with dynamic selection of function location, BaaS service Speech2Text and Text2Speech, and storage during runtime. <br> 5. Various AFCLWorkflows on our github organization [*AFCLWorkflows*](https://github.com/AFCLWorkflows), such as Montage, BWA, 1000Genome, etc, which run on AWS and GCP with dynamic selection of function location and storage during runtime.|
---


## *OptimizeFedFaaS*

Model and optimize specific aspects of Serverless Workflows (More details will follow very soon). For the moment, see the four [bachelor theses topics](https://github.com/sashkoristov/bachelor-theses): 

1. *CacheLess*: Cache-aware data flow in AFCL serverless workflows.
1. *StorageLess*: Benchmark networking of federated FaaS with federated storage infrastructure.
1. *PackageLess* Benchmarking packaging and deployment time of serverless functions in federated FaaS.
1. *ProfileBaaS*: Characterizing and profiling Backend-as-a-Service in Federated FaaS.


<!--
## *fServiceX*

## *fOps*

| Title | ***fOps*: A pipeline for one-touch development, deployment, and testing of serverless functions across multiple providers** |
| ----- | ----- | 
| Description |  The goal of this master thesis is to develop a CI/CD pipeline for development, deployment, and testing of serverless functions across multiple providers. The main approach is to minimize the development effort and automatize the deployment and testing of the code for multiple FaaS providers (e.g., AWS, IBM, Google, Azure, Alibaba). The developer needs to develop the function locally only once (*function template*) and after pushing the code on git (eg. github), *fOps* pipeline will conduct a series actions. First, *fOps* will encapsulate the code (*function implementation* - *FI*) for the selected programming language (e.g., Java, Python, Node.js, Go) for each supported FaaS provider including all dependencies. Second, *fOps* will deploy the code (FI) for each specified *function deployment* - *FD* (e.g. in MariaDB AFCL metadata database), which may include deploy the code on various cloud regions of multiple FaaS providers and determine the minimum needed memory, run the code with some predefined data inputs and test whether the code runs successfully on each FaaS provider. Finally, *fOps* will run functional and non-functional tests and store deployment times, package size, resource link, round trip time, and minimum memory in the existing AFCL metadata database for all FDs. *fOps* may consider to deploy multiple functions from a single code with multiple handlers and functions may be developed with fService and then also tests should check if the function may use all enumerated services. *fOps* will be evaluated with a real life workflow for various FaaS providers.
|Tasks| 1. Develop a module for pipeline scripts. <br> 2. Develop wrappers for serverless function handlers for the selected programming languages for various FaaS providers (e.g. AWS, IBM, Google, etc). <br> 3. Develop interfaces with AFCL metadata DB. <br> 4. Develop an automatic deployer for various FaaS providers (e.g. AWS, IBM, Google, etc).<br> 5. Evaluate *fOps* with real life applications.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs, git.|
| Related work | 1. (`Automatic function packaging and deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF). This tools can be used for wrappers and deployment scripts for various programming languages and FaaS providers. <br> 2. (`Node.js FaaSifier`) S. Ristov, S. Pedratscher, J. Wallnöfer, and T. Fahringer, “DAF: Dependency-Aware FaaSifier for Node.js Monolithic Applications,” in IEEE Software, doi: 10.1109/MS.2020.3018334, [DAF](https://github.com/qngapparat/daf).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. (`Automatic function deployment`) [Serverless](https://www.serverless.com/).<br>  5. (`Node2FaaS Framework`) [Node2FaaS *FCifier*](https://github.com/node2faas/framework).|
---

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

-->

# Active master theses


## *HolisticFaaS*

| Title | ***HolisticFaaS*: A web-based platform for management of serverless applications in Federated FaaS** |
| ----- | ----- | 
| Student | Stefan Achmüller | 
| Status | Requirements analysis | 
| Description |  Each FaaS provider offers a management console where their customers can view and manage serverless functions. Unfortunately, users need to use multiple management consoles when their serverless applications are deployed across different FaaS providers, e.g., due to better performance, lower cost, increased resilience, better service offer, etc. In this master thesis, the student will develop a web-based platform for holistic view of all user serverless applications across different providers. Moreover, the platform will offer migration / replication of applications from one to another user, from one to another cloud region, one to another provider, etc. The system has a holistic view of all source codes (e.g., github), deployment packages, inputs to the applications (e.g., input.json), yaml file of the applications (e.g., AFCL yaml file), etc. <br> *Use case 1*: students do some project and have functions on their own accounts / providers / cloud regions. The lecturer has a hard time to replicate the environment. <br> *Use case 2* The research team comprises multiple users, each with different accounts and need to share / run / replicate serverless applications in federated FaaS.|
|Tasks| 1. Develop a module for migration / replication per user / region / workflow application / function / provider. <br> 2. Develop web-based application for user and serverless application management. <br> 3. Integrate automatic deployer for various FaaS providers (e.g. TerraForm, Serverless Framework, GoDeploy, TestOps).<br> 4. Evaluate migration / replication of serverless applications.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs, git.|
| Related work | 1. (`Automatic function packaging and deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF). This tools can be used for wrappers and deployment scripts for various programming languages and FaaS providers. <br> 2. (`Node.js FaaSifier`) S. Ristov, S. Pedratscher, J. Wallnöfer, and T. Fahringer, “DAF: Dependency-Aware FaaSifier for Node.js Monolithic Applications,” in IEEE Software, doi: 10.1109/MS.2020.3018334, [DAF](https://github.com/qngapparat/daf).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. (`Automatic function deployment`) [Serverless](https://www.serverless.com/).<br>  5. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking.|
---

## *FissionLess*

| Title | ***FissionLess*: FaaSify and fission monoliths as pipelines in federated FaaS** |
| ----- | ----- | 
| Student |  Simon Triendl| 
| Status | Development | 
| Description | Often, serverless functions are seen as a black-box atomic units that receive data input to compute something and return data output. Many existing works use fusion to merge computation within serverless workflows, thereby reducing invocation latency and ephemeral data transfer between workflow functions. In this thesis, we will dive into the function code and examine to what extent fission of user or serverless functions into multiple smaller chunk-functions would bring benefit in terms of cost and performance. We will also investigate to what extent splitting monoliths can be automatized in order to FaaSify them. Finally, this thesis will explore existing scheduling approaches and their applicability in decision making where each chunk-function should be deployed. |
|Tasks| 1. Develop function-fission and FaaSifier. <br> 2. Develop a profiler for chunk-function execution on various providers. <br> 3. Integrate automatic deployer for various FaaS providers (e.g. TerraForm, Serverless Framework, GoDeploy, TestOps).<br> 4. Develop an optimization algorithm that creates a Pareto-optimal chunk functions <br>5. Evaluate FissionLess with some real life examples.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs, git.|
| Related work | 1. (`Automatic function packaging and deployment`) R. Cordingly, H. Yu, V. Hoang, Z. Sadeghi, D. Foster, D. Perez, R. Hatchett, and W. Lloyd. "The Serverless Application Analytics Framework: Enabling Design Trade-off Evaluation for Serverless Software." In 2020 21st ACM/IFIP International Middleware Conference: 6th International Workshop on Serverless Computing (WoSC'20). 2020, [SAAF](https://github.com/wlloyduw/SAAF). This tools can be used for wrappers and deployment scripts for various programming languages and FaaS providers. <br> 2. (`Node.js FaaSifier`) S. Ristov, S. Pedratscher, J. Wallnöfer, and T. Fahringer, “DAF: Dependency-Aware FaaSifier for Node.js Monolithic Applications,” in IEEE Software, doi: 10.1109/MS.2020.3018334, [DAF](https://github.com/qngapparat/daf).<br> 3. (`Automatic function deployment`) [Terraform](https://www.terraform.io/).<br> 4. (`Automatic function deployment`) [Serverless](https://www.serverless.com/).<br>  5. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking.|
---

## *xAFCL2* (xAFCLStream)

| Title | ***xAFCL2*: A microservices-based serverless workflow management system in Federated FaaS** |
| ----- | ----- | 
| Student | Thomas Oberroither | 
| Status | Requirements analysis | 
| Description |  The existing xAFCL serverless workflow management system will be migrated on a new platform based on microservices, including <br> - *workflow parser(s)* microservice(s), (AFCL or Step Functions.) <br> - *static scheduler(s)* service(s) (e.g., random, FaaSt, etc.); <br> - *invoker service* to run functions across multiple providers; <br> - *deployer service* to deploy functions across multiple providers; <br> - *resilience service* (e.g., for fault tolerance); <br> - *monitoring service* (status of each function), <br> - *dynamic scheduler* before execution, still check the status of cloud regions, etc. <br> The system should support both synchronous and asynchronous serverless workflows, as well as multiple serverless workflows simulatenaously.   
|Tasks| 1. Develop the core microservices (parser, invoker, monitor, resilience). <br> 2. Develop at least one scheduler microservice. <br> 3. Integrate automatic deployer for various FaaS providers (e.g. TerraForm, Serverless Framework, GoDeploy, TestOps).<br> 4. Evaluate latencies of the system. <br> 5. Evaluate the system with state-of-the-art.|
| Theoretical skills | Cloud Computing, Serverless. | 
| Practical skills | Programming languages, Cloud APIs.|
| Related work | 1. Ideally the student attended the course "Serverless Cloud Automation Application" SS23. <br> 2. Books regarding microservice patterns.<br> 3. *xAFCL* enactment engine with integrated simulator SimLess [*xAFCL EE*](https://doi.org/10.1109/TSC.2021.3128137).<br> 4. Various FaaS tools on our github organization [*FaaS Tools*](https://github.com/FaaSTools), such as GoDeploy and TestOps for automatic deployment and benchmarking.|
---


##  *MOStoreLess*

| Title | ***MOStoreLess*: Multi-objective data-aware scheduler in federated storage** |
| - | - | 
| Student | Thomas Wurzer | 
| Status | Evaluation | 
| Description | The aim of this master thesis is create a multi-objective data-aware scheduler that aims to minimize the overall makespan and cost of an AFCL serverless workflow in federated FaaS using federated storage. *MOStoreLess* analyzes ephemeral data transfers between functions of the workflow and considers network locality, both for cost and round trip times. ||
---

##  *CORE*

| Title | ***CORE*: Code Once, Run Everywhere. Engineering serverless workflow applications with high-level of abstraction** |
| - | - | 
| Student | Thomas Larcher | 
| Status | Defensio | 
| Description | All cloud providers offer SDKs to easily code applications with their services. While on the one hand, these SDKs simplify developers' effort, they lock users to use other cloud services from the same cloud provider. Such codes (e.g., serverless functions), are neither *portable* (to migrate them on another cloud provider), nor *interoperable* (switch cloud service from another cloud provider). This vendor lock-in prevents users to switch the same service from other providers or to mix services from arbitrary providers. For instance, one cloud provider may reduce storage price, while another cloud provider may introduce more accurate OCR service for preferred language. To bridge this gap, this master thesis introduces CORE (Core Once Run Everywhere), an abstraction library that allows developers to code portable functions that can use interoperable cloud services within AFCL serverless workflows (text2speech and OCR). Moreover, heuristics will be researched to select the appropriate service based on user objectives.||
---


##  *AccessLess*

| Title | ***AccessLess*: Data-aware scheduler in federated FaaS** |
| - | - | 
| Student | Mika Hautz | 
| Status | Evaluation | 
| Description | The aim of this master thesis is create a data-aware scheduler that aims to minimize the overall makespan of an AFCL serverless workflow in federated FaaS. *AccessLess* analyzes ephemeral data transfers between functions of the AFCL workflow and considers network locality. Unlike the related work, which schedules functions only, *AccessLess* schedules where ephemeral data should be stored in federated FaaS.||
---



# Closed master theses

1. "ML-based profiling of serverless functions with federated storage", Philipp Gritsch, SS2023 [details](./closed/MLProfileLess.md)
1. "*CrossFlow*: Cross-layered resource management in Cloud continuum", Ahmet Aspir, WS2022 [details](./closed/CrossFlow.md)
1. "*AFCL-Sched*: Optimal execution of FCs across multiple FaaS systems", Christian Hollaus, SS2022 [details](./closed/AFCL-Sched.md).
1. "AFCL Environment - Development and Scalable Execution of Portable Function Choreographies Across Multiple Serverless Cloud Platforms", Stefan Pedratscher, SS2021 [details](./closed/AFCLEnvironment.md).
1. "VolatileSim: A simulation framework for cloud volatile resources", Christoph Schöpf, SS2020, `Among top four master theses for 2020` at the institute.
1. "Distributed GPGPU on Cloud GPU Clusters", Martin Schuchardt, SS2019.


Details for closed master theses can be found [here](./closed/README.md).



----


# Milestones for a successful master thesis

- Requirements analysis
- Review the related work and detect their weaknesses
- System architecture
- Development
- Evaluation
- Finalizing the master thesis
- Defensio
- `Farewell party` :blush:


# Contact

If you need any additional information, or have your own idea from the aforementioned research tracks, please do not hesitate to contact me. 

My topics for bachelor theses may be found [here](https://github.com/sashkoristov/bachelor-theses), which could also be adapted as master theses.