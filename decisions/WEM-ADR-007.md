---
Document: Architecture Decision Record
Identifier: WEM-ADR-007
Title: Consolidate ADR governance in the canonical ADR specification
Status: Accepted
Created Date: 2026-08-07
ASI Level: 4
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-007 — Consolidate ADR governance in the canonical ADR specification

## Identifier

`WEM-ADR-007`

---

## Title

Consolidate ADR governance in the canonical ADR specification

---

## Status

Accepted

---

## Created Date

2026-08-07

---

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-08-07 | Proposed | Project Owner | ASI-4 Architectural Pause opened to consolidate ADR governance in its canonical specification. |
| 2026-08-07 | Accepted | Project Owner | Canonical ADR governance boundary approved and Sprint 0.11 remediation authorized. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

The Sprint 0.11 Cross-Document Coherence Review identified a normative duplication between `WEM.md` and `specifications/ADR_SPECIFICATION.md`.

`WEM.md` contains a partial normative definition of the Architecture Decision Record contract. It independently requires eight ADR fields:

- Identifier;
- Title;
- Status;
- Context;
- Decision;
- Consequences;
- ASI Level;
- Related Principles.

`specifications/ADR_SPECIFICATION.md` is the canonical responsibility for ADR governance and requires twelve fields. In addition to the eight fields listed by `WEM.md`, it requires:

- Created Date;
- Status History;
- Decision Authority;
- WEM Reference.

It also requires Alternatives Considered for every ASI-4 and ASI-5 ADR.

`WEM.md` states that ADR creation is evaluated during an Architectural Pause. The canonical ADR specification defines the actual applicability rules: an ADR is required for ASI-2, ASI-3, ASI-4 and ASI-5 decisions, while ASI-1 uses proportional ADR governance. It also defines how ADR requirements interact with Architectural Pauses.

The independent and incomplete definition in `WEM.md` can be read as the full ADR contract even though it omits requirements established by the responsible specification. Maintaining both definitions would permit future divergence and conflicts with `WEM-P-006` — Canonical Source of Normative Knowledge.

The correction must remove the duplication without reducing, expanding or otherwise changing the effective ADR governance already established by `specifications/ADR_SPECIFICATION.md`.

This decision is ASI-4 because it corrects the structural boundary between the foundational WEM method and the canonical ADR governance specification. The Project Owner accepted this ADR and closed the Architectural Pause on 2026-08-07.

---

## Decision

The decision is to make `specifications/ADR_SPECIFICATION.md` the single canonical source for:

- ADR applicability;
- required content;
- lifecycle;
- decision authority;
- identifier governance;
- the relationship between ADRs and ASI;
- the relationship between ADRs and Architectural Pauses.

`WEM.md` retains only a high-level definition of Architecture Decision Records and references `specifications/ADR_SPECIFICATION.md` for the applicable governance.

`WEM.md` does not enumerate an independent list of mandatory ADR fields.

The Architectural Pause section of `WEM.md` does not state only that ADR creation is evaluated. It refers to the applicable requirements defined by `specifications/ADR_SPECIFICATION.md`.

The correction SHALL NOT reduce or expand the current requirements of `specifications/ADR_SPECIFICATION.md`.

`specifications/ADR_SPECIFICATION.md` SHALL NOT be modified as part of this decision when final review confirms that it already represents the accepted ADR governance correctly. If implementation reveals a new conflict in that specification, affected work SHALL stop and return to the Project Owner for evaluation.

Acceptance of this ADR closes the Architectural Pause and authorizes the bounded Sprint 0.11 remediation recorded in the Implementation Notes.

---

## Consequences

### Positive

- ADR governance will have one authoritative normative definition;
- `WEM.md` will remain focused on the high-level engineering method;
- ADR applicability, content, lifecycle, authority and ASI relationships will be interpreted consistently;
- future ADR governance changes will no longer require maintaining a duplicate field list in `WEM.md`;
- adopting projects will resolve detailed ADR requirements through an explicit canonical path.

### Negative

- readers of `WEM.md` will need to follow a reference to obtain the complete ADR contract;
- the correction requires a coordinated update to foundational wording even though the effective ADR requirements do not change;
- future changes to the canonical path will require affected references to be updated.

### Risks and Limitations

- an overly detailed replacement summary in `WEM.md` could recreate normative duplication;
- imprecise wording could accidentally weaken or expand existing ADR applicability;
- combining unrelated release or governance changes with this correction could obscure the bounded purpose of the decision;
- the correction does not itself release any Draft specification.

### New Responsibilities

- keep the high-level ADR description in `WEM.md` aligned with, but subordinate to, `specifications/ADR_SPECIFICATION.md`;
- review future changes for accidental duplication across the canonical responsibility boundary;
- preserve historical ADR interpretation under the WEM Reference recorded by each ADR.

---

## Alternatives Considered

### Alternative A — Maintain both definitions through manual synchronization

`WEM.md` and `specifications/ADR_SPECIFICATION.md` would continue to define ADR requirements independently, and each future change would update both documents.

This approach keeps more detail in the foundational method but preserves duplicate normative definitions and depends on every future change maintaining perfect synchronization.

It was not selected because it conflicts with `WEM-P-006` and retains the divergence risk identified by the coherence review.

### Alternative B — Make WEM.md the complete source of ADR governance

All ADR applicability, required content, lifecycle, authority, identifier and Architectural Pause rules would move into `WEM.md`.

This approach would remove duplication, but it would collapse a distinct governance responsibility into the foundational method, expand `WEM.md` substantially and weaken the modular specification architecture.

It was not selected because ADR governance is already an active, coherent and independently maintained responsibility in `specifications/ADR_SPECIFICATION.md`.

### Alternative C — Make ADR_SPECIFICATION.md the single canonical source

`specifications/ADR_SPECIFICATION.md` would remain the complete authoritative definition of ADR governance. `WEM.md` would retain a concise high-level description and reference the canonical specification.

This approach preserves modular responsibility boundaries, removes the incomplete duplicate contract and leaves the effective ADR governance unchanged.

It is the selected alternative.

---

## ASI Level

ASI-4 — Repository and architectural structure

This decision is classified within ASI-4 because it changes the durable normative boundary between the foundational method and the canonical ADR governance specification without changing WEM's foundational purpose or the effective ADR requirements.

---

## Related Principles

- `WEM-P-003` — Explicit and Traceable Decisions: the canonical ADR system preserves significant decision context, consequences and authority;
- `WEM-P-004` — Proportional Governance: the canonical specification retains proportional ADR treatment for ASI-1 while requiring ADRs for ASI-2 through ASI-5;
- `WEM-P-006` — Canonical Source of Normative Knowledge: one specification owns the authoritative ADR governance definition;
- `WEM-P-007` — Human Accountability: ADR decision authority and Architectural Pause approval remain human responsibilities as defined by the canonical sources;
- `WEM-P-008` — Knowledge Preservation Through Evolution: existing ADR history and WEM References remain unchanged and interpretable.

---

## Related Artifacts

- `WEM.md`, corrected by this decision to retain a high-level ADR definition and reference the canonical governance specification;
- `ENGINEERING_PRINCIPLES.md`, for the authoritative Engineering Principles;
- `specifications/ADR_SPECIFICATION.md`, as the canonical ADR governance specification;
- `specifications/REPOSITORY_BLUEPRINT.md`, for the responsibility boundary between foundation and governance specifications;
- `decisions/WEM-ADR-001.md`, for the Accepted repository architecture;
- `decisions/WEM-ADR-003.md`, for the Accepted retirement of `CURRENT_CONTEXT.md` and the related Sprint 0.11 coherence correction.

---

## Implementation Notes

The Project Owner accepted this ADR on 2026-08-07, closed the Architectural Pause and authorized the bounded Sprint 0.11 remediation.

The remediation operation implemented:

### WEM-CR-001

- corrected `WEM.md` according to the decision recorded here.

### WEM-CR-002

- updated `specifications/REPOSITORY_BLUEPRINT.md` so that it preserves the historical treatment of `CURRENT_CONTEXT.md` and records that the file was later retired through `decisions/WEM-ADR-003.md`.

### WEM-CR-003

- updated `AGENTS.md` so that the Reviewer uses the canonical Review Result semantics `Accepted for the next authorized gate` or `Changes requested`, without duplicating the complete Review Result contract.

That remediation operation did not modify:

- historical ADRs WEM-ADR-001 through WEM-ADR-006;
- `ENGINEERING_PRINCIPLES.md`;
- `PROJECT_CHARTER.md`;
- `specifications/ADR_SPECIFICATION.md`;
- `README.md`;
- `CLAUDE.md`;
- `LICENSE`;
- `documentation/wem-presentacio.pdf`.

No other file or directory is authorized by this Accepted ADR.

---

## End of Record
