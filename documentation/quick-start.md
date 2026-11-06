# WEM 1.2.0 Quick Start

> Non-normative adoption guidance. The Released WEM specifications govern if this guide conflicts with them.

WEM can be adopted without AI agents, automation or a large document set. Start with the smallest maintained knowledge needed for the decisions that are real today.

## 1. Declare the method

Record the adopted version in the project's maintained foundation:

```text
Methodology: WEM 1.2.0 — Released
```

The adopting project remains responsible for its objectives, architecture, implementation, risks and outcomes.

## 2. Establish the project foundation

Write one concise Project Charter that identifies:

- project identity and type;
- problem and mission;
- scope in and scope out;
- Project Owner and decision authority;
- applicable constraints and success criteria;
- WEM version and status.

Use [the Project Charter template](../templates/project-charter.md) as a starting structure. Remove sections that are genuinely not applicable; do not invent content merely to fill a template.

The WEM 1.3.0 Draft extends Project Initiation by automatically evaluating structural-validator adoption and including one decision-ready disposition in the Foundation Package:

- `Adopt` when a compatible, approved validator can be activated within known authority;
- `Defer` when validation is relevant but compatibility, authority or execution capability is unresolved;
- `Not Applicable` only with a responsibility-based rationale.

Projects adopting only WEM 1.2.0 are not required to apply this Draft extension. When it is applied, the Project Owner decides the disposition at the existing foundation gate; the recommendation does not silently authorize installation, maintained configuration, CI integration or repository effects.

## 3. Govern only decisions that need governance

Classify a decision when it constrains future work, affects shared structures or contracts, or requires coordinated effort to reverse.

- ASI-4 and ASI-5 decisions require an Architectural Pause and ADR.
- ASI-3 decisions require an ADR.
- ASI-2 uses an ADR for compatibility commitments, multiple maintained components or coordinated migration. A bounded task record or handoff may suffice while an interface remains Draft, has one controlled consumer and is inexpensive to reverse.
- ASI-1 and routine reversible choices normally need no ADR.

The canonical rules are in [WEM](../WEM.md) and the [ADR Specification](../specifications/ADR_SPECIFICATION.md). The [ADR template](../templates/adr.md) is only an authoring aid.

## 4. Create structure when responsibility becomes real

Do not create a complete repository tree in advance. Introduce a directory with its first real artifact and assign every maintained artifact one responsibility and canonical location.

Product repositories may contain executable implementation. The WEM repository itself remains a knowledge repository.

See the [Repository Blueprint](../specifications/REPOSITORY_BLUEPRINT.md) and the [minimal example](../examples/minimal-project.md).

## 5. Deliver one bounded outcome

Define a small first Milestone with:

- outcome;
- scope and exclusions;
- authority and human-reserved decisions;
- acceptance criteria;
- focused verification;
- stop and escalation conditions.

Adjacent phases may be combined when authority and evidence remain explicit. Human gates are for material or reserved decisions, not for every mechanical step.

## 6. Preserve what is worth reusing

Record significant decisions and reusable lessons. Routine execution messages and transient handoffs do not need permanent storage unless recovery, audit, acceptance or future reuse requires it.

Knowledge from delivery should inform the next round of thinking.

## Small-project baseline

A small project can begin with only:

```text
PROJECT_CHARTER.md
```

Add an ADR only when a qualifying decision appears. Add implementation, tests, documentation or other directories only with their first real artifact. WEM does not require a fixed number of documents, collaborators or tools.

## Canonical sources

- [WEM](../WEM.md)
- [Project Charter](../PROJECT_CHARTER.md)
- [Engineering Principles](../ENGINEERING_PRINCIPLES.md)
- [ADR Specification](../specifications/ADR_SPECIFICATION.md)
- [Repository Blueprint](../specifications/REPOSITORY_BLUEPRINT.md)
- [Collaboration Governance](../specifications/AGENT_COLLABORATION.md)
- [Project Initiation](../specifications/PROJECT_INITIATION.md)
