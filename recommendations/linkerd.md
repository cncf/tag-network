# SIG Network Linkerd Project Review

## Background

- [TOC PR](https://github.com/cncf/toc/pull/616)
- [Presentation slide](https://docs.google.com/presentation/d/1qseWDYWD4KzYFhb4bcp8WuDPYFVwB8sYeNnjCsgDUOw/edit)
- [Presentation recording](https://www.youtube.com/watch?v=R5F8l9ursBk#t=50m22)
- [GitHub org](https://github.com/linkerd) (specifically, [linkerd2](https://github.com/linkerd2/linkerd2) and [linkerd2-proxy](https://github.com/linkerd2/linkerd2) repos).

## Project Goal

[Linkerd](https://linkerd.io) is an ultralight, security-first service mesh for Kubernetes. Linkerd adds critical security, observability, and reliability features to your Kubernetes stack with no code change required.

Linkerd features a [control plane](https://github.com/linkerd/linkerd2) built in Go and a [data plane "micro-proxy"](https://github.com/linkerd/linkerd2-proxy) written in Rust. The original [1.x line](https://github.com/linkerd/linkerd) of Linkerd, written in Scala, is currently in maintenance mode.

Linkerd has 10,000+ GitHub stars and 150+ contributors across the various repos in the [Linkerd GitHub org](https://github.com/linkerd/), and 5000+ users registered for the [Linkerd community Slack](https://slack.linkerd.io/). Linkerd was [open sourced in early 2016](https://linkerd.io/2016/02/18/linkerd-twitter-style-operability-for-microservices/)
and [joined the CNCF as its fifth-ever project in January 2017](https://www.cncf.io/blog/2017/01/23/linkerd-project-joins-cloud-native-computing-foundation/).
It currently powers production systems around the world, including at
Nordstrom, H-E-B, Elkjop, Microsoft, HP, and many more.

## Metrics

- Stars: 10,000+
- Contributors: 200+
- Commits: 5,000+
- Forks: 1,500+
- Releases: 250+

## Roadmap

Linkerd's project [roadmap](https://github.com/linkerd/linkerd2/blob/main/ROADMAP.md) is publicly published and supplemented by milestones and associated issues in GitHub.

## Project scope

### Clear project definition

_Does the project have a clear and well defined scope?_

SIG Network agrees that Linkerd has a well defined scope. See Linkerd's [Design Principles](https://linkerd.io/design-principles/) for a characterization of project scope.

### Value-add to the CNCF ecosystem

_Does the project have a clear value add to the current project ecosystem? How does it relate to other projects with overlapping capabilities?_

Linkerd's reliability, observability, and security features provide a clear
value to Kubernetes adopters. Linkerd "plays nice" with many other ecosystem
projects. There is overlap in the service mesh ecosystem including with other
CNCF projects, but in the view of SIG Networking this is a healthy situation.

### Alignment with other CNCF projects

_Does the project align and actively collaborate with other CNCF projects?_

Linkerd collaborates with other CNCF projects, including:

- Prometheus (shipped as part of its [viz extension](https://linkerd.io/2.10/tasks/extensions/) extension)
- Jaeger (shipped as part of its [jaeger extension](https://linkerd.io/2.10/tasks/extensions/) extension)
- Contour (documented [ingress integration](https://linkerd.io/2.10/tasks/using-ingress/#contour))
- Ambassador / Emissary-ingress (documented [ingress integration](https://linkerd.io/2.10/tasks/using-ingress/#ambassador))
- Service Mesh Interface [via CRD](https://linkerd.io/2019/05/24/linkerd-and-smi/) with current [conformance published](https://meshery.io/smi).
- [Service Mesh Performance](https://smp-spec.io) via Meshery

And, of course, Linkerd is highly coupled to Kubernetes.

## Alignment with SIG-Network

[High level architecture](https://docs.google.com/presentation/d/1qseWDYWD4KzYFhb4bcp8WuDPYFVwB8sYeNnjCsgDUOw/edit#slide=id.g5adfc000d8_5_99)

## Formal Requirements

_Document that the project fulfills the requirements as documented in the [CNCF
graduation
criteria](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)_

#### Have committers from at least two organizations

Linkerd does _not_ currently have maintainers from two organizations. However,
the [Linkerd graduation proposal](https://github.com/cncf/toc/pull/616/files),
states:

> Throughout its history, Linkerd has always been open to contributors and
> maintainers from anywhere in the world. Linkerd has [publicly committed to
> open
> governance](https://linkerd.io/2019/10/03/linkerds-commitment-to-open-governance/)
> and features a [steering
> committee](https://linkerd.io/2021/01/28/announcing-the-linkerd-steering-committee/)
> comprising end-users.

While Linkerd does not meet the letter of this requirement, it is the opinion of SIG Network that the project upholds this requirement in spirit.

#### Have achieved and maintained a Core Infrastructure Initiative Best Practices Badge.

Per the proposal, The Linkerd project has achieved a [Core Infrastructure
Initiative Best Practices Badge](https://bestpractices.coreinfrastructure.org/en/projects/4629).

#### Have completed an independent and third party security audit with results published of similar scope and quality as the following example (including critical vulnerabilities addressed): https://github.com/envoyproxy/envoy#security-audit and all critical vulnerabilities need to be addressed before graduation.

Per the proposal, Linkerd completed a CNCF-sponsored [Cure53 security
audit](https://github.com/linkerd/linkerd2/blob/main/SECURITY_AUDIT.pdf) in
June 2019. The audit identified two minor issues in the dashboard, both of
which were promptly fixed. Further audits are scheduled for this year.

#### Explicitly define a project governance and committer process. This preferably is laid out in a GOVERNANCE.md file and references an OWNERS.md file showing the current and emeritus committers.

Yes, per the proposal:

- Project governance:
  [GOVERNANCE.md](https://github.com/linkerd/linkerd2/blob/main/GOVERNANCE.md)
- Steering committee charter:
  [STEERING.md](https://github.com/linkerd/linkerd2/blob/main/STEERING.md)
- Maintainers and Steering Committee members:
  [MAINTAINERS.md](https://github.com/linkerd/linkerd2/blob/main/MAINTAINERS.md)

#### Have a public list of project adopters for at least the primary repo (e.g., ADOPTERS.md or logos on the project website). For a specification, have a list of adopters for the implementation(s) of the spec.

Yes, [ADOPTERS.md](https://github.com/linkerd/linkerd2/blob/main/ADOPTERS.md).

## CNCF IP Policy

External dependencies (including licenses):

As of 3/25/2021, see the report here:

https://gist.github.com/olix0r/38759123e08dfe5b35c4b1dd6cc52da5

## Other Considerations

### Alignment with Cloud Native

_Does the project meet the definition of Cloud Native? The CNCF charter states:_

_“Cloud native technologies empower organizations to build and run scalable applications in modern, dynamic environments such as public, private, and hybrid clouds. Containers, service meshes, microservices, immutable infrastructure, and declarative APIs exemplify this approach._

_“These techniques enable loosely coupled systems that are resilient, manageable, and observable. Combined with robust automation, they allow engineers to make high-impact changes frequently and predictably with minimal toil.”_

Yes. Linkerd is a service mesh, one of the examples of cloud native
technologies in the definition above.

### Project and Code Quality

#### Are there any metrics around code quality? Are there good examples of code reviews? Are there enforced coding standards?

The Linkerd project maintains a strong history of code review, which is where
quality and standards are enforced. Some recent examples include:

https://github.com/linkerd/linkerd2/pull/5921
https://github.com/linkerd/linkerd2/pull/5829
https://github.com/linkerd/linkerd2/pull/5814
https://github.com/linkerd/linkerd2-proxy/pull/954
https://github.com/linkerd/linkerd2-proxy/pull/955

#### What is the CI/CD system? Are there code coverage metrics? What types of tests exist?

Linkerd uses a comprehensive suite of unit tests, integration tests, static
analysis, powered by GitHub actions. Almost all tests run on GitHub-provided
VMs, with minor exceptions (such as ARM build validation) that run on
CNCF-provided Equinix servers. See https://github.com/linkerd/linkerd2/actions for details.

A CNCF-sponsored fuzzing project with Ada Logics is underway.

Releases are also created via GitHub Actions and the workflows are available
in the same URL as above.

#### Has a security assessment by the security SIG been done? If not, what is the status/progress of the assessment?

Per the proposal, Linkerd completed a CNCF-sponsored [Cure53 security
audit](https://github.com/linkerd/linkerd2/blob/main/SECURITY_AUDIT.pdf) in
June 2019.

## SIG Network Findings and Recommendation

**Addressed Questions**

1. Published project scope - https://github.com/linkerd/rfc/issues/37
1. Roadmap clarification - https://github.com/linkerd/linkerd2/issues/6009
1. Linkerd mailing list for code of conduct issues? - https://github.com/linkerd/linkerd/wiki/Linkerd-code-of-conduct#moderation

**Open Questions**

1. 

**Recommendations**

1. We encourage participation in service mesh specification projects: SMI and SMP

<!-- SIG Network recommends promotion of Linkerd to graduated status. -->
