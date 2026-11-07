# Workspace Engineering Method (WEM)

> Design. Build. Evolve.

Workspace Engineering Method (WEM) is a technology-independent engineering method for designing, building and evolving sustainable software systems.

**Latest release: WEM 1.3.0 — Released**

## What is WEM?

WEM provides a shared method for making engineering decisions explicit, shaping architecture before implementation and preserving knowledge as systems evolve. It focuses on engineering responsibilities rather than prescribing languages, frameworks, platforms or AI providers.

The canonical definition of the method is maintained in [WEM.md](WEM.md).

## Current Status

| | |
| --- | --- |
| Version | 1.3.0 |
| Status | Released |

WEM 1.3.0 adds project-neutral ASI semantics, durable release assurance evidence and automatic structural-validator adoption decisions during Project Initiation. It completed coherence review, independent technical review and received explicit Project Owner release approval on 2026-11-07.

WEM 1.3.0 contains these updated normative components:

| Component | Component version |
| --- | --- |
| `WEM.md` | 1.3.0 — Released |
| `PROJECT_CHARTER.md` | 1.1.0 — Released |
| `specifications/ADR_SPECIFICATION.md` | 1.2.0 — Released |
| `specifications/AGENT_COLLABORATION.md` | 1.2.0 — Released |
| `specifications/PROJECT_INITIATION.md` | 1.1.0 — Released |

The Engineering Principles and Repository Blueprint remain at their Released component versions and are normative dependencies of WEM 1.3.0.

## Core Idea

WEM offers a concise way to orient engineering work across five connected concerns:

**Thinking → Architecture → Implementation → Evolution → Knowledge → renewed Thinking**

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
| [specifications/PROJECT_INITIATION.md](specifications/PROJECT_INITIATION.md) | Automatic new-project initiation workflow |
| [documentation/quick-start.md](documentation/quick-start.md) | Concise non-normative adoption path |
| [templates/project-charter.md](templates/project-charter.md) | Minimal Project Charter starting structure |
| [templates/adr.md](templates/adr.md) | Minimal ADR starting structure |
| [examples/minimal-project.md](examples/minimal-project.md) | Small-project adoption example |
| [knowledge/wem-orchestrator-adoption-validation.md](knowledge/wem-orchestrator-adoption-validation.md) | First adopting-project validation record |
| [decisions/](decisions/) | Architecture Decision Records |
| [documentation/wem-presentacio.pdf](documentation/wem-presentacio.pdf) | WEM overview presentation |

## Adoption

Projects adopt WEM as a methodology, not as a technical dependency. WEM 1.3.0 Released provides the current stable version reference while each adopting project retains responsibility for its own architecture, implementation, risks and outcomes.

A project adopting this release can identify it as:

```text
Methodology: WEM 1.3.0 — Released
```

See [PROJECT_CHARTER.md](PROJECT_CHARTER.md) and [WEM.md](WEM.md) for the maintained adoption responsibilities and method definition.

## Repository Responsibility

This repository contains maintained engineering knowledge for WEM. It does not contain functional product implementations.

The authoritative boundaries are defined by [ENGINEERING_PRINCIPLES.md](ENGINEERING_PRINCIPLES.md) and [specifications/REPOSITORY_BLUEPRINT.md](specifications/REPOSITORY_BLUEPRINT.md).

## Human and AI Collaboration

WEM supports role-based collaboration between human and AI participants while preserving human accountability. WEM 1.3.0 combines bounded Work Package and Milestone delivery, automatic Project Initiation and explicit validator-adoption decisions so that human gates correspond to material decisions rather than procedural phase management. The maintained workflows are defined in [specifications/AGENT_COLLABORATION.md](specifications/AGENT_COLLABORATION.md) and [specifications/PROJECT_INITIATION.md](specifications/PROJECT_INITIATION.md).

## License

Workspace Engineering Method repository content is licensed under the Creative Commons Attribution-ShareAlike 4.0 International Public License, subject to the scope and exclusions defined by [WEM-ADR-004](decisions/WEM-ADR-004.md).

Requested attribution:

```text
Workspace Engineering Method (WEM), by Arç Fontrodona
```

See the root [LICENSE](LICENSE) for the official legal text.

## Specification Authority

This README is a non-normative repository interface. If a summary here conflicts with a canonical WEM specification or Accepted ADR, the canonical source governs.
