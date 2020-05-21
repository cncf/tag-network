# SIG Network Chaos Mesh Project Review

# Background

**[TOC PR](https://github.com/cncf/toc/pull/367)** 

**[Presentation Slide](https://docs.google.com/presentation/d/115QvSCnT6ROwwV1lK-R10d4MW54fQhtVM2uZDGscpEk/edit#slide=id.g80f082b201_0_0)**

**[Presentation Link](https://www.youtube.com/watch?v=SuRUtlSQbm4)**

**[GitHub](https://github.com/pingcap/chaos-mesh)**

**Name of Project:** Chaos Mesh  

**Project Goal:**

Chaos Mesh is a versatile Chaos Engineering platform that orchestrates chaos experiments on Kubernetes environments. It features all-around fault injection methods for complex systems on Kubernetes, covering faults in Pod, network, file system, and even the kernel.

Chaos Mesh was originated from the internal chaos engineering platform at PingCAP to ensure the resilience of TiDB, its distributed database system. As the system evolves and testing requirements multiply, the team realized that they need an easy to use, scalable and universal chaos testing platform. The combination of chaos and Kubernetes became the natural choice.  Chaos Mesh uses CRD to define chaos objects, which makes it naturally integrate with the Kubernetes ecosystem. 

At the current stage, it supports the following fault injection types:

- pod-kill: Simulates Kubernetes Pods being killed
- pod-failure: Simulates Kubernetes Pods being continuously unavailable
- container-kill: Simulates Kubernetes Pod’s container being killed
- network-delay: Simulates network delay
- network-loss: Simulates network packet loss
- network-duplication: Simulates network packet duplication
- network-corrupt: Simulates network packet corruption
- network-partition: Simulates network partition
- I/O delay: Simulates file system I/O delay
- I/O errno: Simulates file system I/O errors
- Time skew: Simulates time jumping forward or backward

Besides the versatile chaos types, it also offers Chaos Dashboard (under development), a visualized panel that shows the impacts of chaos experiments on the online services of the system, which makes chaos tests easily observable and manageable. 

**Current Status:**

* Stars: 1700+
* Contributors: 33
* Commits: 330+
* Forks: 128
* Releases: 1 (V1.0 coming soon)

** Future Plans: ** 

**Roadmap**:

See [https://github.com/pingcap/chaos-mesh/blob/master/ROADMAP.md](https://github.com/pingcap/chaos-mesh/blob/master/ROADMAP.md)


## Project Scope 

## Clear project definition
Does the project have a clear and well defined scope?

SIG Network agrees that Chaos Mesh has a well defined scope. 

## Value-add to the CNCF ecosystem

Does the project have a clear value add to the current project ecosystem? How does it relate to other projects with overlapping capabilities? 

ChaosMesh is a universally applicable Chaos Engineering platform and would allow for further resiliency in CNCF projects. 


## Alignment with other CNCF projects
Does the project align and actively collaborate with other CNCF projects? 

##### Put other projects here ########

## Alignment with SIG-Network


## High level architecture:
https://docs.google.com/presentation/d/115QvSCnT6ROwwV1lK-R10d4MW54fQhtVM2uZDGscpEk/edit#slide=id.g80deb1f634_0_331 

# Formal Requirements

Document that the project fulfills the requirements as documented in the (CNCF graduation criteria)[https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc]
Sandbox Stage
As ChaosMesh is submitted at the sandbox stage it needs to meet the following criteria.

*   ChaosMesh is requesting 3 TOC sponsors
*   ChaosMesh will adopt the CNCF [Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md) -- this has not yet been done 
*   ChaosMesh will adhere to CNCF [IP Policy](https://github.com/cncf/foundation/blob/master/charter.md#11-ip-policy) (including trademark transferred)

## CNCF IP Policy 

External dependencies (including licenses):

Apache License 2.0:

github.com/containerd/containerd
github.com/docker/docker
github.com/ethercflow/hookfs
github.com/go-logr/logr
github.com/grpc-ecosystem/go-grpc-middleware
github.com/grpc-ecosystem/go-grpc-prometheus
github.com/oklog/run
github.com/prometheus/client_golang
github.com/vishvananda/netlink
github.com/vishvananda/netns
github.com/kubernetes-sigs/controller-runtime
MIT:

github.com/ghodss/yaml
github.com/jmoiron/sqlx
github.com/onsi/ginkgo
github.com/onsi/gomega
github.com/robfig/cron
github.com/unrolled/render
Mozilla Public License 2.0:

github.com/go-sql-driver/mysql
BSD 3-Clause:

github.com/golang/protobuf
github.com/gorilla/mux
BSD:

github.com/hanwen/go-fuse

# Other Considerations


## Cloud Native

**_Does the project meet the definition of Cloud Native?  The CNCF charter states:_**

_“Cloud native technologies empower organizations to build and run scalable applications in modern, dynamic environments such as public, private, and hybrid clouds. Containers, service meshes, microservices, immutable infrastructure, and declarative APIs exemplify this approach._

_“These techniques enable loosely coupled systems that are resilient, manageable, and observable. Combined with robust automation, they allow engineers to make high-impact changes frequently and predictably with minimal toil.”_

From the Chaos Mesh Team: 
We believe Chaos Mesh is one of the essential enablements to this mission, and it’s also a great addition to the sandbox project scope. By covering comprehensive fault injection methods in Pod, network, file system, and even the kernel, Chaos Mesh aims at providing a neutral, universal Chaos Engineering platform that enables cloud-native applications to be as resilient as they should be. Chaos Mesh uses CRD to define chaos objects, making it naturally integrated with the Kubernetes ecosystem. In addition, it integrates several other projects in the cloud-native ecosystem, such as Helm, Prometheus, and Grafana.

## Project and Code Quality

**_Are there any metrics around code quality?  Are there good examples of code reviews? Are there enforced coding standards?_**

### Code Quality
https://codecov.io/gh/pingcap/chaos-mesh 

### Code Review
https://codecov.io/gh/pingcap/chaos-mesh 

### Coding Standards

https://github.com/pingcap/chaos-mesh/wiki/Weekly-Update---2020


**_What is the CI/CD system?  Are there code coverage metrics?  What types of tests exist?_**

Chaos Mesh uses in-house Jenkins CI cluster for integration tests. We plan to use CNCF test cluster to automatically run stability tests and performance tests in the future.

Website: https://github.com/pingcap/chaos-mesh

Documentation: https://github.com/pingcap/chaos-mesh/wiki

Release methodology and mechanics:

This is currently being defined. Releases every few months with RC process.

### Code Coverage

**_Has a security assessment

**_Has a security assessment by the security SIG been done? If not, what is the status/progress of the assessment?_**

No assessment has been done.

# SIG Network recommendation:

SIG Network recommends inclusion of Chaos Mesh at sandbox level, providing that there is adoption of CNCF's code of conduct 
