---
Document: Project Initiation Specification
Title: Workspace Engineering Method Project Initiation
Version: 1.0.0
Status: Released
Type: Governance
ASI: 3
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method Project Initiation

## Purpose

This specification defines how a new WEM project progresses from conversational intent to an accepted foundation, an authorized first Milestone and continuing delivery.

It makes phase progression the responsibility of the assigned Architect function so that the Project Owner makes substantive decisions without having to direct the procedure.

## Status and Authority

Version 1.0.0 is Released as part of WEM 1.2.0 under Accepted `WEM-ADR-010`, following coherence review and explicit Project Owner approval on 2026-10-27.

Release establishes the canonical Project Initiation workflow. It does not initialize an adopting project or transfer any Project Owner authority by itself.

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

## Scope

This specification governs:

- initiation of a new WEM project;
- conversational discovery;
- classification of preferences, constraints, assumptions and uncertainties;
- preparation and approval of the project foundation;
- selection of the first maintained artifact;
- definition and authorization of the first Milestone;
- automatic phase progression;
- meaningful human gates;
- transition from initiation to continuing delivery.

It does not prescribe product architecture, technology, commercial validation, funding, organization design or a universal repository structure.

## Normative Dependencies

This specification applies:

- `WEM.md`, for lifecycle, ASI, Architectural Pauses and proportional delivery;
- `PROJECT_CHARTER.md`, for project identity, scope and final authority;
- `ENGINEERING_PRINCIPLES.md`, for permanent Engineering Principles;
- `specifications/ADR_SPECIFICATION.md`, for decision classification and ADR requirements;
- `specifications/REPOSITORY_BLUEPRINT.md`, for artifact responsibility and repository activation;
- `specifications/AGENT_COLLABORATION.md`, for roles, Authorization Envelopes, handoffs, Milestones, gates, review and repository actions.

This specification SHALL NOT redefine those responsibilities inconsistently.

## Terms

### Initiation Run

An Initiation Run is one bounded progression from a request to start a project through the accepted initial baseline and transition to continuing Milestone delivery.

### Preference Profile

A Preference Profile is the transient, structured interpretation of the Project Owner's stated preferences. It distinguishes binding requirements from defaults and SHALL NOT create authority by inference.

### Decision Skeleton

A Decision Skeleton identifies the decisions required now, their provisional ASI, responsible authority, recommended direction and decisions explicitly deferred.

It is a planning view and SHALL NOT make a decision governing before its required authority acts.

### Foundation Package

A Foundation Package is the decision-ready proposal containing project identity, problem, mission, scope, authority, roles, constraints, Decision Skeleton and first-Milestone recommendation.

### Initialization Baseline

The Initialization Baseline is the reviewed repository and knowledge state from which continuing Milestone delivery begins.

## Governing Rules

### Architect-owned progression

The assigned Architect function SHALL own progression through the initiation phases.

When a phase's completion criteria are satisfied and no human-reserved decision or stop condition applies, the Architect SHALL advance to the next phase automatically.

The Architect SHALL NOT ask the Project Owner what procedural phase comes next when this specification defines the transition.

Progress updates MAY identify the current phase and next transition, but SHALL NOT transfer phase-management responsibility to the Project Owner.

### Decision-ready interaction

When human input is required, the Architect SHALL present:

- the decision being requested;
- the recommended option;
- material alternatives;
- consequences and risks;
- confirmed facts, assumptions and unresolved material uncertainty;
- the exact scope authorized by acceptance.

The Architect SHOULD consolidate related material questions into one interaction. It SHALL NOT interrupt progression for a non-material preference that can be resolved safely through the Preference Profile and documented as an assumption.

### Preference classification

Every preference that affects the Foundation Package or first Milestone SHALL be classified as one of:

- `required`: explicitly binding within the stated scope;
- `preferred`: the default unless evidence justifies another choice;
- `open`: intentionally left for analysis or later decision;
- `assumed`: inferred provisionally and disclosed for review.

Silence, tool availability, an existing local installation or a provider default SHALL NOT convert a preference into a requirement or authority.

### Minimal persistence

Discovery notes, conversation transcripts, Preference Profiles, Decision Skeletons, Authorization Envelopes and Implementation Handoffs MAY remain transient.

They SHALL be persisted only when required for authority, recovery, audit or reusable knowledge.

The Project Charter SHOULD normally be the first maintained project artifact after the foundation is approved. Another first artifact MAY be selected when a distinct current responsibility justifies it and the Foundation Package explains why.

Empty directories, placeholder files and speculative architecture SHALL NOT be created during initiation.

## Initiation Phase Model

Except for PI-0 and recovery governed by this specification, a phase enters only after the preceding phase has satisfied its completion criteria and every applicable gate has a recorded decision. Authority and the relevant execution base SHALL remain valid at phase entry.

The normative phase sequence is:

| Phase | Name | Responsible function | Primary result | Default transition |
| --- | --- | --- | --- | --- |
| PI-0 | Trigger | Architect | Initiation responsibility established | Automatic to PI-1 |
| PI-1 | Observation and Discovery | Architect | Sufficient confirmed context | Automatic to PI-2 |
| PI-2 | Synthesis | Architect | Preference Profile and Decision Skeleton | Automatic to PI-3 |
| PI-3 | Foundation Proposal | Architect | Decision-ready Foundation Package | Human gate PI-G1 |
| PI-4 | Foundation Materialization | Architect or Builder | Canonical project foundation | Automatic to PI-5 |
| PI-5 | Architecture and Milestone Definition | Architect | Approved decisions and bounded first Milestone | Conditional gates only |
| PI-6 | Execution Contract | Architect | Authorization Envelope and Implementation Handoff | Automatic to PI-7 |
| PI-7 | Execution and Correction | Builder and Reviewer | Implemented and verified first Milestone | Automatic to PI-8 |
| PI-8 | Review and Baseline | Reviewer and human authority when required | Reviewed result and authorized repository state | Required acceptance when applicable |
| PI-9 | Continuation | Architect | Next Milestone selected or project paused | Initialization complete |

An Initiation Run SHALL record its current phase transiently or durably enough to resume without repeating an effect or human decision.

## PI-0 — Trigger

### Entry

PI-0 begins when a human requests a new project, product, repository or maintained engineering responsibility.

### Responsibilities

The Architect SHALL:

- recognize the request as project initiation;
- identify the Project Owner or disclose that authority is unresolved;
- identify the applicable WEM version;
- establish whether a workspace or repository already exists;
- preserve unrelated existing state.

### Completion and transition

PI-0 completes when initiation authority and workspace scope are known sufficiently to perform read-only observation. It transitions automatically to PI-1.

Missing ownership authority is a blocking gate.

## PI-1 — Observation and Discovery

### Responsibilities

The Architect SHALL inspect available repository and maintained context before relying on conversation alone.

Discovery SHALL obtain, with depth proportional to the project:

- the problem and intended users;
- desired outcomes and evidence of success;
- explicit scope and exclusions;
- legal, operational, cost, time and platform constraints;
- Project Owner preferences and reserved decisions;
- existing systems, data or repositories affected;
- the desired level of automation and autonomy.

The Architect SHOULD ask one consolidated set of questions only when missing answers can materially change the Foundation Package or first Milestone.

### Completion and transition

PI-1 completes when remaining uncertainty can be classified and exposed without guessing a material project decision. It transitions automatically to PI-2.

## PI-2 — Synthesis

### Responsibilities

The Architect SHALL produce a transient synthesis that separates:

- confirmed facts;
- required constraints;
- preferences;
- assumptions;
- uncertainties;
- decisions required now;
- decisions safely deferred;
- apparent conflicts;
- the smallest useful first Milestone.

The Architect SHALL classify material decisions provisionally under the ASI and ADR rules.

Non-material choices MAY receive a recommended default. The Architect SHALL identify the evidence or preference supporting that default.

### Completion and transition

PI-2 completes when the Foundation Package can be evaluated without private reasoning or missing material context. It transitions automatically to PI-3.

## PI-3 — Foundation Proposal

### Required result

The Foundation Package SHALL identify:

- project name and type;
- declared WEM version;
- repository or workspace responsibility;
- problem statement and mission;
- intended users and expected outcomes;
- scope in and scope out;
- Project Owner and final authority;
- initial operational role assignments;
- binding constraints and classified preferences;
- Decision Skeleton with required and deferred decisions;
- recommended first maintained artifact;
- recommended first Milestone;
- acceptance criteria and major risks;
- the exact human decision requested.

### Gate PI-G1 — Foundation Decision

The Project Owner SHALL accept, reject or modify the Foundation Package.

Acceptance authorizes only the foundation and actions explicitly included in the package. It SHALL NOT silently authorize product implementation, external publication or a later human-reserved decision.

After acceptance, progression continues automatically to PI-4. Rejection ends or redirects the Initiation Run. Requested changes return to the earliest affected phase without repeating unaffected work.

## PI-4 — Foundation Materialization

### Responsibilities

The Architect or authorized Builder SHALL create only the accepted foundation artifacts and repository state.

The operation SHALL:

- re-observe the execution base before mutation;
- create the first maintained artifact in its canonical location;
- activate no empty or speculative structure;
- preserve exact accepted mission, scope and authority;
- run applicable structural and coherence verification;
- perform only repository actions already authorized.

### Completion and transition

PI-4 completes when the foundation exists, matches the accepted package and has received the required technical review. It transitions automatically to PI-5.

A material discrepancy returns to PI-3. An operational correction within the accepted foundation remains inside PI-4.

## PI-5 — Architecture and First-Milestone Definition

### Responsibilities

The Architect SHALL determine the minimum decisions required before the first Milestone can execute safely.

It SHALL:

- avoid deciding architecture not needed by the first Milestone;
- prepare ADRs only when required by classification or authority;
- identify accepted architecture, local implementation choices and deferred decisions separately;
- define the first Milestone as an evaluable outcome rather than a list of disconnected artifacts;
- select focused, Milestone and release verification profiles;
- define scope, limits, correction cycles, repository actions and stop conditions.

### Conditional gates

PI-5 creates a human gate only for:

- an ASI-4 or ASI-5 decision;
- an ASI-2 or ASI-3 decision whose governing authority requires human approval;
- a material change to the accepted foundation;
- an external, legal, destructive, credential, publication or budget decision not covered by PI-G1.

Other decisions proceed under their assigned authority and recorded traceability.

### Completion and transition

PI-5 completes when the first Milestone has sufficient accepted architecture and a bounded execution plan. It transitions automatically to PI-6.

## PI-6 — Execution Contract

### Responsibilities

The Architect SHALL prepare a self-sufficient execution contract for the first Milestone.

One bounded instruction MAY combine the Authorization Envelope, Implementation Handoff and Work Package or Milestone authorization.

The contract SHALL identify:

- objective and Milestone outcome;
- execution base;
- governing sources and accepted decisions;
- scope in and out;
- permitted responsibilities, paths, tools and effects;
- deliverables and acceptance criteria;
- verification profiles;
- attempt, correction, time, cost or context limits when applicable;
- repository actions and their conditions;
- human-reserved decisions;
- stop and escalation conditions.

### Completion and transition

PI-6 completes when the receiving Builder can execute without access to private conversation and the contract fits within current authority. It transitions automatically to PI-7.

It creates a gate only when execution authority has not already been granted or the contract exposes a new material decision.

## PI-7 — Execution and Correction

### Responsibilities

The Builder SHALL implement the authorized Milestone, run focused verification and disclose deviations and limitations.

Builder and Reviewer functions MAY perform bounded correction cycles automatically while:

- scope and architecture remain valid;
- no human-reserved decision is required;
- limits remain available;
- the execution base remains compatible;
- no ambiguous effect has occurred.

The Architect SHALL NOT interrupt the Project Owner for deterministic implementation corrections inside these boundaries.

### Completion and transition

PI-7 completes when the Milestone is implemented or reaches a defined stopped, blocked or failed outcome with sufficient evidence. It transitions automatically to PI-8.

## PI-8 — Review and Initialization Baseline

### Responsibilities

The Reviewer SHALL evaluate:

- correctness and Milestone acceptance criteria;
- complete diff and scope compliance;
- focused and Milestone verification;
- repository and workspace state;
- architecture and governance coherence;
- failures, deviations, limitations and unintended effects.

The Review Result SHALL be `Accepted for the next authorized gate` or `Changes requested`.

Changes requested return to PI-7 when correction remains authorized. A material scope or architecture change returns to PI-5 or the earliest affected phase.

### Acceptance and repository action

Human acceptance is required when reserved by the Foundation Package, Milestone authorization, applicable ASI, publication or release governance.

Preauthorized commit or push MAY proceed after their conditions are verified without a separate approval message. Publication and release remain human decisions.

### Completion and transition

PI-8 completes when blocking findings are resolved or explicitly accepted, required human acceptance is recorded and authorized repository actions are complete or intentionally deferred. It transitions automatically to PI-9.

## PI-9 — Continuation

The Architect SHALL close initiation by presenting:

- the Initialization Baseline;
- achieved and deferred outcomes;
- unresolved non-blocking risks;
- the recommended next Milestone;
- any decision genuinely required before that Milestone.

If the next Milestone is already authorized and no gate applies, the Architect SHALL begin it automatically under the standard Milestone workflow.

If authorization is required, the Architect SHALL present one decision-ready Milestone proposal rather than ask an open-ended question about what to do next.

Initialization is complete when the project has an accepted foundation, a reviewed initial baseline and an explicit continuation state.

## Stop and Escalation Conditions

An Initiation Run SHALL stop or escalate when:

- Project Owner authority is absent or disputed;
- material intent remains contradictory after consolidated clarification;
- an ASI-4 or ASI-5 decision lacks approval;
- an action would exceed the active authorization;
- destructive, credential, legal, publication or sensitive-data effects lack authority;
- the execution base has drifted materially;
- a required check is unavailable or failed at its applicable gate;
- an external effect is ambiguous;
- continuing would require inventing a material preference or authority.

Difficulty, silence from a tool, a deterministic implementation defect or the existence of multiple reasonable local choices SHALL NOT alone create a Project Owner gate.

## Progress Reporting

During initiation, progress reports SHOULD state:

- current phase;
- result completed since the previous report;
- material assumptions or risks;
- next automatic phase;
- whether a human gate is approaching and why.

At a human gate, the final response SHALL be self-contained and SHALL NOT require the Project Owner to reconstruct prior commentary.

## Recovery and Resumption

After interruption, the Architect SHALL inspect actual repository and execution state, identify the last completed phase and resume from the earliest phase whose completion evidence remains valid.

Completed human decisions SHALL NOT be requested again unless their scope, assumptions or execution base have changed materially.

Preparation errors that occur before an authorized external effect MAY be corrected without consuming an execution attempt when the active envelope permits it.

## Verification

Conformance verification SHOULD cover at least:

1. sufficient conversational context advances without an unnecessary question;
2. a preference remains distinguishable from a requirement;
3. one consolidated clarification resolves material ambiguity;
4. a Foundation Package produces the PI-G1 gate;
5. acceptance advances automatically through foundation materialization;
6. a local correction does not create a human gate;
7. an ASI-4 decision stops at the correct gate;
8. a preauthorized commit proceeds after verification without redundant approval;
9. interruption resumes without repeating a human decision or external effect;
10. PI-9 proposes or begins the next Milestone without asking what procedural step comes next.

## Adoption

A project adopting this specification MAY map its existing discovery, inception or project-setup process to the phases defined here when entry conditions, results, transitions and gates remain explicit.

Projects MAY rename phases in their user interface. Automation SHALL preserve the normative responsibilities and authority boundaries even when phase names are hidden from the Project Owner.

## Evolution

Changes to the phase sequence, automatic-transition rule, foundation gate, preference classification or completion boundary SHALL be classified as ASI-3 or higher according to their effect.

Changes to final human authority, ASI-4/5 gates or publication and release authority SHALL be classified as ASI-5.

Editorial clarification and provider-specific interaction wording MAY follow lower governance when normative meaning is unchanged.

## End of Specification
