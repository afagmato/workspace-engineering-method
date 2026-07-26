---
Document: Engineering Principles
Title: Workspace Engineering Method Engineering Principles
Version: 1.0.0
Status: Released
Type: Foundation
ASI: 5
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method Engineering Principles

## Purpose

This specification defines the permanent engineering principles that govern WEM and guide projects that adopt it.

Principles express durable engineering intent. Detailed processes, structures and implementation requirements SHALL be defined in the specifications responsible for them.

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Scope

These principles apply to the development and evolution of WEM.

Projects adopting WEM SHALL evaluate the principles against their responsibilities and SHALL apply every applicable principle.

Any determination that a principle is not applicable, when it affects a significant decision or adoption claim, SHALL be explicit and justified.

Projects SHALL reference applicable principles by identifier when documenting significant decisions.

This specification does not define repository layouts, ADR formats, collaboration workflows, coding rules or technology-specific implementation requirements.

---

## Principle Structure

Each principle SHALL contain:

- a permanent identifier;
- a title;
- a status;
- a statement;
- a rationale.

Principle status SHALL be one of:

- Active;
- Retired.

The Principle Index is the authoritative source for a principle's status.

The statement defines the normative rule.

The rationale explains why the principle exists without introducing additional normative requirements.

---

## Identifier Governance

Principle identifiers use the following format:

```text
WEM-P-NNN
```

`WEM` identifies the method, `P` identifies an engineering principle and `NNN` is a sequential numeric identifier.

Principle identifiers are permanent.

An identifier SHALL NOT be reassigned, reused or changed because a principle is renamed, revised or retired.

The numerical order of an identifier does not indicate priority.

A retired principle SHALL retain its identifier so that historical references remain valid.

A principle reference SHALL be interpreted within the WEM version declared by the adopting project.

When historical meaning is relevant, a reference SHOULD identify both the principle identifier and the applicable WEM version.

Example:

```text
WEM-P-003 — WEM 1.0.0
```

---

## Principle Index

| Identifier | Title | Status |
| --- | --- | --- |
| WEM-P-001 | Responsibility Before Structure | Active |
| WEM-P-002 | Separation of Knowledge and Products | Active |
| WEM-P-003 | Explicit and Traceable Decisions | Active |
| WEM-P-004 | Proportional Governance | Active |
| WEM-P-005 | Technology-Independent Method | Active |
| WEM-P-006 | Canonical Source of Normative Knowledge | Active |
| WEM-P-007 | Human Accountability | Active |
| WEM-P-008 | Knowledge Preservation Through Evolution | Active |

---

## WEM-P-001 — Responsibility Before Structure

### Statement

Persistent repository artifacts and structural elements SHALL be introduced only when they serve a current and explicit responsibility.

Empty directories, placeholder documents, speculative abstractions and inactive structures SHALL NOT be created solely to anticipate possible future work.

### Rationale

Every persistent artifact introduces cognitive, maintenance and coordination cost.

Delaying structure until its responsibility becomes real keeps the repository minimal, makes architectural intent visible and prevents speculative design from being mistaken for an accepted commitment.

This principle is commonly referred to as the Zero Empty Rule.

---

## WEM-P-002 — Separation of Knowledge and Products

### Statement

Reusable engineering knowledge and functional product implementation SHALL have distinct responsibilities.

A repository whose responsibility is engineering knowledge SHALL NOT contain functional product implementations.

Executable applications, libraries, frameworks and tools SHALL be maintained under separate product responsibilities when they become real.

### Rationale

Knowledge and executable products usually have different consumers, release cycles, licensing needs and maintenance obligations.

Separating them allows engineering knowledge to remain reusable and technology-independent while products evolve according to their own requirements.

---

## WEM-P-003 — Explicit and Traceable Decisions

### Statement

Engineering decisions that constrain future work, affect shared structures or contracts, modify governance, or require coordinated effort to reverse SHALL be explicit and traceable.

Their context, rationale, consequences and decision authority SHALL be recoverable from the project's maintained knowledge.

### Rationale

Undocumented decisions lose their reasoning and become indistinguishable from accidents or arbitrary conventions.

Traceability allows future collaborators to understand why a decision exists, evaluate whether its assumptions remain valid and change it without relying on conversation history or individual memory.

---

## WEM-P-004 — Proportional Governance

### Statement

Governance effort SHALL be proportional to the expected scope and cost of changing a decision.

Routine, local and readily reversible choices MAY use lightweight or no formal governance.

Decisions with broader, structural or durable consequences SHALL receive correspondingly greater analysis, review and approval.

### Rationale

Applying the same process to every decision creates bureaucracy and obscures the decisions that require genuine scrutiny.

Proportional governance preserves rigor where change is expensive while allowing routine implementation work to proceed efficiently.

---

## WEM-P-005 — Technology-Independent Method

### Statement

WEM normative knowledge SHALL remain independent from particular programming languages, frameworks, platforms, vendors and AI providers.

Projects MAY use technology-specific implementations and instructions, but those implementations SHALL NOT redefine the WEM method or become its only source of normative knowledge.

### Rationale

Technologies and providers change faster than foundational engineering responsibilities.

Keeping the method independent from them allows WEM to remain reusable, replaceable and valid across different implementation environments.

---

## WEM-P-006 — Canonical Source of Normative Knowledge

### Statement

Each normative requirement SHALL have one authoritative definition.

Other specifications MAY reference, apply or specialize that requirement within their own responsibilities, but SHALL NOT redefine it inconsistently.

Supporting summaries MAY exist when they are clearly non-normative and do not replace the authoritative definition.

### Rationale

Duplicated normative knowledge diverges over time and creates ambiguity about which statement governs.

An authoritative definition preserves consistency while allowing modular specifications to remain focused on their own responsibilities.

---

## WEM-P-007 — Human Accountability

### Statement

Human decision-makers SHALL retain final responsibility for project objectives, foundational and structural approvals, milestone acceptance, publication and release decisions.

AI collaborators MAY analyze, propose, implement, review and document work within their authorized responsibilities, but SHALL NOT approve their own foundational proposals on behalf of the responsible human authority.

### Rationale

AI systems can extend engineering capacity but cannot assume project accountability.

Explicit human authority ensures that consequential decisions remain owned, reviewable and aligned with the project's objectives.

---

## WEM-P-008 — Knowledge Preservation Through Evolution

### Statement

Reusable knowledge generated through design, implementation and evolution SHALL be preserved when it can improve future engineering decisions.

Changes that supersede established decisions SHALL retain or explicitly account for the relevant prior rationale and consequences.

### Rationale

Software systems and engineering methods evolve, but losing the reasoning behind previous decisions causes repeated mistakes and makes change harder to evaluate.

Preserving knowledge allows future evolution to build on experience instead of starting again from incomplete context.

---

## Applying the Principles

Applicable principles SHALL be interpreted and applied together rather than in isolation.

An apparent conflict between principles SHALL be made explicit and evaluated with governance proportional to the scope and cost of the decision.

A principle SHALL NOT be silently ignored because compliance is inconvenient.

Any accepted deviation SHALL be explicit, justified, traceable and approved by the responsible human decision authority.

---

## Evolution

Adding a principle, retiring a principle or changing its normative meaning is a foundational decision and SHALL be classified as ASI-5.

Editorial corrections that do not change normative meaning are not foundational decisions.

They require explicit ASI classification only when they meet the applicable ASI threshold and SHALL otherwise follow proportional governance.

Changes SHALL preserve permanent identifiers and the traceability of historical references.

---

## End of Specification
