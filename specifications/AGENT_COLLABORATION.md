---
Document: Agent Collaboration
Title: Workspace Engineering Method Human and AI Collaboration Governance
Version: 1.0.0
Status: Released
Type: Governance
ASI: 4
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method Human and AI Collaboration Governance

## Purpose

This specification defines the roles, authority boundaries and collaboration controls used when human and AI participants work together on WEM engineering responsibilities.

It establishes explicit handoffs, review workflow, controlled concurrency, conflict prevention, interaction boundaries and completion criteria while preserving final human accountability.

It also defines provider-independent logical contracts that allow authorized collaboration to be automated without turning human authority into a requirement for human message mediation.

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Status and Authority

This specification is Released as part of WEM 1.0.0 following the required cross-document coherence review and explicit Project Owner approval recorded in `decisions/WEM-ADR-008.md`.

`decisions/WEM-ADR-002.md` and `decisions/WEM-ADR-006.md` are Accepted, and the role-based, automation-ready collaboration model defined here governs WEM collaboration.

Release of this specification does not create additional provider-specific entry files, executable orchestration products or transferred decision authority.

---

## Scope

This specification governs:

- generic collaboration roles;
- authority boundaries between those roles;
- explicit transfer of work and context;
- proposal, implementation, review and acceptance workflow;
- controlled concurrency and workspace ownership;
- conflict detection and escalation;
- optional programmatic orchestration;
- Authorization Envelopes;
- structured Implementation Handoffs;
- Builder Results and Verification Evidence;
- Review Results;
- bounded correction loops;
- proportional traceability and persistence;
- replaceable adapter boundaries;
- completion criteria for collaborative tasks;
- proportional assignment of participants to roles.

This specification does not define:

- project objectives or final ownership authority;
- ASI levels or Architectural Pause requirements;
- ADR structure or lifecycle;
- repository architecture;
- Sprint planning or milestone sequence;
- provider-specific prompts or instructions;
- native communication capabilities of a particular platform;
- provider-specific repository entry files;
- executable orchestrators, scripts, command-line tools, services or pipelines;
- market validation, finance or general business governance.

Those concerns remain governed by their responsible specifications or future explicitly activated responsibilities.

---

## Governing Principles

This specification applies the following Engineering Principles as authoritatively defined in `ENGINEERING_PRINCIPLES.md`:

- `WEM-P-001` — Responsibility Before Structure;
- `WEM-P-002` — Separation of Knowledge and Products;
- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-005` — Technology-Independent Method;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

These references do not redefine their normative meaning.

---

## Normative Dependencies

This specification applies collaboration-specific requirements within the boundaries established by:

- `WEM.md`, for the engineering lifecycle, ASI and Architectural Pause;
- `PROJECT_CHARTER.md`, for project ownership and final decision authority;
- `ENGINEERING_PRINCIPLES.md`, for permanent Engineering Principles and deviation governance;
- `specifications/ADR_SPECIFICATION.md`, for ADR applicability, lifecycle and approval;
- `specifications/REPOSITORY_BLUEPRINT.md`, for canonical artifact responsibilities and locations;
- `decisions/WEM-ADR-001.md`, for the accepted WEM repository architecture;
- `decisions/WEM-ADR-002.md`, for the accepted role-based, human-controlled collaboration architecture;
- `decisions/WEM-ADR-006.md`, for the accepted automation-ready collaboration architecture.

This specification SHALL reference those authoritative definitions and SHALL NOT redefine them inconsistently.

---

## Collaboration Model

WEM uses role-based, human-controlled collaboration governance.

The collaboration model defines three generic roles:

- Project Owner and Final Authority;
- Architect and Reviewer;
- Builder.

Roles define responsibilities and authority, not a particular person, provider, model or tool.

Operational assignments MAY change without changing the normative role definitions.

Participants, agents, models and providers assigned to roles are replaceable operational configuration and SHALL NOT become normative WEM dependencies.

A participant MAY perform more than one role when the assignment is explicit and the required authority and review separation are preserved.

The participant that implements a significant change SHOULD NOT be its only reviewer.

No combination of roles SHALL allow an AI collaborator to assume final human decision authority.

WEM does not require any fixed number of AI participants.

---

## Authority Boundaries

The Project Owner and Final Authority is a human role.

The Project Owner and Final Authority retains the authority defined in `PROJECT_CHARTER.md`, including approval of ASI-4 and ASI-5 decisions.

Human authority SHALL NOT be interpreted as requiring the human authority to transport every message between authorized participants.

An explicit human authorization MAY permit actions within defined boundaries to proceed without repeated human mediation when the applicable governance does not reserve a later human decision.

The Architect and Reviewer and the Builder MAY analyze, propose, implement, verify and document work within explicitly authorized scope.

They SHALL NOT:

- accept an ADR on behalf of the Project Owner and Final Authority;
- approve their own ASI-4 or ASI-5 proposal on behalf of the responsible human authority;
- expand an approved responsibility without identifying the scope change;
- treat tool access, successful execution or repository write permission as decision authority;
- commit, merge, publish or release unless that repository action has been authorized.

When authority is unclear or disputed, affected work SHALL pause and return to the Project Owner and Final Authority for resolution.

---

## Roles

### Project Owner and Final Authority

The Project Owner and Final Authority establishes intent and makes the human decisions reserved to project ownership.

Within the collaboration workflow, this role SHALL:

- define or approve the objective and task scope;
- resolve material ambiguity in desired outcomes;
- review alternatives for significant decisions;
- approve, reject or modify ASI-4 and ASI-5 proposals;
- resolve authority or collaborator conflicts;
- accept or reject completed work;
- authorize repository actions when required.

This role MAY pause, redirect or cancel collaborative work.

### Architect and Reviewer

The Architect and Reviewer protects coherence between intent, WEM governance, architecture and implementation.

This role SHALL:

- read the applicable maintained specifications and accepted ADRs;
- inspect the actual repository and Git state;
- distinguish confirmed facts from assumptions;
- identify decisions that require ASI classification or an Architectural Pause;
- evaluate relevant alternatives, consequences and risks;
- prepare bounded implementation plans and handoffs;
- review the implementation diff and verification evidence;
- identify unnecessary scope expansion or normative inconsistency;
- report review findings before human acceptance.

This role SHALL NOT present its review as final human acceptance.

### Builder

The Builder implements work that has received the authority required by its scope.

This role SHALL:

- verify the starting repository state;
- implement only the approved objective and file boundaries;
- preserve unrelated work;
- follow applicable specifications and Accepted ADRs;
- run the required tests, linters or validation checks;
- disclose failed validation, deviations, blockers and unexpected conditions;
- summarize changed files and verification evidence;
- address approved review findings.

If implementation reveals an architectural conflict or an inadequate approved design, the Builder SHALL stop the affected work and return it for architectural and human review.

---

## Automation-Ready Collaboration

WEM collaboration SHALL remain executable through interactive and non-interactive mechanisms without redefining its governance.

Automation MAY use command-line invocation, APIs, continuous integration, MCP or other current or future mechanisms.

Automation SHALL remain optional and SHALL be applied with governance proportional to the scope and cost of the work.

Human Final Authority SHALL be preserved without requiring human message mediation between authorized participants.

An initial human authorization MAY allow actions within explicitly approved boundaries to proceed without repeated human mediation when the applicable governance does not reserve a later human decision.

Automation SHALL NOT transfer authority, expand approved scope or bypass an Architectural Pause, required ADR or human approval.

---

## Authorization Envelope

Every automated collaboration execution SHALL operate within an explicit Authorization Envelope.

The Authorization Envelope SHALL identify, with detail proportional to the execution:

- objective;
- approved scope;
- applicable authority;
- permitted participants or tools;
- permitted files and responsibilities;
- permitted repository actions;
- applicable limits;
- human-reserved decisions;
- stopping and escalation conditions.

Applicable limits SHALL include attempt or iteration limits and SHOULD include time or cost limits when those limits are relevant to the execution.

Repository actions such as commit, push, merge, publication or release SHALL be permitted only when the responsible authority explicitly includes the applicable action in the Authorization Envelope or provides a separate authorization.

Tool access, repository permissions and successful execution SHALL NOT expand the Authorization Envelope.

An Authorization Envelope SHALL NOT pre-authorize a decision whose governing specification requires human approval after evaluation of the resulting proposal, evidence or review.

---

## Proportional Role Topology

WEM SHALL NOT require two AI participants or any fixed number of automated participants.

A participant MAY perform multiple roles or authorized functions when the assignment is explicit and proportional governance permits it.

The Architect and Reviewer role contains distinct Architect and Reviewer functions that MAY be assigned separately without creating additional normative roles.

For significant changes, the Builder SHOULD NOT be the only Reviewer.

Combining roles or functions SHALL NOT combine or transfer their authorities.

ASI-4 and ASI-5 decisions SHALL continue to require the human intervention defined by their governing specifications.

---

## Structured Implementation Handoff

The Architect function SHALL transform relevant context and approved decisions into a structured, verifiable Implementation Handoff for the Builder.

The Implementation Handoff SHALL identify, with detail proportional to the work:

- task identifier;
- objective;
- base commit or starting repository state;
- governing specifications and Accepted ADRs;
- approved decisions;
- assumptions and uncertainties;
- scope in;
- scope out;
- expected deliverables;
- acceptance criteria;
- verification;
- permitted actions;
- stopping and escalation conditions.

The Implementation Handoff SHALL be sufficient for the Builder to interpret the task without access to the Architect's private conversation or conversational state.

Conversation MAY provide input context, but SHALL NOT be the execution contract.

The depth and formality of an Implementation Handoff SHALL be proportional to the scope and cost of the transferred work.

A single bounded task instruction MAY satisfy the Implementation Handoff requirements when every required element is explicit or identified as not applicable.

When the same participant performs multiple authorized functions, logical collaboration contracts MAY be combined or represented within the execution context instead of requiring separate persistent artifacts, provided that scope, authority, acceptance criteria, verification and escalation boundaries remain explicit and verifiable.

The receiving function SHALL inspect the actual repository state before relying on the Implementation Handoff.

An Implementation Handoff SHALL NOT silently transfer approval authority.

---

## Standard Collaboration Workflow

The workflow SHALL be applied with governance proportional to the scope and cost of change.

For routine, local and readily reversible work, adjacent phases MAY be combined and handoffs MAY be concise, provided that authority, scope, verification and completion remain explicit.

Phases required by an Architectural Pause, ADR or human approval SHALL NOT be omitted when applicable.

### Phase 1 — Intent

The Project Owner and Final Authority defines the problem, desired outcome and relevant constraints.

### Phase 2 — Analysis

The Architect and Reviewer inspects maintained knowledge and repository state, identifies assumptions and evaluates the applicable governance.

If the work affects ASI-4 or ASI-5, the Architectural Pause and ADR requirements defined by the responsible specifications SHALL apply before affected implementation continues.

### Phase 3 — Proposal

The Architect and Reviewer presents the recommended approach, relevant alternatives, consequences, affected responsibilities, acceptance criteria and required verification.

### Phase 4 — Human Decision

The Project Owner and Final Authority approves, rejects or modifies the proposal when human approval is required.

Approval SHALL be explicit and SHALL NOT be inferred solely from continued conversation or tool access.

### Phase 5 — Implementation Handoff

The Architect and Reviewer prepares the Structured Implementation Handoff required by this specification.

### Phase 6 — Implementation

The Builder verifies the starting state, implements the approved scope and produces the Builder Result and Verification Evidence required by this specification.

### Phase 7 — Review

The Architect and Reviewer reviews the complete diff, verification evidence, scope compliance and documentation coherence.

The Reviewer produces the Review Result required by this specification.

### Phase 8 — Correction

The Builder addresses authorized findings and repeats the required verification within the Bounded Correction Loop.

### Phase 9 — Human Acceptance

When required by the applicable governance, ASI level, task authorization or repository policy, the Project Owner and Final Authority accepts the result, requests further changes or closes the work without acceptance.

For work that does not require human acceptance, an authorized review result MAY complete this phase.

Human acceptance SHALL NOT be inferred from continued conversation, tool access or successful execution.

### Phase 10 — Repository Action

After the required acceptance and repository authorization, the responsible participant verifies Git state, reviews the final staged diff and performs only the repository actions permitted by the Authorization Envelope or a separate explicit authorization.

---

## Builder Result and Verification Evidence

The Builder SHALL return a structured Builder Result that identifies:

- implementation status;
- changed files;
- the complete diff or its recoverable location;
- tests and validation performed;
- failures and limitations;
- deviations;
- unresolved questions;
- repository state;
- confirmation that the Authorization Envelope was respected.

Verification Evidence SHALL be sufficient to evaluate the applicable acceptance criteria and SHALL identify incomplete, failed or unavailable validation.

Tool completion or a successful command SHALL NOT by itself establish successful implementation.

---

## Review Result

The Reviewer SHALL return one explicit technical Review Result:

- Accepted for the next authorized gate; or
- Changes requested.

Each finding in a Changes requested result SHALL be specific and verifiable.

Accepted for the next authorized gate means that the reviewed result satisfies the applicable technical review contract.

It SHALL NOT be interpreted as human acceptance, ADR acceptance, publication approval or release approval when one of those decisions is required.

---

## Traceability and Persistence

A structured Authorization Envelope, Implementation Handoff, Builder Result, Review Result or item of Verification Evidence SHALL NOT by itself require permanent storage.

Persistence SHALL be proportional to the applicable governance, the significance of the work and the value of the artifact as reusable knowledge.

Significant decisions and evidence required by their governing specifications SHALL remain traceable according to those specifications.

Routine execution messages, intermediate contracts and verification details MAY remain transient when their preservation is not required for acceptance, traceability, audit or reusable knowledge.

When persistent traceability is required, the responsible maintained artifact or recoverable location SHALL be identified explicitly.

---

## Bounded Correction Loop

Builder and Reviewer functions MAY repeat implementation, verification, review and correction automatically while:

- the work remains within the Authorization Envelope;
- no decision reserved to human authority is required;
- the approved architecture does not change;
- the applicable attempt, iteration, time and cost limits are not exceeded;
- no stopping or escalation condition occurs.

The maximum number of correction cycles SHALL be defined by the Authorization Envelope or explicitly authorized operational configuration.

Time and cost limits SHOULD be defined when they are relevant to the execution.

The correction loop SHALL stop and escalate when:

- a configured limit is reached;
- an architectural conflict appears;
- required authority is unavailable;
- the base commit or starting repository state is no longer valid;
- a requested correction would exceed approved scope;
- another stopping or escalation condition in the Authorization Envelope occurs.

---

## Review Independence

Review SHALL evaluate correctness, approved scope, applicable governance, verification evidence and unintended changes.

Successful execution SHALL NOT by itself establish architectural correctness or task acceptance.

When the Architect and Reviewer also implements a change, another authorized reviewer or the Project Owner and Final Authority SHOULD review significant work before acceptance.

Blocking findings SHALL be resolved or explicitly accepted by the responsible human authority before completion.

---

## Controlled Concurrency

Every active implementation task SHALL have explicit workspace or file ownership.

Collaborators SHALL NOT modify the same files concurrently in a shared workspace.

Parallel work MAY proceed when:

- responsibilities or file sets do not overlap; or
- separate branches or worktrees provide explicit isolation.

Parallel work SHALL identify:

- each task owner;
- permitted files or responsibilities;
- the integration owner;
- the expected integration order;
- conflict review requirements.

Shared access to a repository does not imply shared ownership of active changes.

---

## Conflict Prevention and Escalation

Before editing, each collaborator SHALL:

- inspect Git and workspace state;
- identify pre-existing tracked and untracked changes;
- confirm active task scope;
- preserve unrelated work;
- verify that no other participant owns the same files in the active workspace.

If unexpected overlapping changes are detected, affected work SHALL pause.

The conflict SHALL be reported with the affected files, known ownership and available reconciliation options.

No collaborator SHALL overwrite, discard, stage or commit another participant's work without explicit authorization.

Architectural conflicts SHALL return to the Architect and Reviewer and, when required by authority or ASI, to the Project Owner and Final Authority.

---

## Agent Interaction Model

AI collaborators SHALL NOT assume native conversational context with another AI collaborator.

Coordination between participants SHALL therefore use, as applicable:

- maintained repository specifications and Accepted ADRs;
- Authorization Envelopes;
- Structured Implementation Handoffs;
- Builder Results and Verification Evidence;
- Review Results;
- Git status, diffs and commits;
- explicitly authorized orchestration mechanisms;
- human decisions when reserved or required by the applicable governance.

The ability of multiple agents to read the same repository SHALL NOT be treated as evidence that they share conversational context.

Human authority SHALL NOT require human transport of messages that an authorized mechanism can transfer within the Authorization Envelope.

---

## Programmatic Orchestration

Command-line invocation, automation APIs or similar mechanisms MAY be used to invoke or coordinate collaborators only within an applicable Authorization Envelope.

Programmatic orchestration is not native agent-to-agent communication and SHALL NOT transfer human approval authority.

Programmatic orchestration SHALL use the Structured Implementation Handoff, Builder Result, Verification Evidence and Review Result requirements applicable to the execution.

The orchestrating function remains responsible for reporting the invocation result, enforcing applicable limits and preserving authority boundaries.

Programmatic orchestration SHALL NOT bypass an Architectural Pause, ADR requirement or required human approval.

---

## Replaceable Adapters

Participants and automation mechanisms MAY integrate through replaceable adapters.

An adapter MAY describe:

- invocation method;
- input and output format;
- available capabilities;
- permission model;
- timeout and failure behavior;
- provider-specific restrictions.

An adapter SHALL remain an operational interface and SHALL reference the applicable canonical WEM specifications and Accepted ADRs.

An adapter SHALL NOT redefine roles, authority, ASI, ADR governance, collaboration governance or repository architecture.

Replacing a participant, model, provider or invocation mechanism SHALL NOT require a change to normative WEM governance unless the replacement changes a normative responsibility or authority boundary.

---

## Separation from Executable Products

This specification defines governance and logical collaboration contracts only.

Executable orchestrators, scripts, command-line tools, services, pipelines, queue systems and runtime integrations are product implementations outside the responsibility of the WEM knowledge repository.

When an executable orchestration responsibility becomes real, it SHALL be maintained as a separate product that adopts WEM and defines its own repository architecture, licensing and decision governance.

Physical templates, temporary handoff files and queue artifacts SHALL NOT be created in the WEM repository merely because their logical information is defined by this specification.

---

## Completion Criteria

A collaborative task is complete only when:

- the approved objective and scope have been implemented;
- required verification has completed;
- failures, deviations and limitations have been disclosed;
- the complete diff has been reviewed;
- the applicable Authorization Envelope has been respected;
- blocking findings have been resolved or explicitly accepted;
- the Project Owner and Final Authority has accepted the result when required;
- repository actions have been authorized and remain traceable;
- maintained knowledge has been updated when the accepted work changes it.

Completion of implementation does not by itself authorize commit, publication or release.

---

## Evolution

Changes to generic roles, authority boundaries, Authorization Envelopes, logical collaboration contracts, review responsibility, controlled concurrency, correction-loop governance or completion governance affect the collaboration architecture and SHALL be classified as ASI-4 or higher according to their actual scope and cost of change.

Provider-specific operational instructions MAY follow lower governance when they do not change normative collaboration meaning or human authority.

Editorial corrections that do not change normative meaning SHALL follow proportional governance.

---

## End of Specification
