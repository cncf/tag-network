# CNCF Service Mesh Working Group

Primary Author(s): [Lee Calcote](https://twitter.com/lcalcote)

Reviewed and Contributed to by: 

## Introduction

Service meshes are a cloud native technology that are quickly becoming ubiquitiuos. There are a great number of service meshes available as open and closed source offerings today.

## Initiatives

The CNCF Service Mesh Working Group has a number of initiatives, which share some common goals. See the working group [overview deck](https://docs.google.com/presentation/d/1mDE9K8OJ3lyl4GN98Ja3c9ATGWS4rByRtCPIKcoc7LY/edit?usp=sharing).

**Commonal goals across initiatives**

1. Use of CNCF labs for at-scale testing
1. Ongoing publication of initiative's results
   - As the service mesh ecosystem evolves, published information from these initiatives will be updated.

### Service mesh abstractions

Because it's a multi-mesh world, there are a number of service mesh abstractions that have emerged. Currently, three in total.

1. [SMI](https://smi-spec.io) - A standard interface for service meshes on Kubernetes.
1. [SMP](https://smp-spec.io) - A standard for describing and capturing service mesh performance.
1. Hamlet - A set of API standards for enabling service mesh federation.

### Active Initiatives

- [Service Mesh Interface Conformance](https://meshery.io/features/service-mesh-interface-conformance) - The scope of this initiative includes all service mesh projects participating in the Service Mesh Interface specification. [Meshery](https://meshery.io) is the service mesh conformance tool. See the project's [design specfiication](https://docs.google.com/document/d/1HL8Sk7NSLLj-9PRqoHYVIGyU6fZxUQFotrxbmfFtjwc/edit?usp=sharing).
- [Service Mesh Performance](https://smp-spec.io) -Directly enables capturing details of infrastructure capacity, service mesh configuration, and workload metadata.
- [Distributed Performance Analysis](http://layer5.io/projects/distributed-performance-testing) -
Focuses on the fact that distributed systems require distributed analysis. Distributed load testing offers insight into system behaviors that arguably more accurately represent real world behaviors of services under load as that load comes from any number of sources. This project integrates [Nighthawk](https://github.com/envoyproxy/nighthawk) and Meshery.
- Service Mesh Patterns - A collection of curated deployment models and common best practices of using service meshes.

## Communications

- Slack Channel ([#sig-network](https://app.slack.com/client/T08PSQ7BQ/CMG237Z5Z))
- Join [SIG-Network](mailto:sig-network@lists.cncf.io) mailer at [lists.cncf.io](https://lists.cncf.io)
- Repo: [https://github.com/cncf/sig-network](https://github.com/cncf/sig-network)
- Meetings: 
  - Time: Network SIG meets the 1st and 3rd Thursday of every month at 11am Pacific (here's [a link](https://goo.gl/eyutah) to a public Google calendar that you can subscribe to).
  - Location: Zoom - [https://zoom.us/my/cncfsignetwork](https://zoom.us/my/cncfsignetwork)
  - [Meeting Minutes](https://docs.google.com/document/d/18hYemFKK_PC_KbT_TDBUgb0rknOuIhikkRxer4_bv4Q/edit#)
