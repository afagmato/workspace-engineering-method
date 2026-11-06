---
Document: Architecture Decision Record
Identifier: WEM-ADR-011
Title: Define project-neutral ASI semantics
Status: Accepted
Created Date: 2026-11-03
ASI Level: 5
Decision Authority: Project Owner
WEM Reference: WEM 1.2.0 — Released
---

# WEM-ADR-011 — Define project-neutral ASI semantics

## Identifier

`WEM-ADR-011`

## Title

Define project-neutral ASI semantics

## Status

Accepted

## Created Date

2026-11-03

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-11-03 | Proposed | Project Owner | ASI-5 Architectural Pause opened to evaluate project-neutral classification semantics and the audit finding raised by WEM 1.2.0. |
| 2026-11-03 | Accepted | Project Owner | Project-neutral ASI semantics approved and normative implementation authorized. |

## Decision Authority

Project Owner

## WEM Reference

WEM 1.2.0 — Released

## Context

WEM classifies engineering decisions by the expected scope and cost of changing them. The current canonical labels are:

- ASI-5 — Foundational decisions;
- ASI-4 — Repository and architectural structure;
- ASI-3 — Framework architecture;
- ASI-2 — Public interfaces;
- ASI-1 — Internal implementation.

The labels for ASI-3 and ASI-2 assume terminology that does not transfer cleanly to every adopting project. Applications, services, knowledge repositories and operational workflows may have cross-component architecture without being frameworks. Externally consumed contracts may also be material without being described naturally as public interfaces.

WEM-ADR-010 classified the automated Project Initiation workflow as ASI-3. That decision introduced a new normative specification, modified the WEM method and provider adapters, and changed the progression behavior expected for every newly initiated WEM project. The classification is defensible as cross-cutting workflow architecture because it preserved principles, final human authority and ASI-4/5 gates. ASI-4 is also plausible because reversal requires coordinated change across a normative responsibility, the method and operational adapters.

The uncertainty does not prove that WEM-ADR-010 is invalid. It demonstrates that the current labels and classification guidance do not communicate the boundary between ASI-3 and ASI-4 precisely enough. Historical records SHALL NOT be rewritten merely to remove that ambiguity.

Changing the canonical meaning or interpretation of ASI affects every WEM project and future decision. This decision was therefore classified as ASI-5 and opened an Architectural Pause, which the Project Owner closed on acceptance.

## Decision

The decision is to define the ASI levels in project-neutral, effect-based terms while preserving their ordering, existing ADR thresholds and human-authority gates.

The selected canonical meanings are:

| Level | Canonical project-neutral meaning |
| --- | --- |
| ASI-5 | Project foundation, final authority or method identity |
| ASI-4 | Durable system structure, responsibility boundaries or human-governance architecture |
| ASI-3 | Cross-component architecture, workflow or coordinated technical policy |
| ASI-2 | Externally consumed interface, contract or compatibility boundary |
| ASI-1 | Local internal implementation constraint |

Classification SHALL continue to use expected scope and cost of reversal rather than perceived importance, artifact count, release number or the fact that a file is created.

### Boundary guidance

ASI-5 applies when a decision changes project identity, mission, final decision authority, permanent Engineering Principles or the foundational method by which all other decisions are governed.

ASI-4 applies when a decision changes durable system decomposition, canonical responsibility boundaries, repository architecture, generic role authority, required human gates or the structural relationship among major responsibilities.

ASI-3 applies when a decision coordinates multiple components or establishes a reusable workflow, execution architecture or technical policy without changing the ASI-4 structural and authority boundaries that contain it.

ASI-2 applies when a decision establishes or changes a contract consumed outside its owning component. Public visibility is not required; an interface with one external consumer can still be ASI-2. Decisions with coordinated migration or broader structural consequences may require a higher level.

ASI-1 applies to durable local implementation constraints whose reversal remains contained within one internal responsibility.

When a decision reasonably spans two levels, it SHOULD use the higher level unless the record explains why the lower level adequately represents reversal cost and affected responsibility boundaries.

### WEM-ADR-010 audit disposition

WEM-ADR-010 SHALL remain an Accepted historical record with ASI-3. This decision does not retroactively rewrite its classification or WEM 1.2.0 tag.

The implementation review evaluated WEM-ADR-010 against the clarified boundary and selected the first of these prospective conclusions:

- ASI-3 remains reasonable under the clarified cross-component workflow definition; or
- an additional Accepted decision is required before materially extending the Project Initiation responsibility.

The audit SHALL NOT invalidate compliant work solely because earlier terminology was ambiguous.

### Implementation boundary

The accepted bounded implementation may update:

- `WEM.md`, for the ASI table and concise boundary guidance;
- `specifications/ADR_SPECIFICATION.md`, for cross-domain classification guidance;
- `README.md`, only if its non-normative summary requires alignment;
- provider adapters, only if necessary to direct classification to the canonical definitions.

The implementation SHALL NOT change ADR applicability thresholds, final human authority, Architectural Pause requirements or historical ADR classifications. Any such change requires separate evaluation.

## Consequences

### Positive Consequences

- adopting projects can classify decisions without treating themselves as frameworks;
- ASI-2 applies clearly to private and public external contracts;
- ASI-3 and ASI-4 boundaries become easier to review;
- future decisions can explain classification through affected boundaries and reversal cost;
- historical decisions remain traceable without retroactive rewriting.

### Negative Consequences

- projects must interpret effect-based guidance rather than rely on a short domain label;
- some decisions will still require judgment at level boundaries;
- WEM documentation and review practice require coordinated updates.

### Risks and Limitations

- more general wording may appear less concrete without examples;
- conservative use of the higher level may increase governance overhead;
- projects could still under-classify decisions by describing structural impact as workflow detail;
- clarifying terminology cannot mechanically resolve every future classification dispute.

### New Responsibilities

- maintain project-neutral ASI definitions and cross-domain examples;
- explain boundary classifications in ADRs when more than one level is plausible;
- audit classification ambiguity as reusable knowledge rather than silently rewriting history.

## Alternatives Considered

### Alternative A — Retain the current labels without clarification

This preserves a concise table and avoids specification changes. It leaves applications, services and non-framework projects with ambiguous terminology and does not resolve the WEM-ADR-010 audit finding.

### Alternative B — Allow every adopting project to redefine ASI labels

This maximizes local fit. It would weaken comparability, permit incompatible governance claims and make the WEM version insufficient to interpret an ASI reference.

### Alternative C — Define canonical project-neutral, effect-based semantics

This preserves one WEM classification system while making it applicable across project types. It retains proportional judgment and the existing threshold structure. This is the selected alternative.

## ASI Level

ASI-5 — Foundational decisions.

The decision changes the canonical interpretation of the method's decision-classification scale across WEM and all adopting projects.

## Related Principles

- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-005` — Technology-Independent Method;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

## Related Specifications and Decisions

- `WEM.md` Version 1.2.0 — Released;
- `specifications/ADR_SPECIFICATION.md` Version 1.1.0 — Released;
- `specifications/PROJECT_INITIATION.md` Version 1.0.0 — Released;
- `decisions/WEM-ADR-009.md` — Accepted;
- `decisions/WEM-ADR-010.md` — Accepted.

## Implementation Notes

The Project Owner accepted this decision on 2026-11-03, closed the Architectural Pause and authorized preparation of the normative implementation.

The implementation prepares Draft WEM 1.3.0 components. It does not authorize release, commit, tag or publication.

WEM-ADR-010 remains reasonably classified as ASI-3 under the clarified cross-component workflow definition because it preserved the existing structural responsibility boundaries, final human authority and ASI-4/5 gates. Material extension of Project Initiation that changes those boundaries requires a new classification under the clarified semantics.

---

End of WEM-ADR-011
