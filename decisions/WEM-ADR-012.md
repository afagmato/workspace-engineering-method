---
Document: Architecture Decision Record
Identifier: WEM-ADR-012
Title: Establish durable release assurance evidence
Status: Accepted
Created Date: 2026-11-03
ASI Level: 5
Decision Authority: Project Owner
WEM Reference: WEM 1.2.0 — Released
---

# WEM-ADR-012 — Establish durable release assurance evidence

## Identifier

`WEM-ADR-012`

## Title

Establish durable release assurance evidence

## Status

Accepted

## Created Date

2026-11-03

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-11-03 | Proposed | Project Owner | ASI-5 Architectural Pause opened to evaluate durable evidence and review independence for WEM releases. |
| 2026-11-03 | Accepted | Project Owner | Durable release assurance evidence and review-independence disposition approved for normative implementation. |

## Decision Authority

Project Owner

## WEM Reference

WEM 1.2.0 — Released

## Context

WEM requires coherence review and explicit Project Owner approval before a specification release. Collaboration governance requires review to evaluate correctness, scope, governance, evidence and unintended changes. It also states that significant work should receive review by another authorized reviewer or the Project Owner when the Architect and Reviewer also implements the change.

WEM permits routine execution messages and intermediate evidence to remain transient when persistence is unnecessary. That proportional rule is appropriate for local reversible work. A public WEM release is different: it creates a stable normative reference consumed by adopting projects, and the fact and basis of its review have durable audit value.

WEM 1.1.0 and WEM 1.2.0 were released on 2026-10-27, thirty-one minutes apart. Their Accepted ADRs state that coherence review and Project Owner approval occurred. The Git repository does not retain the reviewed diff, verification matrix, reviewer identity, findings or explicit disposition in enough detail to evaluate the depth or independence of those reviews.

The short interval does not itself prove inadequate review. Review evidence may have existed in private conversation, and WEM does not mandate an arbitrary waiting period. The audit finding is that a public methodology release cannot demonstrate its assurance solely through an assertion that review completed.

Changing WEM release assurance affects publication governance and the durable evidence expected before future specification releases. This decision was therefore classified as ASI-5 and opened an Architectural Pause, which the Project Owner closed on acceptance.

## Decision

The decision is to require a durable, proportional release assurance record for every future WEM specification release without imposing a minimum elapsed-time delay.

### Minimum release assurance evidence

Before a WEM release is declared, durable evidence SHALL identify:

- release candidate identity and base commit;
- exact changed artifact scope;
- specification and component version matrix;
- status and historical-reference audit;
- relative-link and required-structure validation;
- applicable automated and manual checks;
- unavailable, incomplete or failed verification;
- reviewer role and review-independence disposition;
- review findings and their resolution or explicit acceptance;
- canonical Review Result;
- explicit Project Owner release decision;
- authorized commit, tag and publication actions;
- final commit and tag relationship after publication.

The evidence MAY be maintained in the governing release ADR, a pull request, a signed or immutable external record, or another recoverable location identified by the governing ADR. WEM SHALL NOT require a separate document when an existing maintained record contains the required evidence coherently.

### Review independence

For an ASI-4 or ASI-5 WEM release, a participant that authored or implemented a material change SHALL NOT be the only technical reviewer unless the Project Owner records an explicit exception with rationale and compensating review.

The Project Owner may provide the additional review when technically qualified and explicitly acting in that review capacity. Human release authority remains separate from the technical Review Result.

An exception SHALL remain visible in the release assurance evidence. Successful tests, tool completion or Project Owner approval alone SHALL NOT be represented as independent technical review.

### No mandatory waiting period

WEM SHALL NOT impose a time delay merely to create the appearance of scrutiny. A release may proceed whenever its decision, implementation, verification, review and human approval evidence are complete.

Rapid consecutive releases SHOULD receive additional scope and compatibility review when the later release depends on assumptions introduced by the earlier release.

### Historical releases

Tags `v1.0.0`, `v1.1.0` and `v1.2.0` SHALL remain unchanged. This decision SHALL NOT fabricate historical evidence or retroactively claim a reviewer that cannot be verified.

If Accepted, implementation SHALL include a retrospective audit of WEM 1.1.0 and WEM 1.2.0 using only recoverable evidence. The audit SHALL identify gaps as limitations rather than treating them automatically as release invalidation.

### Implementation boundary

If Accepted, the bounded implementation may update:

- `PROJECT_CHARTER.md`, for WEM-specific release assurance responsibility;
- `specifications/AGENT_COLLABORATION.md`, for significant-release review independence and persistence;
- `WEM.md`, only where a high-level release assurance reference is necessary;
- the governing ADR implementation notes or a non-normative knowledge record for the retrospective audit.

The implementation SHALL NOT change final release authority, existing tags, historical Status History or the content of Released historical versions.

## Consequences

### Positive Consequences

- future releases expose review and verification evidence proportionate to their public impact;
- release speed is evaluated through evidence rather than elapsed time;
- combined-role work cannot silently present self-review as independent review;
- adopting projects can audit the basis of a WEM release;
- existing records can carry the evidence without mandatory document proliferation.

### Negative Consequences

- release preparation requires additional durable evidence;
- small teams may need an explicit independence exception;
- retrospective audits may reveal evidence that cannot be reconstructed.

### Risks and Limitations

- a checklist may create false confidence when evidence quality is weak;
- review records may become verbose or duplicate information already present in Git or a pull request;
- requiring independence without an exception path could block small projects;
- external evidence may become inaccessible unless its recoverable location is maintained.

### New Responsibilities

- preserve minimum assurance evidence for WEM releases;
- identify review independence or an explicit exception;
- maintain recoverable evidence locations;
- audit rapid dependent releases for compatibility and inherited assumptions.

## Alternatives Considered

### Alternative A — Require a fixed waiting period between releases

This makes rapid publication less likely but does not guarantee review quality. Waiting without evidence is not assurance and can delay valid corrections.

### Alternative B — Continue allowing all release review evidence to remain transient

This minimizes maintenance cost. It prevents later evaluation of public release claims and is disproportionate to the durable impact of a normative tag.

### Alternative C — Require durable proportional evidence and independence disposition

This preserves flexibility in tools and artifact form while making review quality auditable. It supports small teams through an explicit exception rather than silent self-review. This is the selected alternative.

## ASI Level

ASI-5 — Foundational decisions.

The decision changes the governance evidence and review boundary required before WEM specification publication and release.

## Related Principles

- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

## Related Specifications and Decisions

- `PROJECT_CHARTER.md` Version 1.0.0 — Released;
- `specifications/AGENT_COLLABORATION.md` Version 1.1.0 — Released;
- `decisions/WEM-ADR-008.md` — Accepted;
- `decisions/WEM-ADR-009.md` — Accepted;
- `decisions/WEM-ADR-010.md` — Accepted;
- Git tags `v1.0.0`, `v1.1.0` and `v1.2.0`.

## Implementation Notes

The Project Owner accepted this decision on 2026-11-03, closed the Architectural Pause and authorized preparation of the normative implementation and retrospective evidence audit.

The implementation prepares Draft WEM 1.3.0 components. It does not authorize release, commit, tag or publication.

The retrospective audit is maintained at `knowledge/release-assurance-audit-1.1.0-1.2.0.md`. It preserves the verified release commits and annotated-tag relationships, identifies unavailable reviewer and verification evidence, and does not invalidate or rewrite either historical release.

---

End of WEM-ADR-012
