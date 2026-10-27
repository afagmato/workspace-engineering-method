---
Document: Architecture Decision Record
Identifier: WEM-ADR-010
Title: Define the Automated Project Initiation Workflow
Status: Accepted
Created Date: 2026-10-27
ASI Level: 3
Decision Authority: Project Owner
WEM Reference: WEM 1.1.0 — Released
---

# WEM-ADR-010 — Define the Automated Project Initiation Workflow

## Identifier

`WEM-ADR-010`

## Title

Define the Automated Project Initiation Workflow

## Status

Accepted

## Created Date

2026-10-27

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-10-27 | Proposed | Project Owner | Requested one canonical process that advances a new project automatically and asks for human input only at meaningful gates. |
| 2026-10-27 | Accepted | Project Owner | Approved the automated Project Initiation workflow and authorized WEM 1.2.0 release, commit, tag and publication. |

## Decision Authority

Project Owner

## WEM Reference

WEM 1.1.0 — Released

## Context

WEM 1.1.0 defines the engineering lifecycle, Project Charter responsibility, ADR governance, repository architecture and milestone-oriented collaboration. Those sources establish the necessary pieces of project initiation but do not define one end-to-end procedure for applying them.

As a result, a Project Owner may need to ask repeatedly what happens next. An Architect may also over-request clarification, expose internal phase management to the owner or wait for instructions even when the next transition is deterministic.

Project initiation requires a distinct responsibility that defines:

- how conversational intent becomes confirmed project context;
- how preferences are distinguished from mandatory constraints;
- which initialization decisions must be made before implementation;
- which artifact is justified first;
- when the Architect advances automatically;
- which conditions create a human gate;
- how the first Milestone is authorized and executed;
- when project initialization is complete.

This workflow applies existing authority, ASI, repository and collaboration governance. It does not change the Project Owner's authority or create a new generic collaboration role. The decision is ASI-3 because it adds a cross-cutting WEM workflow while preserving the Released foundation and authority boundaries.

## Decision

The proposal is to add `specifications/PROJECT_INITIATION.md` as the canonical WEM Project Initiation specification and include it in a WEM 1.2.0 release.

### Autonomous progression

The specification SHALL require the assigned Architect function to own phase progression during initiation.

When a phase's completion criteria are satisfied and the next transition does not require a reserved human decision, the Architect SHALL advance automatically. It SHALL NOT ask the Project Owner to choose the next procedural step.

When a human gate is required, the Architect SHALL present a decision-ready package containing the recommendation, material alternatives, consequences, unresolved material questions and the exact decision requested.

### Initialization sequence

The specification SHALL define phases for:

1. initiation trigger and workspace observation;
2. conversational discovery;
3. synthesis of facts, preferences, constraints, assumptions and uncertainties;
4. foundation and first-Milestone proposal;
5. human foundation decision;
6. foundation materialization;
7. architecture and Milestone authorization;
8. autonomous execution, verification and bounded correction;
9. review, required acceptance and repository action;
10. transition to continuing milestone delivery.

Each phase SHALL define entry conditions, responsible function, required result, completion criteria, automatic transition and gate conditions.

### Preference handling

Preferences expressed in conversation SHALL NOT silently become normative constraints. The Architect SHALL classify them as confirmed requirements, preferences with a recommended default, assumptions or unresolved material decisions and SHALL expose that classification in the foundation proposal.

Non-material choices MAY be resolved by the Architect using the Project Owner's stated preferences and WEM principles. Material ambiguity SHALL create one consolidated clarification or decision gate.

### Persistence boundary

Conversation transcripts, discovery notes, Authorization Envelopes and Implementation Handoffs SHALL remain transient unless their persistence serves an explicit maintained responsibility.

The Project Charter SHOULD normally be the first maintained project artifact after the foundation gate. ADRs, repository structure and implementation artifacts SHALL be created only when their current responsibility and authorization are real.

### WEM 1.2.0 candidate

The initial candidate SHALL contain:

- `specifications/PROJECT_INITIATION.md` Version 1.0.0 Draft;
- `WEM.md` Version 1.2.0 Draft, referencing the new responsibility;
- `README.md`, identifying WEM 1.2.0 as the candidate and WEM 1.1.0 as the latest Released version;
- provider adapters aligned so an assigned Architect starts and advances the initialization workflow without waiting for procedural prompts.

Other normative components SHALL remain at their existing versions unless coherence review demonstrates that a normative change is required.

Acceptance of this ADR SHALL authorize preparation and review of the complete WEM 1.2.0 candidate. Release, commit, tag and push remain separately reserved until the candidate is reviewed.

### Scope boundary

This decision does not:

- prescribe a programming language, platform or product architecture;
- require a fixed number of agents;
- require persistent discovery or handoff documents;
- eliminate Project Owner approval of the foundation, ASI-4/5 decisions, publication or release;
- automatically create a repository or hosted project;
- modify any adopting project;
- authorize changes in WEM Orchestrator.

## Consequences

### Positive Consequences

- A Project Owner can begin with a normal conversation rather than a methodology checklist.
- The Architect owns deterministic phase progression and stops asking open-ended procedural questions.
- Preferences and binding constraints remain distinguishable.
- Initialization produces one decision-ready foundation package and one executable first Milestone.
- The workflow becomes directly automatable by WEM Orchestrator.

### Negative Consequences

- The Architect must exercise judgment about material and non-material ambiguity.
- A complete initiation specification adds another normative component to WEM.
- Automatic progression can move too quickly if phase completion criteria are weak.

### Risks and Limitations

- An Architect may incorrectly interpret a preference as authority.
- A foundation proposal may hide unresolved assumptions behind a recommended default.
- A first Milestone may become too broad if initiation and product roadmap planning are conflated.

The specification SHALL mitigate these risks through explicit classification, decision-ready gates, bounded first-Milestone scope and fail-closed authority handling.

## ASI Level

ASI-3 — Framework architecture.

The decision adds a reusable, cross-cutting workflow for every new WEM project but does not change WEM's foundational principles, generic roles or human authority boundary.

## Related Principles

- WEM-P-001 — Responsibility Before Structure
- WEM-P-003 — Explicit and Traceable Decisions
- WEM-P-004 — Proportional Governance
- WEM-P-006 — Canonical Source of Normative Knowledge
- WEM-P-007 — Human Accountability
- WEM-P-008 — Knowledge Preservation Through Evolution

These identifiers retain their normative meaning from `ENGINEERING_PRINCIPLES.md` Version 1.0.0.

## Related Specifications and Decisions

- `WEM.md` Version 1.1.0 — Released
- `PROJECT_CHARTER.md` Version 1.0.0 — Released
- `specifications/ADR_SPECIFICATION.md` Version 1.1.0 — Released
- `specifications/REPOSITORY_BLUEPRINT.md` Version 1.0.0 — Released
- `specifications/AGENT_COLLABORATION.md` Version 1.1.0 — Released
- `decisions/WEM-ADR-009.md` — Accepted

## Implementation Notes

- The complete Draft specification was prepared with this proposal so the Project Owner could evaluate the decision and its implementation as one package.
- The Project Owner accepted this decision and approved WEM 1.2.0 release, commit, tag and publication on 2026-10-27.
- WEM Orchestrator adoption remains a separate Milestone after the WEM release.

---

End of WEM-ADR-010
