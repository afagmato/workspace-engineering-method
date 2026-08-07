---
Document: Architecture Decision Record
Identifier: WEM-ADR-006
Title: Establish automation-ready collaboration governance
Status: Accepted
Created Date: 2026-08-07
ASI Level: 4
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-006 — Establish automation-ready collaboration governance

## Identifier

`WEM-ADR-006`

---

## Title

Establish automation-ready collaboration governance

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
| 2026-08-07 | Proposed | Project Owner | ASI-4 Architectural Pause opened for automation-ready collaboration governance. |
| 2026-08-07 | Accepted | Project Owner | Automation-ready collaboration governance approved and implementation authorized. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

WEM currently defines role-based, human-controlled collaboration governance through `specifications/AGENT_COLLABORATION.md` and the decision recorded in `decisions/WEM-ADR-002.md`.

That governance establishes the generic roles, explicit handoffs, review workflow, controlled concurrency, final human accountability and optional programmatic orchestration. It also correctly states that AI collaborators do not share native conversational context and that automation cannot transfer approval authority or bypass WEM governance.

When this decision was proposed, the collaboration model did not define complete logical contracts for an automated collaboration execution. Its handoff requirements did not identify an execution base, explicit permitted actions or a task identifier; its Builder result and review result were not defined as structured outputs; and its correction loop had no required execution bounds. Programmatic orchestration could therefore be authorized, but an implementation could not derive a complete and verifiable execution protocol from maintained WEM knowledge alone.

Human accountability does not require a human to transport every message manually between participants. A human authorization can establish bounded authority for a sequence of architecture, implementation, verification and review actions, while reserving decisions and escalation conditions that must return to the responsible human authority.

The collaboration architecture must remain independent from providers, models and invocation technologies. The current Codex and Claude Code assignment is useful operational context, but it cannot become the normative topology of WEM. Future participants may combine roles, use other providers or operate through non-interactive tools, APIs, command-line interfaces, continuous integration, MCP or mechanisms that do not yet exist.

WEM is a maintained engineering-knowledge repository. Defining collaboration governance and logical contracts belongs in this repository. Implementing an orchestrator, command-line tool, service, pipeline or other executable mechanism would activate a distinct product responsibility and therefore belongs in a separate product repository.

This decision is ASI-4 because it changes the durable collaboration and orchestration architecture, including authorization boundaries, handoff contracts, result contracts and correction-loop governance. The required Architectural Pause closed when the Project Owner accepted this ADR on 2026-08-07.

---

## Decision

The decision is to extend the role-based collaboration governance established by `decisions/WEM-ADR-002.md` with provider-independent, automation-ready logical contracts.

The authoritative normative definitions resulting from this decision are maintained in `specifications/AGENT_COLLABORATION.md`. This ADR remains the historical record of why the architecture was selected and does not replace that specification.

### Role-Based Architecture

WEM continues to define these normative roles:

- Project Owner and Final Authority;
- Architect and Reviewer;
- Builder.

Architect and Reviewer functions may be performed separately within an explicitly authorized assignment without creating provider-specific normative roles.

Participants, agents, models and providers assigned to those roles are replaceable operational configuration. WEM governance does not require Codex, Claude Code or any other named provider.

The current reference configuration may remain recorded in provider adapters and relevant historical ADRs as:

- Human Project Owner: Project Owner and Final Authority;
- Codex: Architect and Reviewer;
- Claude Code: Builder.

That configuration remains non-normative and replaceable.

### Automation-Ready Governance

WEM collaboration supports execution through interactive or non-interactive mechanisms without redefining its governance. Compatible mechanisms may include APIs, command-line interfaces, continuous integration, MCP and future invocation systems.

Automation remains optional. Its use and the depth of its controls follow governance proportional to the scope and cost of the work.

Human Final Authority is preserved without requiring human message mediation. An explicit initial human authorization may permit actions inside its approved boundaries to proceed without additional human transport or repeated approval when no governing specification requires human approval after evaluating the resulting work. Any action or decision outside those boundaries requires a new authorization or escalation.

### Authorization Envelope

Every automated collaboration execution operates within an explicit Authorization Envelope.

The envelope identifies, with detail proportional to the execution:

- objective;
- approved scope;
- applicable authority;
- permitted participants or tools;
- permitted files and responsibilities;
- permitted repository actions;
- time, cost or iteration limits when applicable;
- decisions reserved to human authority;
- stopping and escalation conditions.

Repository actions such as commit, push, merge, publication or release are permitted only when the responsible authority explicitly includes the applicable action in the envelope or provides a separate authorization.

An Authorization Envelope does not authorize bypassing an applicable Architectural Pause, required ADR or approval reserved to human authority. Tool access, repository permissions and successful execution do not expand the envelope.

An Authorization Envelope SHALL NOT pre-authorize a decision whose governing specification requires human approval after evaluation of the resulting proposal, evidence or review.

### Structured Implementation Handoff

The Architect function transforms relevant context and approved decisions into a structured, verifiable Implementation Handoff for the Builder.

The handoff identifies, with detail proportional to the work:

- task identifier;
- objective;
- starting repository state or base commit;
- governing specifications and Accepted ADRs;
- approved decisions;
- assumptions and uncertainties;
- scope in;
- scope out;
- expected deliverables;
- acceptance criteria;
- required verification;
- permitted actions;
- stopping and escalation conditions.

The handoff is sufficient for the Builder to interpret the task without access to the Architect's private conversation or conversational state. Conversation may provide input context, but it is not the execution contract.

When the same participant performs multiple authorized functions, logical collaboration contracts MAY be combined or represented within the execution context instead of requiring separate persistent artifacts, provided that scope, authority, acceptance criteria, verification and escalation boundaries remain explicit and verifiable.

### Builder Result and Verification Evidence

The Builder returns a structured result identifying:

- implementation status;
- changed files;
- the complete diff or its recoverable location;
- tests and validation performed;
- failures and limitations;
- deviations;
- unresolved questions;
- repository state;
- confirmation that the Authorization Envelope was respected.

The result makes incomplete verification, partial implementation and unexpected repository state explicit rather than treating tool completion as successful delivery.

### Review Result

The Reviewer function returns one explicit technical result:

- Accepted for the next authorized gate; or
- Changes requested.

Every review finding is specific and verifiable.

Acceptance for the next authorized gate means that the reviewed result satisfies the technical review contract. It does not mean human acceptance, ADR acceptance, publication approval or release approval when one of those decisions is required.

### Traceability and Persistence

A structured Authorization Envelope, Implementation Handoff, Builder Result, Review Result or item of execution evidence SHALL NOT by itself require permanent storage.

Persistence SHALL be proportional to the applicable governance, the significance of the work and the value of the artifact as reusable knowledge.

Significant decisions and evidence required by their governing specifications SHALL remain traceable according to those specifications.

Routine execution messages, intermediate contracts and verification details MAY remain transient when their preservation is not required for acceptance, traceability, audit or reusable knowledge.

### Bounded Correction Loop

Builder and Reviewer functions may repeat implementation, verification, review and correction automatically while:

- the work remains within the Authorization Envelope;
- no decision reserved to human authority is required;
- the approved architecture does not change;
- the authorized attempt, time and cost limits are not exceeded;
- no stopping or escalation condition occurs.

The maximum number of correction cycles is stated in the Authorization Envelope or in explicitly authorized operational configuration.

The loop stops and escalates when a bound is reached, an architectural conflict appears, required authority is unavailable, the base state becomes invalid or a requested correction would exceed approved scope.

### Proportional Role Topology

WEM does not require two AI participants or any fixed number of automated participants.

A participant may perform multiple roles when the assignment is explicit and proportional governance permits it. For significant changes, the Builder should not be the only Reviewer.

Combining roles does not combine or transfer their authorities. ASI-4 and ASI-5 decisions continue to require the human intervention defined by WEM.

### Replaceable Adapters

Participants and automation mechanisms integrate through replaceable adapters.

An adapter may describe:

- invocation method;
- input and output format;
- available capabilities;
- permission model;
- timeout and failure behavior;
- provider-specific restrictions.

Adapters remain operational interfaces. They do not redefine WEM roles, authority, ASI, ADR governance or collaboration governance.

The existing `AGENTS.md` and `CLAUDE.md` adapters and the decision recorded in `decisions/WEM-ADR-003.md` remain valid for the current operational configuration. This decision does not require Codex and Claude Code to share native memory, conversation or automatically synchronized intent.

### Separation from Executable Products

This decision and `specifications/AGENT_COLLABORATION.md` define governance and logical collaboration contracts only.

Sprint 0.10 does not create scripts, command-line tools, services, pipelines, physical templates, queue directories, temporary handoff files or orchestration implementations.

Any future executable orchestrator is a separate product that adopts WEM and is maintained under its own product responsibility, repository architecture, licensing and decision governance.

### Scope Boundary

This decision does not expand WEM into a general business methodology.

A business need or idea may be an input to an engineering project. Market validation, finance and general business governance remain outside the scope of WEM 1.0.0.

---

## Consequences

### Positive

- collaboration can progress between authorized roles without requiring a human to relay every message;
- human accountability remains explicit at authorization and reserved decision boundaries;
- handoffs and results become verifiable without private conversational context;
- agents, providers, models and invocation technologies remain replaceable;
- bounded correction loops can resolve routine findings without repeated human intervention;
- automation and manual collaboration can apply the same governance proportionally;
- future orchestrators can implement stable logical contracts without becoming normative WEM sources;
- the separation between WEM knowledge and executable products remains intact.

### Negative

- authorization, handoff, result and review contracts add structure to automated work;
- operators must define execution bounds and escalation behavior before automation begins;
- provider adapters may require maintenance as capabilities and permission models change;
- combined-role execution may provide less review independence when staffing is limited;
- a separate product repository will be required if executable orchestration is implemented.

### Risks and Limitations

- an Authorization Envelope may be too broad to preserve meaningful control or too narrow to permit useful automation;
- structured fields can create false confidence if their content is incomplete or inaccurate;
- an orchestrator may accidentally treat technical review acceptance as human acceptance;
- stale base commits or concurrent repository changes may invalidate a handoff during execution;
- correction loops may consume disproportionate time or cost if their bounds are poorly selected;
- provider-specific adapters may drift into alternative governance sources;
- the logical contracts will require validation through real executions before their practical sufficiency is known;
- this governance does not itself provide an executable orchestration capability.

### New Responsibilities

- maintain the authoritative automation-ready collaboration requirements in `specifications/AGENT_COLLABORATION.md`;
- define and apply Authorization Envelopes for automated executions;
- produce structured handoffs, Builder results, verification evidence and review results;
- configure and enforce correction-loop bounds and escalation conditions;
- keep provider adapters subordinate to canonical collaboration governance;
- maintain executable orchestration, if activated later, as a separate product responsibility.

---

## Alternatives Considered

### Alternative A — Human-mediated collaboration

The human Project Owner would manually transfer every instruction, handoff, result and review finding between participants.

This alternative makes human oversight continuously visible and requires no orchestration contract. It does not scale well, makes the human a transport dependency and does not distinguish accountability from message mediation.

It was not selected because WEM can preserve human authority through explicit bounded authorization and reserved gates without requiring manual transport for every interaction.

### Alternative B — Provider-specific direct coordination

WEM would depend on native communication or proprietary integrations supplied by Codex, Claude Code or another named provider.

This alternative may exploit convenient provider capabilities. It would couple WEM governance to changing tools, assume capabilities that are not portable and weaken the replaceability of operational participants.

It was not selected because it conflicts with technology independence and would make provider behavior part of the effective method.

### Alternative C — Single-agent execution model

One agent would perform architecture, implementation and review by default.

This alternative minimizes handoffs and operational complexity. It reduces independent review, concentrates assumptions and makes role boundaries less visible even when the same participant could perform them explicitly.

It was not selected as the default architecture. WEM may still assign multiple roles to one participant when that topology is explicit and proportional governance permits it.

### Alternative D — Provider-independent automation-ready contracts

Roles exchange structured Authorization Envelopes, Implementation Handoffs, Builder Results and Review Results through a replaceable orchestration mechanism. Human authority defines the permitted boundaries and receives escalations and reserved decisions.

This alternative preserves provider independence, makes execution verifiable without shared conversational context and permits bounded autonomous correction while separating governance from executable orchestration products.

It is the selected alternative.

---

## ASI Level

ASI-4 — Repository and architectural structure

Collaboration and orchestration architecture is classified within the canonical ASI-4 level because it changes durable structural relationships among roles, authorization boundaries, logical contracts and future orchestration implementations.

---

## Related Principles

- `WEM-P-001` — Responsibility Before Structure: collaboration contracts are introduced for an active automation-readiness responsibility without creating speculative executable artifacts;
- `WEM-P-002` — Separation of Knowledge and Products: WEM defines governance and logical contracts while future orchestration implementations remain separate products;
- `WEM-P-003` — Explicit and Traceable Decisions: significant decisions and evidence required by governing specifications remain traceable, while routine collaboration artifacts may remain transient under proportional governance;
- `WEM-P-004` — Proportional Governance: automation, contract detail, role separation and execution limits scale with scope and cost of change;
- `WEM-P-005` — Technology-Independent Method: roles and contracts remain independent from providers, models and invocation mechanisms;
- `WEM-P-006` — Canonical Source of Normative Knowledge: `specifications/AGENT_COLLABORATION.md` owns the resulting normative definitions while adapters and products reference it;
- `WEM-P-007` — Human Accountability: the Authorization Envelope preserves explicit human authority and reserved decisions without requiring human message mediation;
- `WEM-P-008` — Knowledge Preservation Through Evolution: reusable execution and review knowledge derived from structured contracts and results is preserved when its significance or future value justifies persistence.

---

## Related Specifications and Decisions

- `WEM.md`, for WEM scope, ASI, the Architectural Pause and the implemented Modular Specification correction;
- `PROJECT_CHARTER.md`, for project scope and the Project Owner's final authority;
- `ENGINEERING_PRINCIPLES.md`, for the authoritative Engineering Principles;
- `specifications/ADR_SPECIFICATION.md`, for ADR applicability, lifecycle and decision authority;
- `specifications/REPOSITORY_BLUEPRINT.md`, for repository responsibilities and the separation from executable products;
- `specifications/AGENT_COLLABORATION.md`, as the responsible canonical specification updated by this decision;
- `decisions/WEM-ADR-001.md`, for the Accepted repository architecture;
- `decisions/WEM-ADR-002.md`, which this decision extends and makes automation-ready without replacing its generic roles or human authority;
- `decisions/WEM-ADR-003.md`, which remains the Accepted decision for the current provider-specific adapters;
- `decisions/WEM-ADR-004.md`, for licensing boundaries relevant to WEM knowledge and future software products;
- `decisions/WEM-ADR-005.md`, for the non-normative public repository interface.

---

## Implementation Notes

Before this ADR was Accepted, no collaboration specification, foundation specification, adapter or executable artifact was authorized to change.

The Project Owner accepted this decision on 2026-08-07, closed the Architectural Pause and authorized implementation. `specifications/AGENT_COLLABORATION.md` is revised as the canonical source of the automation-ready collaboration governance and logical contracts recorded here. Existing role definitions and human authority are preserved, and `decisions/WEM-ADR-002.md` remains governing historical context rather than being superseded.

The `Modular Specification` section of `WEM.md` is corrected. Its speculative list entries `AI Agents`, `Standards` and `Coding Standards` are removed and replaced by a responsibility-based description of the current specification ecosystem, consistent with `WEM-P-001`, canonical-source governance and maintained navigation.

That correction does not authorize creation of those documents, new directories or other speculative artifacts.

The current provider assignments remain only in operational adapters and relevant historical ADRs. Existing adapters are aligned concisely with this Accepted decision without duplicating the canonical collaboration requirements.

Sprint 0.10 does not create scripts, command-line tools, services, pipelines, physical templates, queue directories, temporary handoff files or executable orchestration implementations.

---

## End of Record
