---
Document: Architecture Decision Record
Identifier: WEM-ADR-009
Title: Adopt Proportional Milestone Delivery Governance for WEM 1.1.0
Status: Accepted
Created Date: 2026-10-27
ASI Level: 5
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Released
---

# WEM-ADR-009 — Adopt Proportional Milestone Delivery Governance for WEM 1.1.0

## Identifier

`WEM-ADR-009`

## Title

Adopt Proportional Milestone Delivery Governance for WEM 1.1.0

## Status

Accepted

## Created Date

2026-10-27

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-10-27 | Proposed | Project Owner | Opened the ASI-5 Architectural Pause to evaluate a less interruptive, milestone-oriented application of WEM governance. |
| 2026-10-27 | Accepted | Project Owner | Approved proportional milestone delivery governance and authorized preparation of the WEM 1.1.0 release candidate. |

## Decision Authority

Project Owner

## WEM Reference

WEM 1.0.0 — Released

## Context

WEM 1.0.0 establishes proportional governance, permits bounded authorization without repeated human mediation, permits one participant to perform multiple explicitly assigned functions and allows a single bounded instruction to satisfy an Implementation Handoff.

Experience applying WEM 1.0.0 to WEM Orchestrator nevertheless exposed recurrent friction:

- reversible operational choices were classified too highly;
- approval was requested separately for planning, implementation, correction, commit and push even when one bounded authorization could cover them;
- zero correction cycles converted deterministic implementation errors into human gates;
- persistent ADRs and specifications duplicated information already governed elsewhere;
- release-level verification was repeated during small implementation increments;
- the number of approvals encouraged procedural confirmation rather than substantive human judgment.

Part of this friction is an application error, but part follows from the current ADR threshold: WEM 1.0.0 requires an ADR for every ASI-2 decision even when the change is local to one public interface, remains Draft and is inexpensive to reverse.

The Project Owner has approved the direction of a milestone-oriented workflow in which architecture and milestone boundaries are decided before implementation, work proceeds autonomously inside those boundaries, intermediate gates occur only for reserved or material decisions, and one final review supports human acceptance and repository action.

Changing the normative ADR threshold and collaboration workflow is foundational governance. This proposal is therefore ASI-5 and opens an Architectural Pause. WEM 1.0.0 remains the governing Released version until a WEM 1.1.0 release is separately reviewed and approved.

## Decision

The proposal is to prepare WEM 1.1.0 as a backward-compatible governance refinement centered on proportional work packages and milestones.

### Decision classification and ADR threshold

WEM 1.1.0 SHALL continue to require ADRs for ASI-4 and ASI-5 decisions.

ASI-3 decisions SHALL require an ADR because they establish cross-cutting framework or product architecture whose reversal requires coordinated work.

ASI-2 decisions SHALL use proportional traceability:

- an ADR SHALL be required when a public-interface change affects external consumers, compatibility commitments, multiple maintained components or coordinated migration;
- a bounded task record, issue, change description or implementation handoff MAY provide sufficient traceability when the interface remains Draft, has one controlled consumer and is inexpensive to reverse;
- the responsible human authority MAY require an ADR whenever durable decision rationale is necessary.

ASI-1 and unclassified decisions SHALL NOT require an ADR by default. A concise decision record MAY be used for a durable, non-obvious trade-off.

Classification SHALL be based on the expected scope and cost of reversal. Creating a file, activating an already approved responsibility, selecting a patch version, configuring a local tool or causing bounded external state SHALL NOT by itself raise a decision to ASI-2 or ASI-3.

Implementing an Accepted decision SHALL NOT be treated as a new architectural decision unless implementation reveals a material choice not covered by that decision.

### Milestone-oriented authorization

WEM 1.1.0 SHALL define a Work Package as a bounded unit of delivery and a Milestone as one or more related Work Packages that produce an evaluable outcome.

An Authorization Envelope MAY authorize, in one human decision:

- implementation within approved responsibilities or path subtrees;
- creation of the files needed by those responsibilities;
- deterministic verification and bounded correction cycles;
- role combination permitted by the collaboration specification;
- conditional commit, push or other repository actions when their prerequisites and exact destination are explicit;
- progression across adjacent workflow phases that do not reserve a later human decision.

Separate approval SHALL NOT be required merely because planning, implementation, verification, commit and push are distinct mechanical operations.

An envelope authorizing a Milestone SHALL identify the milestone outcome, architectural boundaries, scope, applicable limits, verification profile, repository actions, human-reserved decisions and stop conditions. Detail SHALL remain proportional; exact file enumeration SHALL NOT be required when an approved responsibility or subtree is a safer and clearer boundary.

### Meaningful gates

Intermediate human gates SHALL occur when:

- an ASI-4 or ASI-5 decision is required;
- the approved architecture or milestone outcome would change materially;
- scope, cost, time or external effects would exceed the active envelope;
- a destructive, publication, release, licensing, credential or sensitive-data decision was not already authorized;
- mandatory verification fails or an effect becomes ambiguous;
- the active envelope explicitly reserves the decision to human authority.

Routine corrections, formatting, tests, internal refactoring within approved boundaries and other local reversible actions SHALL NOT create a human gate solely because they are separate implementation steps.

The Builder and Reviewer MAY use bounded automatic correction cycles while scope, architecture, limits and authority remain valid. An envelope SHOULD permit such cycles unless a specific risk justifies prohibiting them.

### Verification profiles

WEM 1.1.0 SHALL distinguish:

- focused verification during a Work Package;
- complete integration verification at a Milestone gate;
- release verification before publication or release.

Release-level checks SHALL NOT be required for every local increment unless the increment can invalidate the corresponding release property.

Unavailable mandatory verification remains blocking at the gate where that verification is required.

### Role topology and review

One participant MAY perform Architect, Builder and Reviewer functions for routine or low-impact work when the assignment is explicit and no human authority is transferred.

Significant work SHOULD receive independent review. ASI-4 and ASI-5 decisions, milestone acceptance, publication and release remain subject to the human authority defined by WEM.

Claude Code, Codex or any other provider implementation SHALL NOT be required merely to preserve a multi-agent topology.

### WEM 1.1.0 release candidate

If this ADR is Accepted, the release candidate SHALL update only the responsibilities necessary to implement this decision:

- `WEM.md`, to expose milestone-oriented proportional delivery at the method level;
- `specifications/ADR_SPECIFICATION.md`, to implement the revised ADR threshold and classification guidance;
- `specifications/AGENT_COLLABORATION.md`, to define Work Packages, Milestones, combined authorization and meaningful gates;
- `README.md`, to identify the WEM 1.1.0 release candidate and its component versions;
- provider adapters only where operational wording must align with the new governance without redefining it.

Modified normative documents SHALL become Version 1.1.0. Unchanged foundation and specification documents MAY retain Version 1.0.0 and SHALL be identified as unchanged normative dependencies of WEM 1.1.0.

The `v1.0.0` tag and Released WEM 1.0.0 content SHALL remain immutable. WEM 1.1.0 SHALL require complete coherence review, explicit human release approval and separately authorized repository actions before a `v1.1.0` tag or publication.

### Compatibility

WEM 1.1.0 is intended to be backward compatible with WEM 1.0.0:

- work governed validly under WEM 1.0.0 remains valid;
- existing ADRs and their status histories remain unchanged;
- projects MAY continue using stricter gates;
- no project automatically adopts WEM 1.1.0;
- an adopting project SHALL declare the WEM version it applies.

The release candidate review SHALL confirm this compatibility claim. If the proposed text instead invalidates a compliant WEM 1.0.0 workflow, the change SHALL be reclassified as incompatible before release.

### Scope boundary

Acceptance of this ADR would authorize preparation and review of the WEM 1.1.0 release candidate. It would not by itself:

- release or tag WEM 1.1.0;
- commit, push or publish the release candidate;
- modify an adopting project;
- accept changes in WEM Orchestrator;
- remove human authority from ASI-4, ASI-5, milestone acceptance, publication or release;
- authorize destructive actions, credentials or unbounded external effects.

## Consequences

### Positive Consequences

- Human attention is concentrated on decisions rather than mechanical phase boundaries.
- Routine work can proceed from one bounded authorization to one evaluable result.
- ADR volume and cross-document maintenance decrease without losing high-impact traceability.
- Correction and verification can complete autonomously within explicit limits.
- Projects can obtain executable feedback earlier while preserving architectural and publication gates.

### Negative Consequences

- Classification requires more judgment because ASI-2 no longer has one universal artifact rule.
- Broader milestone envelopes can authorize more change before human review.
- Combined roles reduce independent review for routine work.
- Projects using WEM 1.0.0 and 1.1.0 will have different minimum governance profiles.

### Risks and Limitations

- Teams may under-classify decisions to avoid documentation.
- Vague subtree or responsibility permissions may expand scope unintentionally.
- Preauthorized repository actions may publish an incorrect result if their conditions are weak.
- Milestones that are too large may delay useful review.

These risks SHALL be mitigated through explicit milestone outcomes, bounded paths or responsibilities, mandatory stop conditions, focused verification and independent review proportional to impact.

## Alternatives Considered

### Alternative A — Keep WEM 1.0.0 unchanged

This preserves deterministic artifact requirements but retains the observed approval and documentation overhead. It does not address the mismatch between proportional-governance intent and current application.

### Alternative B — Remove structured governance from routine and architectural work

This maximizes speed but loses authority boundaries, traceability and fail-closed external-effect control. It is rejected.

### Alternative C — Adopt proportional milestone delivery while preserving high-impact gates

This keeps WEM's human-accountability and architectural-safety model while reducing low-value interruption. This is the proposed alternative.

## ASI Level

ASI-5 — Foundational.

The decision changes the minimum ADR threshold and the normative collaboration workflow applied by WEM adopters. Its effects span decision governance, authorization, review, repository actions and future project adoption.

## Related Principles

- WEM-P-003 — Explicit and Traceable Decisions
- WEM-P-004 — Proportional Governance
- WEM-P-006 — Canonical Source of Normative Knowledge
- WEM-P-007 — Human Accountability
- WEM-P-008 — Knowledge Preservation Through Evolution

These references retain their normative meaning from `ENGINEERING_PRINCIPLES.md` Version 1.0.0.

## Related Specifications and Decisions

- `WEM.md` Version 1.0.0 — Released
- `ENGINEERING_PRINCIPLES.md` Version 1.0.0 — Released
- `specifications/ADR_SPECIFICATION.md` Version 1.0.0 — Released
- `specifications/AGENT_COLLABORATION.md` Version 1.0.0 — Released
- `decisions/WEM-ADR-002.md`
- `decisions/WEM-ADR-006.md`
- `decisions/WEM-ADR-007.md`
- `decisions/WEM-ADR-008.md`

## Implementation Notes

- The Project Owner accepted this decision on 2026-10-27 and closed its Architectural Pause.
- The bounded WEM 1.1.0 release candidate completed coherence review on 2026-10-27.
- The Project Owner approved WEM 1.1.0 release, commit, tag and publication on 2026-10-27.
- Adoption and simplification changes in WEM Orchestrator remain a separate governed operation after WEM 1.1.0 is Released.

---

End of WEM-ADR-009
