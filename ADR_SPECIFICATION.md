---
Document: ADR Specification
Title: Workspace Engineering Method Architecture Decision Records
Version: 1.0.0
Status: Draft
Type: Governance
ASI: 4
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method Architecture Decision Records

## Purpose

This specification defines the Architecture Decision Record (ADR) system used by WEM and by projects that adopt it.

It establishes when an ADR is required, what an ADR contains, how its status evolves, who may approve it and how architectural decisions remain traceable over time.

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Scope

This specification applies to architectural and governance decisions made during the development and evolution of WEM.

Projects adopting WEM SHALL apply this specification to decisions within their own responsibilities.

This specification defines:

- ADR applicability;
- ADR content;
- identifier governance;
- status and lifecycle;
- decision authority;
- relationship to the Architectural Stability Index;
- relationship to Architectural Pauses;
- historical preservation and supersession.

This specification does not define:

- a universal repository location for ADRs;
- directory or file naming;
- a physical ADR template;
- a specific authoring or approval tool;
- implementation planning or task tracking.

Those concerns SHALL be defined only when their corresponding responsibilities become active.

---

## Governing Principles

This specification applies, in particular, the following Engineering Principles as authoritatively defined in `ENGINEERING_PRINCIPLES.md`:

- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

These references do not redefine their normative meaning.

---

## Architecture Decision Record

An ADR is the maintained historical record of one engineering decision that requires durable traceability.

An ADR preserves:

- the context in which the decision was evaluated;
- the decision that was proposed or made;
- its expected consequences;
- its ASI classification;
- its relationship to applicable Engineering Principles;
- the responsible human decision authority.

An ADR is not a meeting transcript, implementation plan, task description or general design document.

Conversation history, issue trackers and implementation artifacts MAY support an ADR, but SHALL NOT replace it when an ADR is required.

---

## ADR Requirement

ADR governance SHALL be proportional to the expected scope and cost of changing a decision.

The minimum ADR requirement by ASI level is:

| ASI level | ADR requirement |
| --- | --- |
| ASI-5 | Required |
| ASI-4 | Required |
| ASI-3 | Required |
| ASI-2 | Required |
| ASI-1 | Proportional |
| Unclassified | Not required |

An ASI-1 decision SHOULD use an ADR when it establishes a durable internal constraint, coordinates multiple contributors or preserves a non-obvious engineering trade-off.

Other ASI-1 decisions MAY use a lighter traceability mechanism appropriate to their scope and cost of change.

Routine, local and readily reversible choices that do not meet the applicable ASI threshold do not require an ADR.

Every ADR SHALL identify an ASI level.

A Proposed ADR MAY record a provisional ASI level.

The ASI classification SHALL be resolved before the ADR becomes Accepted.

A Rejected or Withdrawn ADR MAY retain a provisional ASI classification when final classification would provide no additional governance value.

A proposed deviation from a normative WEM requirement SHALL be documented and approved through an ADR when it affects a significant decision or a WEM adoption claim.

The responsible human decision authority MAY require an ADR for any classified decision when durable traceability is necessary.

An ADR SHALL address one coherent decision responsibility.

Unrelated decisions SHALL NOT be combined solely to reduce the number of ADRs.

---

## Required Content

Each ADR SHALL contain:

- Identifier;
- Title;
- Status;
- Created Date;
- Status History;
- Decision Authority;
- WEM Reference;
- Context;
- Decision;
- Consequences;
- ASI Level;
- Related Principles.

An ADR for an ASI-4 or ASI-5 decision SHALL also contain:

- Alternatives Considered.

An ADR SHOULD identify related ADRs, specifications and external constraints when they are necessary to understand the decision.

An ADR that supersedes or retires an accepted decision SHALL identify the affected ADR.

Implementation notes MAY be included when useful, but SHALL be distinguishable from the decision itself.

---

## Content Semantics

### Identifier

The Identifier uniquely and permanently identifies the ADR within its decision scope.

### Title

The Title states the decision topic concisely.

It SHOULD describe the decision responsibility rather than its implementation task.

### Status

The Status identifies the ADR's current lifecycle state.

### Created Date

The Created Date records when the ADR first entered maintained project knowledge.

### Status History

The Status History records every lifecycle transition, its effective date and the responsible decision authority.

Historical status entries SHALL NOT be removed or overwritten when the current status changes.

### Decision Authority

The Decision Authority identifies the human role responsible for accepting or rejecting the decision.

### WEM Reference

The WEM Reference identifies both the version and status of WEM under which the decision was governed.

Example:

```text
WEM 1.0.0 — Draft
```

### Context

The Context describes the problem, constraints, assumptions and forces that made the decision necessary.

It SHALL provide enough information to evaluate the decision without relying on undocumented conversation history.

### Decision

The Decision states the proposed or approved direction precisely.

An Accepted ADR SHALL distinguish the decision from supporting explanation and implementation detail.

### Consequences

The Consequences describe the expected benefits, costs, risks, trade-offs, new responsibilities and effects on future change.

Consequences SHALL include material disadvantages and limitations, not only expected benefits.

### ASI Level

The ASI Level records the classification of the decision according to `WEM.md`.

### Related Principles

Related Principles identifies the applicable Engineering Principles by permanent identifier.

When historical meaning is relevant, the reference SHOULD identify both the principle identifier and the applicable WEM version.

### Alternatives Considered

Alternatives Considered records the credible options evaluated and the principal reason each was selected or not selected.

The depth of analysis SHALL be proportional to the decision's ASI level and expected cost of change.

---

## Identifier Governance

WEM ADR identifiers SHALL use the following format:

```text
WEM-ADR-NNN
```

`WEM` identifies the decision scope, `ADR` identifies the record type and `NNN` is a sequential numeric identifier.

Projects adopting WEM SHALL establish a stable ADR identifier convention for their own decision scope.

They SHOULD use:

```text
<PROJECT>-ADR-NNN
```

An adopting project MAY retain an existing identifier convention when it provides equivalent uniqueness, permanence and traceability.

ADR identifiers are permanent.

An identifier SHALL NOT be reassigned, reused or changed because an ADR is renamed, rejected, withdrawn, superseded or retired.

The numerical order of an identifier does not indicate priority, authority, status or implementation order.

---

## ADR Status

ADR status SHALL be one of:

- Proposed;
- Accepted;
- Rejected;
- Withdrawn;
- Superseded;
- Retired.

### Proposed

The decision is under evaluation and has not been approved.

A Proposed ADR does not authorize implementation of the proposed decision.

### Accepted

The responsible human decision authority has approved the decision.

An Accepted ADR governs the recorded decision until it is superseded or retired.

### Rejected

The responsible human decision authority has explicitly decided not to adopt the proposal.

### Withdrawn

The proposal was removed from consideration before an acceptance or rejection decision.

### Superseded

A later Accepted ADR has replaced the decision.

The superseded ADR and the replacing ADR SHALL reference each other.

### Retired

The decision is no longer applicable and has not been replaced by an equivalent active decision.

The retiring ADR and the retired ADR SHALL reference each other.

Only an Accepted ADR represents a currently governing decision.

---

## ADR Lifecycle

An ADR normally begins with status Proposed.

A Proposed ADR MAY transition to:

- Accepted;
- Rejected;
- Withdrawn.

An Accepted ADR MAY transition to:

- Superseded;
- Retired.

An Accepted ADR SHALL be superseded or retired only through another Accepted ADR.

A Rejected or Withdrawn ADR SHALL NOT later become Accepted.

If its proposal is reconsidered, a new ADR SHALL be created and SHALL reference the earlier record.

Updating current status and relationship metadata SHALL NOT rewrite the historical meaning of the original decision or its Status History.

Once an ADR identifier has entered maintained project knowledge, the ADR SHALL remain available for historical traceability.

---

## Decision Authority

The authority that proposes or authors an ADR is distinct from the authority that approves it.

The responsible human decision authority SHALL accept or reject an ADR.

AI collaborators MAY research alternatives, analyze consequences, draft ADRs and verify implementation, but SHALL NOT accept or reject an ADR on behalf of the responsible human authority.

For WEM, the Project Owner is the final authority for ASI-4 and ASI-5 decisions as defined in `PROJECT_CHARTER.md`.

For WEM, authority for ASI-1, ASI-2 and ASI-3 decisions MAY be explicitly delegated by the Project Owner.

When no delegation has been explicitly established, the Project Owner SHALL remain the responsible decision authority.

An adopting project SHALL define its responsible decision authorities within its own governance.

The Decision Authority field SHALL identify the responsible role.

The individual acting in that role MAY also be recorded as operational metadata.

If decision authority is unclear or disputed, the ADR SHALL remain Proposed and affected implementation SHALL pause until authority is resolved.

---

## Architectural Pause

An ASI-4 or ASI-5 decision SHALL follow the Architectural Pause defined in `WEM.md`.

The required ADR SHALL be Proposed during the Architectural Pause and before implementation of the affected decision continues.

The ADR SHALL record the alternatives evaluated and the consequences considered during the pause.

The Architectural Pause SHALL NOT complete until the responsible human decision authority has accepted, rejected or withdrawn the proposal.

Implementation of the proposed decision SHALL proceed only when the ADR is Accepted.

A Rejected or Withdrawn ADR SHALL NOT authorize implementation.

---

## Relationship to Normative Specifications

An ADR that records an accepted decision is the authoritative historical record that the decision was made and why.

It is not automatically the authoritative definition of every normative requirement resulting from that decision.

When an Accepted ADR establishes or changes a requirement governed by a WEM specification, the responsible specification SHALL contain the authoritative definition of that requirement.

The ADR SHALL reference the affected specification, and the specification MAY reference the ADR as decision rationale.

The ADR and affected specifications SHALL NOT define the same requirement inconsistently.

An implementation affected by the decision SHALL NOT be accepted as complete until the responsible normative specifications are coherent with the Accepted ADR.

---

## Traceability and Preservation

ADRs SHALL be maintained as project knowledge and remain discoverable without relying on conversation history or individual memory.

The maintained ADR record, not a transient discussion, SHALL determine the recorded status and meaning of a decision.

ADRs in every status SHALL remain available as maintained records once their identifiers have entered project knowledge.

Supersession and retirement relationships SHALL be traceable in both directions.

An ADR SHALL reference evidence, specifications or implementation artifacts when they are necessary to verify its context or consequences.

Version-control history MAY provide additional evidence, but SHALL NOT be the only place where the current ADR status or supersession relationship can be discovered.

---

## Adoption

A project adopting WEM SHALL define:

- where its ADRs are maintained;
- how ADRs are discovered;
- its identifier convention;
- its responsible decision authorities.

An adopting project MAY add fields or approval controls when they do not weaken the requirements of this specification.

Additional status aliases or substates MAY be used only when their mapping to the required ADR statuses is explicit and unambiguous.

An adopting project with an existing decision-record system MAY map that system to this specification when the equivalence of required content, lifecycle states and authority is explicit.

Any incompatible omission or deviation SHALL follow the deviation governance defined in `ENGINEERING_PRINCIPLES.md`.

WEM does not require a particular directory layout, file format, template engine, repository platform or approval tool.

---

## Initial Adoption

The initial publication of this specification establishes the first operational ADR governance system for WEM.

Its initial acceptance SHALL require an ASI-4 Architectural Pause and explicit approval by the Project Owner.

Because no operational ADR system exists before this specification is accepted, its initial publication does not require a preceding ADR.

This bootstrap provision applies only to the initial adoption of this specification.

After its initial acceptance, all qualifying decisions, including changes to this specification, SHALL follow the ADR governance defined here.

---

## Evolution

Changing ADR applicability thresholds, required content, status semantics, identifier governance or decision-authority boundaries affects the ADR governance system and SHALL be classified as ASI-4 or higher according to its actual scope and cost of change.

Changes that modify a foundational WEM principle or responsibility SHALL follow the applicable ASI-5 governance.

Editorial corrections that do not change normative meaning are not structural decisions.

They require explicit ASI classification only when they meet the applicable ASI threshold and SHALL otherwise follow proportional governance.

Historical ADRs SHALL be interpreted according to the WEM Reference recorded in the ADR.

---

## End of Specification
