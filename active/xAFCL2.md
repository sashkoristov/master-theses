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
