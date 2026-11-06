---
Document: Architecture Decision Record
Identifier: WEM-ADR-013
Title: Automate validator adoption decisions during project initiation
Status: Accepted
Created Date: 2026-11-06
ASI Level: 3
Decision Authority: Project Owner
WEM Reference: WEM 1.2.0 — Released
---

# WEM-ADR-013 — Automate validator adoption decisions during project initiation

## Identifier

`WEM-ADR-013`

## Title

Automate validator adoption decisions during project initiation

## Status

Accepted

## Created Date

2026-11-06

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-11-06 | Proposed | Project Owner | Every new WEM adoption should decide deliberately whether structural validation is activated instead of relying on later manual discovery. |
| 2026-11-06 | Accepted | Project Owner | Mandatory automated validator-adoption evaluation during Project Initiation approved for Draft WEM 1.3.0. |

## Decision Authority

Project Owner

No delegation for this ASI-3 WEM decision has been recorded.

## WEM Reference

WEM 1.2.0 — Released

## ASI Level

ASI-3 — Cross-component workflow and coordinated technical policy

## Context

WEM Validator has completed four internally accepted Milestones and a read-only external pilot against WEM Orchestrator. The pilot demonstrated that structural validation can find a real governance defect, expose false assumptions in the validator itself and provide reproducible evidence without modifying the adopting project.

WEM Project Initiation already automates phase progression and requires a Decision Skeleton, Foundation Package, verification profiles and reviewed Initialization Baseline. It does not currently require an explicit decision about structural validation. A project may therefore adopt WEM, create maintained governance artifacts and only later discover that validation was available or that no compatible profile had been selected.

Silently activating a tool would conflict with the separation of method and product, preference classification, project authority and explicit repository effects. Asking every Project Owner an open-ended tooling question would reintroduce procedural interruption. The workflow instead needs a mandatory automated evaluation that produces a decision-ready disposition inside the existing foundation gate.

The change coordinates synthesis, the Decision Skeleton, Foundation Package, first-Milestone planning, review and continuation. It preserves the Project Owner's foundation gate and every existing ASI, publication and repository-action boundary. It is therefore classified ASI-3 and does not require an Architectural Pause.

## Decision

Every new WEM Initiation Run SHALL automatically evaluate structural-validator adoption and include one explicit Validator Adoption Disposition in its Decision Skeleton and Foundation Package.

### Required dispositions

The disposition SHALL be exactly one of:

- `Adopt` — activate a compatible validator within explicitly authorized scope;
- `Defer` — validation is relevant but compatibility, authority, execution capability or timing is not yet sufficient;
- `Not Applicable` — structural validation is outside the project's current maintained responsibilities or an equivalent governed validation responsibility already satisfies the need.

The disposition SHALL identify:

- the evidence supporting the recommendation;
- the selected validator implementation and exact compatibility profile when `Adopt` is recommended;
- the provisional ASI and responsible authority for activation;
- configuration, execution, repository and CI effects;
- verification commands or the reason they cannot yet run;
- limitations, deferred coverage and the condition for reassessment.

### Automatic evaluation rule

The Architect SHALL recommend `Adopt` when all of the following are true:

1. the project maintains or will maintain WEM-governed artifacts within the Initialization Baseline or first Milestone;
2. a validator implementation has a compatible profile for the declared WEM version and is approved for the intended internal or public use;
3. execution is compatible with project security, environment and repository constraints;
4. activation fits within known authority and can be bounded without inventing a material preference.

The Architect SHALL recommend `Defer` when validation is relevant but any adoption condition is unresolved. The disposition SHALL identify the earliest phase, Milestone or external condition that triggers reassessment.

`Not Applicable` SHALL require an explicit responsibility-based rationale. Tool absence, inconvenience, silence or lack of prior configuration SHALL NOT by themselves make validation not applicable.

### Authority and activation

The evaluation and recommendation are automatic. Tool installation, maintained configuration, CI integration, external access, credentials, repository actions and release effects are not automatically authorized.

The PI-G1 Foundation Decision SHALL accept, reject or modify the Validator Adoption Disposition together with the Foundation Package. This SHALL NOT create a separate human gate when the disposition is already decision-ready within PI-G1.

When an existing Project Owner policy and delegated authority deterministically govern the disposition, the Architect MAY record and apply it without an additional validator-specific gate. The foundation gate itself remains required.

An accepted `Adopt` disposition authorizes only the exact effects included in the Foundation Package. Materialization SHALL occur in PI-4 or the first authorized Milestone according to the accepted scope. The workflow SHALL NOT infer authorization from local installation, tool availability or successful execution.

### Method and product separation

WEM defines the decision responsibility and required evidence. It SHALL NOT make one validator implementation part of the WEM normative method.

WEM Validator is the current reference product for WEM structural validation. An adopting project MAY select another implementation when it provides compatible declared coverage and preserves WEM authority boundaries.

Successful validator execution SHALL remain structural evidence only. It SHALL NOT constitute architectural review, certification, Project Owner acceptance, publication approval or release authority.

### Review and continuation

When `Adopt` is accepted and activation is in scope, applicable validator execution SHALL form part of PI-4 or Milestone verification and PI-8 review evidence.

PI-9 SHALL report the current disposition, activated profile, unresolved limitations and reassessment trigger. A deferred decision SHALL remain visible without blocking Initialization unless its absence prevents an applicable required check.

## Consequences

### Positive Consequences

- every new WEM project makes the validation decision deliberately;
- the decision is integrated into the existing foundation gate instead of adding a procedural interruption;
- compatible projects receive a default recommendation based on evidence;
- deferral and non-applicability remain explicit and reviewable;
- method governance remains separate from validator product implementation;
- validation limitations become visible before the first Milestone executes.

### Negative Consequences

- Foundation Packages gain one additional mandatory disposition;
- Architects must know whether a compatible validator profile and approved distribution are available;
- projects without an executable profile must preserve and revisit a deferral;
- provider adapters and examples must reflect the new initiation responsibility.

### Risks and Limitations

- automatic recommendation could be mistaken for automatic tool authority;
- projects may overstate compatibility from a partial profile;
- a validator product may become an implicit methodology dependency;
- repeated deferral could become invisible process debt.

### Mitigations

- separate evaluation, decision and activation explicitly;
- require exact profile, scope, effects and limitations;
- keep PI-G1 authority unchanged;
- allow equivalent validators while preserving declared compatibility;
- require a reassessment trigger for every deferred disposition;
- prohibit certification and acceptance claims from successful execution alone.

## Related Principles

- `WEM-P-001` — Responsibility Before Structure — WEM 1.2.0;
- `WEM-P-002` — Separation of Knowledge and Products — WEM 1.2.0;
- `WEM-P-003` — Explicit and Traceable Decisions — WEM 1.2.0;
- `WEM-P-004` — Proportional Governance — WEM 1.2.0;
- `WEM-P-005` — Technology-Independent Method — WEM 1.2.0;
- `WEM-P-006` — Canonical Source of Normative Knowledge — WEM 1.2.0;
- `WEM-P-007` — Human Accountability — WEM 1.2.0.

## Alternatives Considered

### A. Leave validator adoption entirely project-specific

This preserves maximum flexibility but allows the decision to be forgotten until defects or release pressure expose the gap. It was not selected.

### B. Activate WEM Validator automatically in every adopting project

This maximizes consistency but silently selects a product, assumes compatibility and execution authority, and can create unauthorized repository or CI effects. It was rejected.

### C. Require automatic evaluation and one decision-ready disposition in Project Initiation

This is the selected alternative. It guarantees deliberate treatment while using the existing foundation gate and preserving project authority.

### D. Ask the Project Owner a separate validator question during every initiation

This would preserve explicit choice but add a repetitive procedural gate even when the evidence and existing policy determine the recommendation. It was rejected.

## Implementation Notes

The Project Owner accepted this decision and authorized implementation through the instruction to automate the decision whenever WEM is integrated into a new project on 2026-11-06.

Implementation SHALL update:

- `specifications/PROJECT_INITIATION.md`, as the canonical workflow responsibility;
- `WEM.md`, as the high-level method reference;
- `README.md`, for Draft version composition and navigation context;
- `AGENTS.md`, as the non-normative Codex operational adapter;
- `documentation/quick-start.md`, `templates/project-charter.md` and `examples/minimal-project.md`, as non-normative adoption aids.

Implementation completed on 2026-11-06. The canonical initiation workflow now produces the mandatory disposition, the Codex adapter invokes it automatically, and the supporting adoption aids show how the accepted result is recorded without implying silent tool authority.

Verification included cross-reference review, whitespace validation and structural validation against the WEM 1.2 compatibility profile. The structural validator reported only the known historical WEM-reference coverage limitations for ADRs governed by earlier Draft or Released WEM versions; it reported no structural error in this decision or the changed normative responsibility.

Review Result: `Accepted for the next authorized gate`.

The implementation prepares Draft WEM 1.3.0 content. It does not release WEM 1.3.0, activate a validator in an existing adopting project, commit, push, tag or publish any artifact.

---
