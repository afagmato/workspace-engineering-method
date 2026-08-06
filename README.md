# Workspace Engineering Method (WEM)

> Design. Build. Evolve.

Workspace Engineering Method (WEM) is a technology-independent engineering method for designing, building and evolving sustainable software systems.

**WEM 1.0.0 — Draft**

## What is WEM?

WEM provides a shared method for making engineering decisions explicit, shaping architecture before implementation and preserving knowledge as systems evolve. It focuses on engineering responsibilities rather than prescribing languages, frameworks, platforms or AI providers.

The canonical definition of the method is maintained in [WEM.md](WEM.md).

## Current Status

| | |
| --- | --- |
| Version | 1.0.0 |
| Status | Draft |

WEM remains under development. Its specification ecosystem has not yet completed the final cross-document coherence review required for release.

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

Projects adopt WEM as a methodology, not as a technical dependency. Because WEM remains Draft, the current specification is suitable for evaluation rather than stable release adoption.

A project evaluating the current specification can identify it as:

```text
Methodology: WEM 1.0.0 — Draft
```

See [PROJECT_CHARTER.md](PROJECT_CHARTER.md) and [WEM.md](WEM.md) for the maintained adoption responsibilities and method definition.

## Repository Responsibility

This repository contains maintained engineering knowledge for WEM. It does not contain functional product implementations.

The authoritative boundaries are defined by [ENGINEERING_PRINCIPLES.md](ENGINEERING_PRINCIPLES.md) and [specifications/REPOSITORY_BLUEPRINT.md](specifications/REPOSITORY_BLUEPRINT.md).

## Human and AI Collaboration

WEM supports role-based collaboration between human and AI participants while preserving human accountability. The maintained roles, authority boundaries and collaboration workflow are defined in [specifications/AGENT_COLLABORATION.md](specifications/AGENT_COLLABORATION.md).

## License

Workspace Engineering Method repository content is licensed under the Creative Commons Attribution-ShareAlike 4.0 International Public License, subject to the scope and exclusions defined by [WEM-ADR-004](decisions/WEM-ADR-004.md).

Requested attribution:

```text
Workspace Engineering Method (WEM), by Arç Fontrodona
```

See the root [LICENSE](LICENSE) for the official legal text.

## Specification Authority

This README is a non-normative repository interface. If a summary here conflicts with a canonical WEM specification or Accepted ADR, the canonical source governs.
