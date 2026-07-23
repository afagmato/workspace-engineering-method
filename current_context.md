# Current Context — Workspace Engineering Method

> Handover document for continuing the project with Codex in VS Code.
>
> Updated: 2026-07-23
>
> Language of collaboration: Catalan. Project specifications: English.

## How Codex should use this document

Before proposing or changing anything:

1. Read this document completely.
2. Read `WEM.md` if it exists.
3. Inspect the repository state with read-only Git commands.
4. Distinguish confirmed repository facts from decisions discussed in the previous conversation.
5. Ask Arç before making an ASI-4 or ASI-5 decision.

This file is a handover and current-state summary. It is not the normative WEM specification. If it conflicts with a released specification or accepted ADR, the specification or ADR takes precedence.

## Collaborator and working preferences

* The project owner is Arç.
* Conversation should normally be in Catalan.
* Documents that define WEM are written in English.
* Work should proceed slowly, explicitly and one Sprint 0 responsibility at a time.
* Do not generate a large repository structure in advance.
* Do not create empty folders, placeholder files or speculative abstractions.
* When a document is completed, provide:

  1. the reviewed document;
  2. a PowerShell 7 script or commands that create it in the correct location;
  3. the recommended Git commit message, including its ASI level.
* Before every commit, run or ask Arç to run `git status`.
* Arç wants to understand and approve important decisions, not merely receive generated files.

## Origin of the project

The conversation began with a practical time-control application built around Google Sheets and Apps Script. While discussing how to structure that application and make its components reusable, the scope widened: instead of building isolated solutions repeatedly, Arç decided to define a coherent engineering system that could guide multiple future projects.

The Sheets and Apps Script implementation details are intentionally omitted from this handover. Their only relevant legacy is that the time-control application is expected to become the first real project used to validate the engineering method.

## Strategic change

The central change in thinking was:

> The time-control application is no longer the whole project. It is the first project that will validate a reusable engineering method.

That method is called:

> **Workspace Engineering Method (WEM)**

WEM is intended to be technology-independent. It defines how engineering decisions are made, documented, reviewed and evolved. It must not depend on Google Workspace, Apps Script, a particular language, a framework or a specific AI model.

## Repository

* GitHub repository name: `workspace-engineering-method`

* Remote: `https://github.com/afagmato/workspace-engineering-method.git`

* Visibility: Public

* Description:

  > A technology-independent engineering method for designing, building and evolving sustainable software systems.

* Project short name: **WEM**

* Proposed motto: **Design. Build. Evolve.**

* The repository was created without a README, `.gitignore` or license.

### Repository status that must be verified

The last confirmed action in the conversation was the creation of the empty GitHub repository and the delivery of commands to:

1. clone it;

2. create `WEM.md`;

3. commit it with:

   ```text
   [ASI-5] Create WEM v1.0.0 foundation specification
   ```

4. push it to `origin main`.

Arç did not subsequently confirm in the conversation whether those local commands and the push were completed. Codex must therefore inspect the repository rather than assume either state.

Suggested read-only checks:

```powershell
git status
git remote -v
git log --oneline --decorate -5
git ls-tree --name-only HEAD
```

If there is no commit yet, `git log` and `git ls-tree` may fail; that is expected for an empty repository.

## Confirmed WEM design decisions

### 1. Nature of WEM

* WEM is an engineering method and modular specification.

* It governs thinking, architecture, implementation, evolution and knowledge preservation.

* It defines decision-making, not specific technologies.

* Projects adopt WEM; they do not import it as a technical dependency.

* A project may declare:

  ```text
  Methodology: WEM v1.0.0
  ```

* WEM should remain useful even if the technologies used by an adopting project disappear.

### 2. Separation between knowledge and products

The `workspace-engineering-method` repository is for knowledge:

* specifications;
* principles;
* standards;
* ADRs;
* templates;
* conceptual examples;
* documentation.

It should not contain functional applications or product implementations. Executable tools, libraries, frameworks and sample applications will belong in other repositories if and when they become real responsibilities.

This separation is important for both architecture and licensing.

### 3. Modular documentation

`WEM.md` defines the method at the highest level. Other responsibilities are intended to live in dedicated specifications, such as:

* Engineering Principles;
* Repository Blueprint;
* Project Charter;
* AI Agents;
* Standards;
* Architecture Decision Records;
* Coding Standards.

Documents should reference one another rather than duplicate knowledge.

These referenced documents do not yet necessarily exist. They must be created only when their responsibility becomes active in Sprint 0.

### 4. Repository growth rule

Two related formulations were discussed:

> A repository SHALL grow only when a responsibility becomes real.

> Nothing exists before it has a responsibility.

This became informally known as the **Zero Empty Rule**:

* no empty folders;
* no placeholder documents;
* no code without an architectural need;
* no architecture without a real responsibility.

The wording and formal identifier of this principle have not yet been finalized in the dedicated Engineering Principles specification.

### 5. Architectural Stability Index

Every engineering decision is intended to receive an Architectural Stability Index:

| Level | Meaning                                |
| ----- | -------------------------------------- |
| ASI-5 | Foundational decisions                 |
| ASI-4 | Repository and architectural structure |
| ASI-3 | Framework architecture                 |
| ASI-2 | Public interfaces                      |
| ASI-1 | Internal implementation                |

Higher levels require greater scrutiny. Changes affecting ASI-4 or ASI-5 trigger an **Architectural Pause**: implementation stops, alternatives and consequences are evaluated, and the need for an ADR is considered before work continues.

### 6. Architecture Decision Records

Significant decisions should be traceable through ADRs containing at least:

* Identifier;
* Title;
* Status;
* Context;
* Decision;
* Consequences;
* ASI level;
* Related principles.

No ADR structure has yet been created in the repository.

### 7. AI collaboration

AI agents are treated as engineering collaborators, while human decision-makers retain final responsibility.

The previous conversation explored role-based collaboration rather than model-based authority:

* Architect;
* Builder;
* Reviewer;
* Documentarian.

These roles are conceptual and have not yet been formalized. They should eventually be specified independently of ChatGPT, Codex, Claude or any other particular model.

## `WEM.md` status

A complete proposed `WEM.md` v1.0.0 was drafted in the previous conversation. Its front matter was:

```yaml
---
Document: WEM
Title: Workspace Engineering Method
Version: 1.0.0
Status: Draft
Type: Foundation
ASI: 5
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---
```

It included sections covering:

* Purpose;
* Scope;
* Normative Language;
* Vision;
* Core Philosophy;
* Engineering Lifecycle;
* Modular Specification;
* Engineering Principles;
* Architectural Stability Index;
* Architectural Pause;
* Architecture Decision Records;
* Documentation;
* Knowledge;
* Artificial Intelligence;
* Repository;
* Governance;
* Evolution.

The agreed intent was to keep `Status: Draft` during Sprint 0 because several referenced specifications did not yet exist, then perform a coherence review before changing it to `Released`.

Important: this handover intentionally does not reproduce the complete specification. If `WEM.md` exists in the repository, it is the working source. If it does not exist, Codex should ask Arç for the copied text or reconstruct it only through an explicit review; it should not silently invent a supposedly approved version.

## Licensing decision

The provisional decision for this methodology repository was:

> **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**

Reasoning:

* WEM is primarily a specification and knowledge repository, not a software library.
* Others should be able to study, apply, translate and improve it.
* Redistributed adaptations should remain under the same license.

GitHub did not offer CC BY-SA 4.0 in its repository-creation selector, so the repository was created with no license.

The license file has not been added. The discussion proposed documenting the licensing strategy in an ASI-4 ADR before adding `LICENSE`. This sequencing remains pending and may be reviewed; do not mistake the chosen license for an already implemented repository state.

Future software repositories may use a software license such as Apache 2.0, but no final decision is needed until such a repository exists.

## Agreed Sprint 0 working method

The intended flow for each responsibility is:

1. Define the document.
2. Review it with Arç.
3. Mark the content as stable enough for the Sprint.
4. Provide one PowerShell 7 creation script or a concise set of commands.
5. Arç executes it.
6. Verify with `git status`.
7. Commit with an ASI-prefixed message.
8. Push only after review.

The conversation also proposed retaining one bootstrap script per Sprint step, for example `bootstrap/sprint-0.1.ps1`, so the repository’s growth could be reconstructed. This idea was accepted in principle, but no bootstrap directory or script was created because the Zero Empty Rule and repository blueprint had not yet established their proper place. Treat the implementation details as pending.

## Current milestone

### Sprint 0.1 — WEM foundation

Goal:

* Create and publish only `WEM.md`.

Intended first repository state:

```text
workspace-engineering-method/
└── WEM.md
```

Do not add a README, license, `.gitignore`, folder structure or extra specification as part of this milestone unless Arç explicitly reopens the scope.

### Immediate next action

1. Open the cloned repository in VS Code.
2. Let Codex read this handover.
3. Inspect the actual Git state.
4. If `WEM.md` is uncommitted, review its contents and finish Sprint 0.1.
5. If the commit is already on `main`, report that Sprint 0.1 is complete and ask Arç which responsibility begins next.

Do not assume that `REPOSITORY_BLUEPRINT`, `PROJECT_CHARTER`, `AGENTS.md`, `CURRENT_CONTEXT.md`, `README` or `LICENSE` should be committed next. Their order belongs to Sprint 0 planning and must be agreed explicitly.

## Open decisions and pending work

* Confirm whether the first `WEM.md` commit was pushed.
* Decide the formal Sprint 0 sequence after Sprint 0.1.
* Define Engineering Principles and formalize the Zero Empty Rule.
* Define the Repository Blueprint before creating a larger directory structure.
* Decide when and how to introduce `AGENTS.md`.
* Decide whether this handover remains a local transition file or becomes a tracked project document.
* Create and accept the licensing ADR before or together with `LICENSE`, if that sequencing is retained.
* Decide when `README.md` becomes a real responsibility.
* Define the status transition criteria from WEM 1.0.0 Draft to Released.
* Later, define how the first time-control project will declare and validate WEM adoption.

## Recommended opening prompt in VS Code

Use this after opening the repository:

```text
Read CURRENT_CONTEXT.md completely and then read WEM.md if it exists.
Inspect the Git repository using read-only commands and tell me the exact current
state of Sprint 0.1. Do not create or modify files yet. Distinguish confirmed
repository facts from decisions described in the handover, and speak to me in
Catalan.
```

## Continuity principle

The conversation is not the source of truth. The repository should progressively become the source of truth.

Until the relevant specifications and ADRs exist, this handover preserves:

* the origin of the project;
* the decisions already discussed;
* the uncertainty about what was actually committed;
* the intended working method;
* the next safe action.

Future sessions should update a concise current-state document only when doing so has a clear responsibility and does not duplicate normative project knowledge.
