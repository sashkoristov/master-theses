##  *MLProfileLess*

| Title | **ML-based profiling of serverless functions with federated storage** |
| - | - | 
| Student | Philipp Gritsch | 
| Status | Defensio | 
| Description | Scientific workloads, which are represented as serverless workflows, benefit from federated clouds in terms of performance. However, such heterogeneous environments burden the decision of the optimal configuration. The existing simulators mostly utilize either mathematical models or machine-learning based methods to predict costs or runtime of serverless functions., Unfortunately, in general, they use federation of serverless functions across multiple regions of various cloud providers, but consider a single storage, which often generates huge latency for ephemeral data transfer between functions. In order to bridge this gap, this master thesis evaluates to what extent existing machine learning methodologies can be used to profile scientific workflows and determines the optimal storage setup for different intermediate data characteristics in federated storage. The outcome is a model, which estimates the round trip time of serverless functions on different providers, regions and storages. The model showed up to 90 % accuracy for running a workflow on "unseen" resources (both for functions and storage regions), which is similar as the state-of-the-art simulators, while reducing the cost for configuration setup by 26 %.||
---
