# CNCF SIG Sandbox Project Request - Service Mesh Interface (SMI)

## Acceptance to CNCF Sandbox

**Authors:** Lee Calcote ([@lcalcote](https://twitter.com/lcalcote))

## Background

- **Proposal TOC PR**: [#337  ](https://github.com/cncf/toc/issues/337) 
- **Proposal Presentation**: SIG Network meeting recording ([Jan 16, 2020](https://youtu.be/1eOrDXUrS-k))
- **Proposal Slides**: [Project deck](https://docs.google.com/presentation/d/11MssWPEyolaZwmJfg7sKE2BwSnGsmrXR3tdCscwf-WA/edit?usp=sharing)
- **Link to GitHub project**: [deislabs/smi-spec](https://github.com/deislabs/smi-spec)

## Project Overview

The Service Mesh Interface (SMI) is a specification for service meshes that run on Kubernetes. 
It defines a common standard that can be implemented by a variety of providers. This allows for both standardization for end-users and innovation by providers of Service Mesh Technology. It enables flexibility and interoperability.

This specification consists of multiple APIs:

- [Traffic Access Control](https://github.com/deislabs/smi-spec/blob/master/traffic-access-control.md) - configure access to specific pods and routes based on the identity of a client for locking down applications to only allowed users and services.
- [Traffic Specs](https://github.com/deislabs/smi-spec/blob/master/traffic-specs.md) - define how traffic looks on a per-protocol basis. These resources work in concert with access control and other types of policy to manage traffic at a protocol level.
- [Traffic Split](https://github.com/deislabs/smi-spec/blob/master/traffic-split.md) - incrementally direct percentages of traffic between various services to assist in building out canary rollouts.
- [Traffic Metrics](https://github.com/deislabs/smi-spec/blob/master/traffic-metrics.md) - expose common traffic metrics for use by tools such as dashboards and autoscalers.

See the individual documents for the details. Each document outlines:

- Specification
- Possible use cases
- Example implementations
- Tradeoffs

## Current Status

__Mar 1, 2020__

- Stars: 424
- Forks: 35
- Maintainers: 11 (Microsoft, Buoyant, Layer5, HashiCorp)
- Releases: [2](https://github.com/deislabs/smi-sdk-go/releases)
- Commits: 109
- Contributors: 17
- Integrations:
  - [Consul](https://consul.io)
  - [Istio](https://istio.io)
  - [Linkerd](https://linkerd.io)
  - [Meshery](https://meshery.io)
  - [Prometheus](https://prometheus.io)
- Adopters: 8 current public adopters
  - [Buoyant](https://buoyant.io)
  - [Has
  - [Layer5](https://layer5.io)
  - [Solo](https://solo.io)
)
- Presentation/Blog:
  - [SMI: Developer Friendly APIs for Service Mesh](https://www.youtube.com/watch?v=KXTBqzqQ_1o)
  - [CNCF SIG Network: SMI Project Overview](https://youtu.be/1eOrDXUrS-k?t=2243)
  - [Supercharge Your Microservices CI/CD with Service Mesh Interface and Kubernetes](https://www.youtube.com/watch?v=SMoaem3UBag)
  - [Democratizing Service Mesh on Kubernetes](https://youtu.be/gDLD8gyd7J8)
  - [A Standard Interface for Service Meshes](https://layer5.io/blog/a-standard-interface-for-service-meshes)

  
## Future Plans

- Integration of traffic metrics into Kiala.
- Meshery as the SMI spec conformance tool.


# Project Scope

Kubernetes only. Lowest common denominator service mesh functionality.

## Project Goals

The goal of the SMI API is to provide a common, portable set of Service Mesh APIs which a Kubernetes user can use in a provider agnostic manner.

In this way people can define applications that use Service Mesh technology without tightly binding to any specific implementation.

## Project Non-Goals
It is a non-goal for the SMI project to implement a service mesh itself.

It merely attempts to define the common specification.

Likewise it is a non-goal to define the extent of what it means to be a Service Mesh, but rather a generally useful subset. 

If SMI providers want to add provider specific extensions and APIs beyond the SMI spec, they are welcome to do so. 

We expect that, over time, as more functionality becomes commonly accepted as part of what it means to be a Service Mesh, those definitions will migrate into the SMI specification.

## Alignment with CNCF mission
_-incomplete-_

## Value-add to the CNCF ecosystem

CNCF provides a vendor neutral home for service mesh interoperability.

_-incomplete-_

## Alignment with other CNCF projects

SMI interoperates with these CNCF projects:

- Kubernetes
- Linkerd
- Prometheus
- Helm

## Anticipated use cases

- [Traffic Access Control](https://github.com/deislabs/smi-spec/blob/master/traffic-access-control.md) - 
- [Traffic Specs](https://github.com/deislabs/smi-spec/blob/master/traffic-specs.md) - 
- [Traffic Split](https://github.com/deislabs/smi-spec/blob/master/traffic-split.md) - 
- [Traffic Metrics](https://github.com/deislabs/smi-spec/blob/master/traffic-metrics.md) - 

## Alignment with SIG Reference Model

[SIG Network](https://github.com/cncf/sig-network)

## High level architecture

_-architecture description here-_

_-architecture diagram here-_

# Formal Requirements

SIG Sponsors: Lee Calcote
TOC Sponsors: Matt Klein, Jeff Brewer, Michelle Noorali

# CNCF IP Policy

- list of package dependencies (and their license)

# Other Considerations

## Cloud Native

**SMI** aligns closely with the Cloud Native Computing Foundation (CNCF) mission, and facilitates service mesh interoperability. Our hope is to align and help foster and grow an inclusive community with the CNCF.

## Project and Code Quality

- CI/CD: CircleCI
- Deployment:
- Docs:
- Project Site:
- Design documents:
- Benefit from CNCF:
  - Vendor neutral home for service mesh abstraction between different projects and vendors.
  - Encouragement of open governance.

## Recommendation

**SIG Network's reflections and recommendation**

1. Move SMI repositories to new GitHub org
1. Relicense to Apache v2?
1. _-incomplete-_