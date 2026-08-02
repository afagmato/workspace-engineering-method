---
Document: Architecture Decision Record
Identifier: WEM-ADR-001
Title: Define the WEM repository architecture
Status: Accepted
Created Date: 2026-07-31
ASI Level: 4
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-001 — Define the WEM repository architecture

## Identifier

`WEM-ADR-001`

---

## Title

Define the WEM repository architecture

---

## Status

Accepted

---

## Created Date

2026-07-31

---

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-07-31 | Proposed | Project Owner | Architectural direction approved for document drafting and final review. |
| 2026-08-01 | Accepted | Project Owner | Hybrid responsibility-based repository architecture approved. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

The WEM repository contains the maintained knowledge that defines and evolves the Workspace Engineering Method.

The repository currently uses a flat root containing the foundational WEM specification, the Project Charter, the Engineering Principles, the ADR governance specification and a transitional continuity document.

The current structure was appropriate while each responsibility was introduced individually during Sprint 0. It does not yet define durable boundaries for future specifications, ADRs, standards, knowledge, documentation, templates or conceptual examples.

The repository now requires an explicit architecture before additional responsibilities create ambiguous or speculative structure.

The architecture must:

- preserve the visibility of WEM's foundational specifications;
- provide canonical locations for specialized responsibilities;
- create no empty directories or placeholder artifacts;
- separate normative specifications from historical decision records and non-normative knowledge;
- keep functional products, runtime libraries, frameworks and derived tools outside the methodology repository;
- distinguish reusable knowledge from explanatory documentation;
- preserve traceability when artifacts move or are retired;
- allow adopting projects to map the same responsibilities to different physical structures;
- accommodate repository-wide, legal or tool-required files when their responsibilities become real.

`AGENT_COLLABORATION.md` is local operational context and is not part of the maintained repository architecture.

`CURRENT_CONTEXT.md` is a transitional continuity artifact. It SHALL NOT be removed as part of this decision-document publication. Its exact physical casing and long-term responsibility will be addressed during a later authorized structural operation.

This decision is ASI-4 because it establishes canonical repository boundaries and constrains the placement of future artifacts.

---

## Decision

The decision is to adopt a hybrid, responsibility-based repository architecture.

Foundational specifications will remain at the repository root.

Specialized responsibilities will use canonical directories. A directory will be created only when it receives its first real artifact in the same operation.

The selected canonical locations are:

| Responsibility | Canonical location |
| --- | --- |
| Foundation specifications | Repository root |
| Other normative specifications | `specifications/` |
| Architecture Decision Records | `decisions/` |
| Standards | `standards/` |
| Reusable knowledge | `knowledge/` |
| Explanatory documentation | `documentation/` |
| Templates | `templates/` |
| Conceptual examples | `examples/` |
| Repository interface, legal and tool-required artifacts | Repository root when their responsibility or external convention requires it |

The foundational specifications currently authorized to remain at the root are:

- `WEM.md`;
- `PROJECT_CHARTER.md`;
- `ENGINEERING_PRINCIPLES.md`.

When the architecture is physically applied:

- `ADR_SPECIFICATION.md` will move to `specifications/ADR_SPECIFICATION.md`;
- `REPOSITORY_BLUEPRINT.md` will move to `specifications/REPOSITORY_BLUEPRINT.md`;
- `WEM-ADR-001.md` will move to `decisions/WEM-ADR-001.md`;
- affected references will be updated in the same structural operation;
- no inactive responsibility directory will be created.

Publication of this Accepted ADR and the Draft Repository Blueprint does not authorize or perform those physical changes.

`CURRENT_CONTEXT.md` will remain present until a separate authorized decision determines its long-term responsibility, location or retirement. This ADR does not authorize its removal.

Projects adopting WEM will not be required to copy the WEM repository tree. They will be required to define equivalent responsibility boundaries, canonical locations and discovery rules within their own repository architecture.

This decision authorizes the repository architecture for controlled structural application. The physical changes remain subject to a separate explicitly authorized ASI-4 operation.

---

## Consequences

### Positive

- foundational specifications remain immediately visible;
- specialized artifacts gain explicit and discoverable boundaries;
- directory creation remains consistent with the Responsibility Before Structure principle;
- specifications and ADRs retain distinct responsibilities;
- knowledge and documentation cannot silently become normative sources;
- future repository growth becomes predictable without pre-creating structure;
- adopting projects retain physical flexibility while preserving equivalent architectural responsibilities.

### Negative

- normative specifications will have two possible location classes: foundational specifications at the root and other specifications under `specifications/`;
- applying the decision will require a separate migration and reference update;
- repository contributors must understand the difference between knowledge, documentation, templates and examples;
- explicit root-admission rules are required to prevent the root from becoming heterogeneous again.

### Risks and Limitations

- a broad interpretation of repository-wide responsibility could weaken the root restrictions;
- misclassified informative content could duplicate or contradict normative specifications;
- case-only renames may require special handling on case-insensitive filesystems;
- publication of the decision documents before structural application creates a temporary transitional state;
- future responsibility classes may require an architectural revision if they do not fit the approved model.

### New Responsibilities

- maintain the Repository Blueprint as the canonical repository-architecture specification;
- verify every new directory against an active responsibility;
- preserve links and history during moves;
- document adopting-project mappings when their physical architecture differs from WEM;
- review transitional root artifacts through separately authorized decisions.

---

## Alternatives Considered

### Alternative A — Flat repository root

Keep every specification, ADR, standard, guide, template and knowledge artifact at the repository root.

This alternative minimizes immediate migration and remains simple while the repository is small.

It was not selected because it mixes responsibilities, scales poorly and provides no durable discovery boundary for future artifact classes.

### Alternative B — Fully classified hierarchy

Move all maintained content, including foundational specifications, below classified directories.

This alternative provides uniform classification and a minimal root.

It was not selected because it reduces the visibility of WEM's foundation, adds unnecessary navigation depth and encourages more structure than the current responsibilities require.

### Alternative C — Previously discussed domain folders

Use the previously discussed top-level names `core/`, `framework/`, `standards/`, `sandbox/`, `knowledge/` and `documentation/`.

This alternative was not selected because:

- `core/` expresses importance rather than responsibility;
- `framework/` suggests executable product responsibilities outside the WEM repository;
- `sandbox/` represents transient work rather than maintained knowledge;
- the model provides no explicit location for ADRs;
- the boundaries between foundational and specialized specifications remain unclear.

### Alternative D — Hybrid responsibility-based architecture

Keep foundational specifications at the root and place specialized responsibilities in canonical directories created only when populated.

This alternative is selected because it balances foundation visibility, responsibility clarity, incremental growth and adoption flexibility.

---

## ASI Level

ASI-4 — Repository and architectural structure

---

## Related Principles

- `WEM-P-001` — Responsibility Before Structure;
- `WEM-P-002` — Separation of Knowledge and Products;
- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-005` — Technology-Independent Method;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

---

## Related Specifications

- `WEM.md`;
- `PROJECT_CHARTER.md`;
- `ENGINEERING_PRINCIPLES.md`;
- `specifications/ADR_SPECIFICATION.md`;
- `specifications/REPOSITORY_BLUEPRINT.md`.

---

## Implementation Notes

The repository architecture was physically applied on 2026-08-02 through the separately authorized ASI-4 operation recorded by commit `d7b2409`.

The implementation:

- created `specifications/` by moving `ADR_SPECIFICATION.md` and `REPOSITORY_BLUEPRINT.md` into their canonical location;
- created `decisions/` by moving `WEM-ADR-001.md` into its canonical location;
- preserved the foundation specifications at the repository root;
- aligned `CURRENT_CONTEXT.md` to its approved tracked casing without changing its root location;
- updated affected references;
- created no other canonical responsibility directory.

This implementation completes the structural operation authorized by this ADR.

It does not determine the long-term responsibility, location or retirement of `CURRENT_CONTEXT.md` and does not authorize additional repository structure.

---

## End of Record
