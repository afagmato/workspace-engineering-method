# Workspace Engineering Method (WEM)

> Design. Build. Evolve.

Workspace Engineering Method (WEM) is a technology-independent engineering method for designing, building and evolving sustainable software systems.

**WEM 1.1.0 — Released**

## What is WEM?

WEM provides a shared method for making engineering decisions explicit, shaping architecture before implementation and preserving knowledge as systems evolve. It focuses on engineering responsibilities rather than prescribing languages, frameworks, platforms or AI providers.

The canonical definition of the method is maintained in [WEM.md](WEM.md).

## Current Status

| | |
| --- | --- |
| Version | 1.1.0 |
| Status | Released |

WEM 1.1.0 introduces proportional Work Package and Milestone delivery under Accepted `WEM-ADR-009`. It completed coherence review and received explicit Project Owner release approval on 2026-10-27. The immutable `v1.0.0` tag remains available as the preceding release.

WEM 1.1.0 contains these updated normative components:

| Component | Candidate version |
| --- | --- |
| `WEM.md` | 1.1.0 — Released |
| `specifications/ADR_SPECIFICATION.md` | 1.1.0 — Released |
| `specifications/AGENT_COLLABORATION.md` | 1.1.0 — Released |

The Project Charter, Engineering Principles and Repository Blueprint remain unchanged at Version 1.0.0 and are normative dependencies of the candidate.

## Core Idea

WEM offers a concise way to orient engineering work across five connected concerns:

**Thinking → Architecture → Implementation → Evolution → Knowledge**

This is an explanatory summary. See [WEM.md](WEM.md) for the maintained engineering lifecycle and its normative definition.

## Start Here

| Document | Responsibility |
| --- | --- |
| [WEM.md](WEM.md) | Core engineering method |
| [PROJECT_CHARTER.md](PROJECT_CHARTER.md) | Mission, scope and authority |
| [ENGINEERING_PRINCIPLES.md](ENGINEERING_PRINCIPLES.md) | Permanent Engineering Principles |
| [specifications/ADR_SPECIFICATION.md](specifications/ADR_SPECIFICATION.md) | Architecture Decision Record governance |
| [specifications/REPOSITORY_BLUEPRINT.md](specifications/REPOSITORY_BLUEPRINT.md) | Repository architecture |
| [specifications/AGENT_COLLABORATION.md](specifications/AGENT_COLLABORATION.md) | Human and AI collaboration governance |
| [decisions/](decisions/) | Architecture Decision Records |
| [documentation/wem-presentacio.pdf](documentation/wem-presentacio.pdf) | WEM overview presentation |

## Adoption

Projects adopt WEM as a methodology, not as a technical dependency. WEM 1.1.0 Released provides the current stable version reference for adoption while each adopting project retains responsibility for its own architecture, implementation, risks and outcomes.

A project adopting this release can identify it as:

```text
Methodology: WEM 1.1.0 — Released
```

See [PROJECT_CHARTER.md](PROJECT_CHARTER.md) and [WEM.md](WEM.md) for the maintained adoption responsibilities and method definition.

## Repository Responsibility

This repository contains maintained engineering knowledge for WEM. It does not contain functional product implementations.

The authoritative boundaries are defined by [ENGINEERING_PRINCIPLES.md](ENGINEERING_PRINCIPLES.md) and [specifications/REPOSITORY_BLUEPRINT.md](specifications/REPOSITORY_BLUEPRINT.md).

## Human and AI Collaboration

WEM supports role-based collaboration between human and AI participants while preserving human accountability. WEM 1.1.0 organizes delivery through bounded Work Packages and Milestones so that human gates correspond to material decisions rather than mechanical phase boundaries. The maintained roles, authority boundaries and collaboration workflow are defined in [specifications/AGENT_COLLABORATION.md](specifications/AGENT_COLLABORATION.md).

## License

Workspace Engineering Method repository content is licensed under the Creative Commons Attribution-ShareAlike 4.0 International Public License, subject to the scope and exclusions defined by [WEM-ADR-004](decisions/WEM-ADR-004.md).

Requested attribution:

```text
Workspace Engineering Method (WEM), by Arç Fontrodona
```

See the root [LICENSE](LICENSE) for the official legal text.

## Specification Authority

This README is a non-normative repository interface. If a summary here conflicts with a canonical WEM specification or Accepted ADR, the canonical source governs.
