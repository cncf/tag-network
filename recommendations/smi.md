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
- Maintainers: x ( )
- Releases: [x](https://github.com/deislabs/smi-spec/releases)
- Commits: 109
- Contributors: 17
- Integrations:
  - [Consul](https://consul.io)
  - [Istio](https://istio.io)
  - [Linkerd](https://linkerd.io)
  - [Meshery](https://meshery.io)
  - [Prometheus](https://prometheus.io)
- Adopters: x current public adopters ()
- Presentation:
  - []()
  
## Future Plans

# Project Scope

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

Kubernetes Event-driven Autoscaling (KEDA)'s mission is to make application autoscaling simple allowing Kubernetes users to focus on their workloads, not the scaling infrastructure. As part of that mission, we want to support as many customers as possible by being vendor neutral and are open to scale on any system.

The Kubernetes Event-driven Autoscaling (KEDA) project does not want to reinvent the wheel but build on standards instead and is complimentary to Kubernetes. Next to that, we have support for CNCF projects like Prometheus and NATS by providing scalers for them as well and package our product as a Helm chart (2.x & 3.x) which is available on Helm Hub. Lastly, we are vendor-neutral by supporting all major clouds and open-source technologies like Redis.

While the scaling features of Kubernetes Event-driven Autoscaling (KEDA) are important, we are a strong believer of making the product itself operable as well. By using Operator SDK we also want to allow operators to efficiently manage the infrastructure necessary to run Kubernetes Event-driven Autoscaling (KEDA) and are planning to provide a better operational experience as a whole by providing a CLI, dashboard, etc.

Security is one of our main focuses and we will keep on investing in that - This is why pod identity has been one of our main focuses for 1.0 and will continue to support more identity providers over time.

## Value-add to the CNCF ecosystem

CNCF provides a vendor neutral home for service mesh interoperability.


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
