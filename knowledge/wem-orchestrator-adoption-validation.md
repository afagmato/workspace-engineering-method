# WEM Orchestrator Adoption Validation

Status: Validation in progress

Observed project: WEM Orchestrator

Observation date: 2026-11-03

Active project reference: WEM 1.2.0 — Released

> Non-normative reusable knowledge. This record reports observed adoption evidence and limitations; it does not redefine WEM or certify the adopting project.

## Purpose

This record consolidates evidence and lessons from WEM Orchestrator, the first executable product project to adopt WEM. It distinguishes demonstrated outcomes from pending validation so that WEM can evolve from real use without overstating the evidence.

## Project characteristics

WEM Orchestrator is maintained in an independent product repository. It declares an executable-software responsibility, human Project Owner authority and provider-independent architecture. Its implementation is separate from the WEM knowledge repository.

The project began under WEM 1.0.0 and adopted WEM 1.2.0 on 2026-10-28. Historical decisions retain their original WEM references.

## Evidence observed

- a Released Project Charter identifies the product, authority, scope and WEM version;
- eleven Accepted project ADRs preserve foundation, repository, architecture, contract, security, implementation, adoption and real-Builder validation decisions;
- four Released project specifications define orchestration, workflow contracts, security and implementation architecture;
- five provider-neutral JSON contract schemas exist;
- executable code validates contracts and implements deterministic state and limit policy;
- architecture, unit, integration, fixture and scenario tests exist;
- the current locked local verification profile passes formatting, linting, strict typing, 72 tests with one separately gated live test skipped, package build and installed-wheel smoke verification;
- bounded process control, local Authority Record ingestion, read-only Git observation and one real Builder adapter are implemented behind provider-neutral boundaries;
- experience from the project exposed excessive approval and artifact overhead in WEM 1.0.0;
- that feedback is recorded in WEM-ADR-009 and influenced proportional Milestone delivery in WEM 1.1.0;
- WEM Orchestrator subsequently adopted WEM 1.2.0 through WEMO-ADR-010.

## Demonstrated WEM outcomes

The project demonstrates that WEM can:

- establish an independent executable-product responsibility without mixing product code into the WEM repository;
- preserve human final authority while assigning operational functions to AI collaborators;
- support provider-independent architecture and replaceable adapter boundaries;
- produce durable architectural traceability;
- evolve from project feedback and preserve historical decision references;
- identify disproportionate governance and correct the method without reopening valid earlier work.

## Friction and lessons

Application of WEM 1.0.0 produced repeated approval boundaries, overly broad ADR use, zero-correction execution envelopes and repeated release-level verification for small increments. Some friction resulted from application choices; some resulted from the then-current ASI-2 ADR threshold.

The volume of maintained project decisions and specifications also demonstrates that a safe architecture can accumulate substantial adoption overhead before visible product capability. WEM should therefore provide concise non-normative onboarding, templates and examples while keeping normative sources canonical.

Review and acceptance evidence for significant milestones should be easier to recover. WEM permits routine intermediate evidence to remain transient, but public methodology releases and foundational adopting-project milestones benefit from a durable minimum review record.

## Validation limitations

This project does not yet establish broad or independent validation of WEM:

- it is owned by the same Project Owner and was designed specifically around WEM collaboration contracts;
- its accepted core-conformance MVP and current local verification remain closely aligned with WEM's own collaboration domain;
- a real Builder adapter exists, but the first live probe stopped on an external provider session limit before model or tool execution;
- no complete real Architect-to-Builder-to-Reviewer execution with an automatic correction loop has yet been demonstrated;
- human-decision and repository-action adapters remain scripted, fake or disabled;
- durable Run persistence remains deferred;
- the project began before WEM 1.2.0, so it cannot validate the complete Project Initiation workflow from a clean start;
- the repository alone does not provide a durable final-acceptance and independent-review record for the completed core-conformance MVP.

## Active validation milestone

WEMO-ADR-011 accepted and authorized the First Real Builder Validation Milestone. Its implementation has:

1. recorded Project Owner acceptance of the provider-free MVP with its known limitations;
2. implemented local observation, Authority Record and bounded process-control prerequisites;
3. added one replaceable Claude Code Builder adapter outside the provider-independent core;
4. added a separately gated disposable-repository test for one bounded correction cycle;
5. preserved normalized evidence without private conversation or provider-session identifiers;
6. stopped the initial live probe when provider capability was unavailable.

Completion still requires a successful live correction-cycle run, independent technical review or an explicit Project Owner exception with compensating review, a canonical Review Result and explicit final Project Owner acceptance. Detailed evidence is maintained by WEM Orchestrator in `knowledge/first-real-builder-validation-evidence.md`.

## Broader validation required

A second, unrelated small project should adopt WEM 1.2.0 from a clean start. It should test Project Initiation, manual usability and proportional governance without assuming an orchestration-product domain. WEM should not treat one closely related dogfooding project as general validation across project types.

## Traceability

- WEM Project Charter success criteria;
- WEM-ADR-009 — proportional Milestone delivery;
- WEM-ADR-010 — automated Project Initiation;
- WEM Orchestrator WEMO-ADR-009 — provider-free core-conformance MVP;
- WEM Orchestrator WEMO-ADR-010 — adoption of WEM 1.2.0.
- WEM Orchestrator WEMO-ADR-011 — first real Builder validation milestone.
