---
Document: Agent Collaboration
Title: Workspace Engineering Method Human and AI Collaboration Governance
Version: 1.0.0
Status: Draft
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

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Status and Authority

This document remains Draft throughout Sprint 0 and until the required cross-document coherence review is complete.

While `decisions/WEM-ADR-002.md` remains Proposed, the collaboration governance defined here is not governing and SHALL NOT be treated as an accepted WEM responsibility.

If `decisions/WEM-ADR-002.md` becomes Accepted, this collaboration model becomes authorized for controlled application while this specification remains Draft.

Publication of this Draft does not create provider-specific entry files or transfer decision authority.

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
- completion criteria for collaborative tasks;
- operational assignment of participants to roles.

This specification does not define:

- project objectives or final ownership authority;
- ASI levels or Architectural Pause requirements;
- ADR structure or lifecycle;
- repository architecture;
- Sprint planning or milestone sequence;
- provider-specific prompts or instructions;
- native communication capabilities of a particular platform;
- `AGENTS.md`, `CLAUDE.md` or other provider-specific repository entry files.

Those concerns remain governed by their responsible specifications or future explicitly activated responsibilities.

---

## Governing Principles

This specification applies the following Engineering Principles as authoritatively defined in `ENGINEERING_PRINCIPLES.md`:

- `WEM-P-001` — Responsibility Before Structure;
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
- `decisions/WEM-ADR-001.md`, for the accepted WEM repository architecture.

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

A participant MAY perform more than one role when the assignment is explicit and the required authority and review separation are preserved.

The participant that implements a significant change SHOULD NOT be its only reviewer.

No combination of roles SHALL allow an AI collaborator to assume final human decision authority.

---

## Authority Boundaries

The Project Owner and Final Authority is a human role.

The Project Owner and Final Authority retains the authority defined in `PROJECT_CHARTER.md`, including approval of ASI-4 and ASI-5 decisions.

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

## Explicit Handoffs

A transfer of responsibility between collaboration roles SHALL use an explicit handoff.

The handoff SHALL identify:

- the objective;
- relevant maintained context and accepted decisions;
- assumptions and known uncertainties;
- constraints and authority boundaries;
- files or responsibilities in scope;
- files or responsibilities out of scope;
- expected deliverables;
- acceptance criteria;
- required verification;
- stopping and escalation conditions.

The depth and formality of a handoff SHALL be proportional to the scope and cost of the transferred work.

A single bounded task instruction MAY satisfy the handoff requirements when every required element is explicit or identified as not applicable.

The receiving role SHALL inspect the actual repository state before relying on the handoff.

A handoff SHALL NOT silently transfer approval authority.

Conversation history MAY provide operational context, but SHALL NOT replace maintained specifications, accepted ADRs or explicit task boundaries.

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

The Architect and Reviewer prepares a bounded handoff for the Builder.

### Phase 6 — Implementation

The Builder verifies the starting state, implements the approved scope and produces verification evidence.

### Phase 7 — Review

The Architect and Reviewer reviews the complete diff, verification evidence, scope compliance and documentation coherence.

The review result SHALL identify either:

- Ready for owner review; or
- Changes requested, with specific and verifiable findings.

### Phase 8 — Correction

The Builder addresses approved findings and repeats the required verification.

Review and correction MAY repeat until no blocking finding remains.

### Phase 9 — Human Acceptance

When required by the applicable governance, ASI level, task authorization or repository policy, the Project Owner and Final Authority accepts the result, requests further changes or closes the work without acceptance.

For work that does not require human acceptance, an authorized review result MAY complete this phase.

Human acceptance SHALL NOT be inferred from continued conversation, tool access or successful execution.

### Phase 10 — Repository Action

After the required acceptance and repository authorization, the responsible participant verifies Git state, reviews the final staged diff and performs only the authorized commit, merge, publication or release action.

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

In the initial operational assignment, Codex and Claude Code do not share a native conversation, shared model memory or automatically synchronized intent.

Their default coordination SHALL therefore use:

- maintained repository specifications and Accepted ADRs;
- explicit handoffs;
- bounded implementation instructions;
- Git status, diffs and commits;
- review findings;
- human-mediated decisions.

The ability of multiple agents to read the same repository SHALL NOT be treated as evidence that they share conversational context.

---

## Programmatic Orchestration

Command-line invocation, automation APIs or similar mechanisms MAY be used to invoke one collaborator from another only when that orchestration has been explicitly authorized.

Programmatic orchestration is not native agent-to-agent communication and SHALL NOT transfer human approval authority.

Before invoking another collaborator programmatically, the orchestrating role SHALL define:

- the exact task;
- the authorized participant or tool;
- permitted files and actions;
- required permissions;
- expected output and verification;
- stopping and escalation conditions;
- timeout or failure handling;
- how the result will be reviewed.

The orchestrating role remains responsible for reporting the invocation result and preserving authority boundaries.

Programmatic orchestration SHALL NOT bypass an Architectural Pause, ADR requirement or required human approval.

---

## Provider-Specific Repository Adapters

Provider-specific repository entry files such as `AGENTS.md` and `CLAUDE.md` are outside the scope of this specification.

They SHALL NOT be created until their separate responsibilities are explicitly activated.

If introduced later, they SHOULD remain concise adapters that reference canonical WEM specifications and Accepted ADRs.

They SHALL NOT become independent sources of collaboration governance, project architecture or human authority.

---

## Completion Criteria

A collaborative task is complete only when:

- the approved objective and scope have been implemented;
- required verification has completed;
- failures, deviations and limitations have been disclosed;
- the complete diff has been reviewed;
- blocking findings have been resolved or explicitly accepted;
- the Project Owner and Final Authority has accepted the result when required;
- repository actions have been authorized and remain traceable;
- maintained knowledge has been updated when the accepted work changes it.

Completion of implementation does not by itself authorize commit, publication or release.

---

## Initial Operational Assignment

This section records non-normative operational context for the initial WEM collaboration environment.

It does not redefine the generic roles or their authority.

| Participant | Initial role assignment |
| --- | --- |
| Arç | Project Owner and Final Authority |
| Codex | Architect and Reviewer |
| Claude Code | Builder |

Codex and Claude Code remain replaceable implementations of their assigned roles.

A change to this operational assignment does not change WEM governance unless it also changes a normative role, responsibility or authority boundary.

---

## Evolution

Changes to generic roles, authority boundaries, required handoffs, review responsibility, controlled concurrency or completion governance affect the collaboration architecture and SHALL be classified as ASI-4 or higher according to their actual scope and cost of change.

Provider-specific operational instructions MAY follow lower governance when they do not change normative collaboration meaning or human authority.

Editorial corrections that do not change normative meaning SHALL follow proportional governance.

---

## End of Specification
