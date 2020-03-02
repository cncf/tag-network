# CNCF SIG Sandbox Project Request - Service Mesh Interface (SMI)

## Acceptance to CNCF Sandbox

**Authors:** Lee Calcote (@lcalcote)

## Background

**_Link to TOC PR_**

https://github.com/cncf/toc/issues/337

**_Link to Presentation_**

Recording: SIG Network meeting (Jan 16, 2020)
https://youtu.be/1eOrDXUrS-k

Slides: https://docs.google.com/presentation/d/11MssWPEyolaZwmJfg7sKE2BwSnGsmrXR3tdCscwf-WA/edit?usp=sharing

**_Link to GitHub project_**

https://github.com/deislabs/smi-spec

## Project Overview

The Service Mesh Interface (SMI) is a specification for service meshes that run on Kubernetes. 

It defines a common standard that can be implemented by a variety of providers. 

This allows for both standardization for end-users and innovation by providers of Service Mesh Technology. 

It enables flexibility and interoperability.

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
- Maintainers: x (5 Microsoft, 2 Red Hat, 1 Codit)
- Releases: [3](https://github.com/kedacore/keda/releases)
- Commits: 109
- Contributors: 17
- Integrations:
  - [Istio](https://istio.io)
  - [Consul](https://consul.io)
  - [Linkerd](https://linkerd.io)
  - [Meshery](https://meshery.io)
  - [Prometheus](https://prometheus.io/)
- Adopters: x current public adopters ()
- Presentation:
  - [KubeCon 2019 NA: KEDA: Event Driven and Serverless Containers in Kubernetes - Jeff Hollan, Microsoft](https://www.youtube.com/watch?v=ZK2SS_GXF-g)
  - [CloudBrew 2019: Event-driven computing with Kubernetes](https://www.cloudbrew.be/2019/#session-event-driven-computing-with-kubernetes)
  - Serverless Practitioners Summit 2020: Application Autoscaling Made Easy With Kubernetes Event-Driven Autoscaling (KEDA)

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

The Kubernetes Event-driven Autoscaling (KEDA) project does not want to reinvent the wheel but build on standards instead and is complimentary to Kubernetes.

From the beginning intent was open and community driven (open community standups, MIT License, non-Microsoft branded). 

CNCF provides a vendor neutral home for key serverless capability.


## Alignment with other CNCF projects

SMI augments and enhances many CNCF projects by adding event driven scale, including:

- Kubernetes itself (helping drive features back into things like the HPA / Cluster autoscaler)
- Virtual Kubelet
- NATS
- Prometheus
- Strimzi
- Helm

## Anticipated use cases

- Serverless container and FaaS scaling
- Data processing pipelines
- Application scaling
- Batch processing

## Alignment with SIG Reference Model

SIG Network

## High level architecture

KEDA performs two key roles within Kubernetes. First, it acts as an agent to activate and deactivate a deployment to scale to and from zero on no events. This is one of the primary roles of the keda-operator container that runs when you install KEDA.

Second, KEDA acts as a Kubernetes metrics server to expose rich event data like queue length or stream lag to the horizontal pod autoscaler to drive scale out. It is up to the deployment to then consume the events directly from the source. This preserves rich event integration and enables gestures like completing or abandoning queue messages to work out of the box. The metric serving is the primary role of the keda-operator-metrics-apiserver container that runs when you install KEDA.

![KEDA Architecture](https://i.imgur.com/lBVkWsH.png)

# Formal Requirements

Sponsors: TBD

# CNCF IP Policy

- list of package dependencies (and their license)

# Other Considerations

## Cloud Native

**SMI** aligns closely with the Cloud Native Computing Foundation (CNCF) mission, and is an important piece for serverless capabilities on Kubernetes. Our hope is to align and help foster and grow an inclusive community with the CNCF.

## Project and Code Quality

- CI/CD: GitHub Actions with nightly e2e tests (live cluster, live event sources) and tests per PR.
- Deployment: Helm chart, operator SDK, or local script. ([docs](https://keda.sh/deploy/))
- Docs: Built with Hugo and uses Netlify to generate previews in PRs
- Design documents: https://keda.sh/concepts/overview/
- Benefit from CNCF:
  - Vendor neutral home for this serverless capabilities
  - Enhances other CNCF projects with serverless event-driven scale
  - Important capability for serverless workloads within open governance / CNCF.
