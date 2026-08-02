---
Document: Architecture Decision Record
Identifier: WEM-ADR-002
Title: Establish human and AI collaboration governance
Status: Accepted
Created Date: 2026-08-02
ASI Level: 4
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-002 — Establish human and AI collaboration governance

## Identifier

`WEM-ADR-002`

---

## Title

Establish human and AI collaboration governance

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
| 2026-08-02 | Proposed | Project Owner | ASI-4 Architectural Pause opened for human and AI collaboration governance. |
| 2026-08-02 | Accepted | Project Owner | Role-based, human-controlled collaboration governance approved. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

WEM recognizes AI agents as engineering collaborators while preserving final human accountability.

The current WEM specifications define foundational authority, decision traceability, proportional governance, ADR requirements and repository architecture. They do not yet define a complete collaboration responsibility for assigning work, transferring context, controlling concurrency, reviewing implementation or preventing conflict between human and AI participants.

The initial WEM workflow involves a human Project Owner and two AI collaborators performing architecture, review and implementation responsibilities.

Those collaborators do not share native conversational context. Access to the same repository does not provide shared memory, shared intent or direct agent-to-agent communication.

Command-line invocation or another automation interface may allow one collaborator to invoke another. Such invocation is optional programmatic orchestration and requires explicit authorization, bounded scope and human-governed review. It is not native agent-to-agent communication and does not transfer decision authority.

The collaboration model must:

- preserve human approval for ASI-4 and ASI-5 decisions;
- define stable roles independently from providers and models;
- separate architecture, implementation, review and final acceptance responsibilities;
- require explicit and verifiable handoffs;
- prevent conflicting concurrent changes;
- preserve repository knowledge as shared maintained context;
- support optional programmatic orchestration without bypassing authority boundaries;
- avoid duplicating normative knowledge owned by other WEM specifications;
- allow provider-specific repository entry files only when their separate responsibilities become active.

This decision is ASI-4 because it establishes durable governance roles, authority boundaries and collaboration structure for WEM engineering work.

---

## Decision

The decision is to establish role-based, human-controlled collaboration governance.

The governance model will define three generic roles:

- Project Owner and Final Authority;
- Architect and Reviewer;
- Builder.

The roles will remain conceptually independent from the people, providers, models or tools assigned to perform them.

The Project Owner and Final Authority will retain the human approvals defined by WEM and the Project Charter, including approval of ASI-4 and ASI-5 decisions.

The Architect and Reviewer will analyze architectural impact, prepare bounded proposals and handoffs, and review implementation evidence without assuming final human authority.

The Builder will implement approved work within explicit scope, report verification evidence and escalate architectural conflicts without redefining the approved decision.

Coordination will occur through maintained repository knowledge, explicit handoffs, Git state and diffs, review findings and human-mediated decisions.

Controlled concurrency will require explicit work ownership or isolated branches or worktrees. Collaborators will not modify the same files concurrently without approved isolation and integration responsibility.

Programmatic delegation will remain optional. It will require explicit authorization and a bounded task definition, and it will not create native shared conversational context or transfer approval authority.

Provider-specific entry files such as `AGENTS.md` and `CLAUDE.md` will remain outside the scope of this decision. They may be introduced later only as concise adapters to the canonical collaboration specification when their responsibilities are explicitly activated.

The initial operational assignment will be recorded as non-normative operational context:

- Arç: Project Owner and Final Authority;
- Codex: Architect and Reviewer;
- Claude Code: Builder.

This decision is governing from the Accepted status recorded in the Status History.

---

## Consequences

### Positive

- collaboration authority becomes explicit and recoverable from maintained project knowledge;
- generic roles remain stable when tools, providers or models change;
- significant work receives bounded handoffs and independent review;
- human accountability remains distinct from AI analysis and implementation capacity;
- concurrent changes are controlled before they create ambiguous ownership or conflicts;
- optional automation can be used without being mistaken for native communication or delegated approval;
- provider-specific instructions can remain thin adapters rather than alternative governance sources.

### Negative

- collaboration requires deliberate handoffs and review evidence rather than relying on conversational continuity;
- role separation introduces coordination overhead for small tasks;
- the same collaborator may need to switch roles explicitly when staffing is limited;
- programmatic delegation requires additional authorization, stopping conditions and result review;
- operational assignments must be maintained separately from normative role definitions when they change.

### Risks and Limitations

- role names could become proxies for specific providers if operational assignments are mistaken for normative identity;
- excessive workflow detail could create disproportionate governance for routine work;
- insufficient handoff detail could cause agents to act on incompatible assumptions;
- shared repository access could be mistaken for shared conversational context;
- overlapping workspaces could still create conflicts if ownership and isolation rules are ignored;
- future collaboration environments may support capabilities not covered by the initial operational assignment.

### New Responsibilities

- maintain the canonical collaboration governance specification;
- identify active roles and authority for each collaborative task;
- prepare explicit handoffs before transferring implementation responsibility;
- review implementation evidence before human acceptance;
- record conflicts, deviations and unresolved authority boundaries;
- introduce provider-specific adapters only through separately activated responsibilities.

---

## Alternatives Considered

### Alternative A — Human-only coordination

The Project Owner would coordinate every task directly and AI collaborators would operate only as isolated assistants without a shared role model.

This alternative preserves simple human control and avoids formal agent interaction rules.

It was not selected because architectural analysis, implementation and review responsibilities would remain implicit, handoffs would vary by conversation and reusable collaboration knowledge would not be preserved.

### Alternative B — Provider-specific direct agent coordination

The collaboration model would depend on direct integrations, native conversations or proprietary orchestration between particular AI providers and models.

This alternative could reduce manual coordination when compatible integrations exist.

It was not selected because WEM would become dependent on provider capabilities, direct shared context cannot be assumed, authority boundaries could become implicit and replacement of a provider could invalidate the governance model.

### Alternative C — Role-based, human-controlled collaboration governance

WEM would define stable collaboration roles, explicit human authority, bounded handoffs, controlled concurrency, independent review and optional authorized programmatic orchestration.

Provider and model assignments would remain operational and replaceable.

This alternative was selected because it preserves human accountability and technology independence while enabling structured collaboration among current and future human and AI participants.

---

## ASI Level

ASI-4 — Repository and architectural structure

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
- `decisions/WEM-ADR-001.md`.

---

## Implementation Notes

The Draft collaboration specification is maintained at `specifications/AGENT_COLLABORATION.md` for controlled application and cross-document coherence review.

The collaboration governance defined by this decision is authorized for controlled application while the specification remains Draft.

This decision does not create or authorize `AGENTS.md`, `CLAUDE.md`, templates, scripts or additional repository directories.

---

## End of Record
