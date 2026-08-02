---
Document: Architecture Decision Record
Identifier: WEM-ADR-003
Title: Establish provider-specific collaboration adapters
Status: Accepted
Created Date: 2026-08-02
ASI Level: 2
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-003 — Establish provider-specific collaboration adapters

## Identifier

`WEM-ADR-003`

---

## Title

Establish provider-specific collaboration adapters

---

## Status

Accepted

---

## Created Date

2026-08-02

---

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-08-02 | Proposed | Project Owner | ASI-2 provider-specific collaboration interface proposal opened. |
| 2026-08-02 | Accepted | Project Owner | Codex and Claude Code adapters and retirement of transitional context approved. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

The collaboration governance accepted in `decisions/WEM-ADR-002.md` defines provider-independent roles, authority boundaries, handoffs, review and completion requirements.

It permits provider-specific repository entry files to be introduced later as concise adapters when their operational responsibilities become active. Sprint 0.7 activates those responsibilities for Codex and Claude Code.

Codex consumes `AGENTS.md` as its repository entry interface. Claude Code consumes `CLAUDE.md` as its repository entry interface. Their conventional root-level locations comply with `specifications/REPOSITORY_BLUEPRINT.md` because each file serves an active tool-required repository-interface responsibility.

`CURRENT_CONTEXT.md` is a transitional handover created before the current specifications and Accepted ADRs existed. It duplicates obsolete project state and workflow assumptions and contains no exclusive canonical normative knowledge.

The retirement review identified three non-normative items with possible future value:

- WEM originated while considering a time-control application, which may become an adopting project used to validate the method;
- collaboration with Arç normally uses Catalan while maintained WEM specifications use English;
- CC BY-SA 4.0 was discussed as a provisional licensing direction, but no licensing decision has been accepted.

This ADR preserves that retirement assessment. It does not establish a validation commitment or licensing decision. The operational language preference may be carried by the provider adapters without becoming WEM governance.

This decision is ASI-2 because the adapters are repository interfaces consumed by external AI collaboration tools. It does not change canonical WEM governance, generic role authority or repository architecture, so it does not require an Architectural Pause.

---

## Decision

WEM will maintain two concise provider-specific collaboration adapters at the repository root:

- `AGENTS.md` for Codex;
- `CLAUDE.md` for Claude Code.

The adapters will:

- identify their provider-specific operational purpose;
- record the applicable initial role assignment;
- reference canonical WEM specifications and Accepted ADRs using explicit relative paths;
- apply provider-specific operating instructions without redefining WEM governance;
- preserve Arç's final human authority;
- prohibit unauthorized commit, push, merge, publication and release actions;
- avoid claiming native or shared conversational context between Codex and Claude Code.

`CURRENT_CONTEXT.md` will be retired because its transitional responsibility has ended. Its history will remain recoverable through Git, and this ADR preserves the potentially reusable context identified during retirement review.

No new directory, template, script or canonical governance responsibility is created by this decision.

---

## Consequences

### Positive

- Codex and Claude Code gain concise entry instructions in the filenames their tools consume;
- operational instructions resolve to canonical WEM governance instead of duplicating it;
- role and authority boundaries become visible at tool entry;
- the obsolete transitional context no longer competes with maintained specifications and Accepted ADRs;
- potentially reusable retirement context remains traceable.

### Negative

- two provider-specific root files must be maintained while those provider responsibilities remain active;
- changes in provider behavior may require adapter updates;
- concise adapters depend on linked canonical documents for full meaning.

### Risks and Limitations

- an adapter could drift into an independent governance source if it accumulates duplicated rules;
- a provider may interpret repository instructions differently across versions;
- Git history is required to recover the complete retired handover;
- the provisional validation and licensing notes remain undecided.

### New Responsibilities

- keep each adapter concise and aligned with `specifications/AGENT_COLLABORATION.md`;
- update adapter references when canonical paths change;
- review provider-specific changes without altering generic role authority;
- retire an adapter if its provider-specific repository-interface responsibility ends.

---

## ASI Level

ASI-2 — Public interfaces

---

## Related Principles

- `WEM-P-001` — Responsibility Before Structure;
- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-005` — Technology-Independent Method;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

---

## Related Specifications and Decisions

- `WEM.md`;
- `PROJECT_CHARTER.md`;
- `ENGINEERING_PRINCIPLES.md`;
- `specifications/ADR_SPECIFICATION.md`;
- `specifications/REPOSITORY_BLUEPRINT.md`;
- `specifications/AGENT_COLLABORATION.md`;
- `decisions/WEM-ADR-001.md`;
- `decisions/WEM-ADR-002.md`.

---

## Implementation Notes

The accepted decision is implemented by creating `AGENTS.md` and `CLAUDE.md` at the repository root and retiring `CURRENT_CONTEXT.md` in the same controlled operation.

The adapters preserve the initial assignments of Codex as Architect and Reviewer and Claude Code as Builder while retaining Arç as Project Owner and Final Authority.

No canonical specification, existing Accepted ADR, directory, template or script is changed by the implementation.

---

## End of Record
