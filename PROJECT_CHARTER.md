---
Document: Project Charter
Title: Workspace Engineering Method Project Charter
Version: 1.0.0
Status: Released
Type: Foundation
ASI: 5
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method Project Charter

## Purpose

This charter defines why the Workspace Engineering Method (WEM) exists, the problem it addresses, its objectives, boundaries, intended adopters, ownership, foundational constraints and success criteria.

It also defines the relationship between WEM and the projects that adopt it.

This charter governs the WEM project itself. It does not replace the individual charter of an adopting project.

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Problem Statement

Software projects repeatedly make decisions about architecture, repository organization, documentation, quality, evolution and collaboration.

When those decisions are implicit, isolated or tied to a particular technology, projects lose knowledge, repeat mistakes and become increasingly difficult to change.

Premature structure also creates responsibilities that do not yet exist, while insufficient structure allows significant decisions to remain undocumented or uncoordinated.

AI-assisted engineering adds implementation capacity, but it also increases the need for explicit authority, bounded responsibilities and verifiable handoffs.

WEM exists to provide a coherent and reusable engineering method for addressing these problems.

---

## Mission

WEM provides a technology-independent method for designing, building and evolving sustainable software systems.

It establishes how engineering responsibilities are identified, how significant decisions are evaluated, how architectural knowledge is preserved and how human and AI collaborators work within explicit authority boundaries.

WEM governs engineering decisions without prescribing the technologies used to implement them.

---

## Objectives

WEM has the following objectives:

- establish a coherent engineering lifecycle from thinking to knowledge;
- make significant engineering decisions explicit and traceable;
- apply scrutiny in proportion to the expected scope and cost of change;
- preserve knowledge independently from specific implementations whenever possible;
- prevent repository structure and documentation from growing without a real responsibility;
- support collaboration between human and AI participants while preserving human authority;
- allow different projects to adopt a shared method without introducing a technical dependency;
- evolve the method without unnecessarily discarding established engineering knowledge.

---

## Expected Outcomes

WEM is expected to produce:

- modular and internally coherent engineering specifications;
- repositories whose structure reflects active responsibilities;
- traceable architectural and governance decisions;
- proportional use of the Architectural Stability Index and Architectural Pauses;
- explicit separation between reusable engineering knowledge and product implementation;
- adoption declarations that identify the WEM version used by a project;
- reusable lessons derived from real project experience;
- clearer collaboration between project owners, architects, reviewers, builders and other engineering participants.

---

## Scope

### In Scope

The WEM project includes:

- engineering principles;
- engineering governance;
- architectural decision-making;
- repository organization;
- project definition and boundaries;
- documentation and knowledge preservation;
- software quality responsibilities;
- human and AI collaboration;
- standards and coding guidance;
- templates and conceptual examples that support adoption;
- versioning, release and evolution of the WEM specifications;
- validation of WEM through real adopting projects.

### Out of Scope

The WEM project does not include:

- functional applications or product implementations;
- project-specific business logic;
- mandatory programming languages, frameworks, platforms or vendors;
- reusable runtime libraries or technical frameworks;
- ownership of the architecture or implementation of adopting projects;
- guarantees of project quality based solely on declaring WEM adoption;
- product-specific priorities, schedules or commercial decisions;
- certification or compliance services unless such a responsibility is explicitly established in the future.

---

## Intended Adopters

WEM may be adopted by:

- individual software engineers;
- engineering teams;
- organizations maintaining one or more software systems;
- projects that require explicit architectural governance;
- projects expected to evolve over an extended period;
- projects involving collaboration between humans and AI agents;
- projects seeking to preserve reusable engineering knowledge.

Adoption is not restricted by project size, programming language, platform, deployment model or development methodology.

WEM SHOULD remain applicable when the technologies or AI providers used by an adopting project change or disappear.

---

## Ownership and Authority

The Project Owner is the final decision authority for WEM.

The Project Owner SHALL approve:

- the objectives and scope of WEM;
- foundational and structural decisions classified as ASI-4 or ASI-5;
- changes to the responsibilities governed by this charter;
- milestone acceptance;
- specification releases;
- publication and licensing decisions.

Contributors and AI collaborators MAY analyze, propose, implement, review and document changes within their authorized responsibilities.

No contributor or AI collaborator may approve its own foundational proposal on behalf of the Project Owner.

Normative WEM specifications SHALL identify authorities by role rather than by the personal name of the current role holder.

Individual role assignments MAY be recorded in project-specific operational context.

Any transfer of project ownership or final decision authority SHALL be explicit and traceable.

---

## Success Criteria

WEM is successful when:

- its foundational specifications are coherent and their normative references resolve to defined responsibilities;
- an adopting project can understand and apply the method without relying on undocumented conversation history;
- an adopting project can identify the WEM version and status it follows;
- significant decisions are traceable without requiring routine local choices to carry unnecessary governance overhead;
- repository growth follows active responsibilities rather than speculative structure;
- reusable knowledge remains separable from product-specific implementation;
- human authority and collaborator responsibilities remain explicit;
- at least one real project validates the method and produces actionable feedback;
- changes in implementation technology do not invalidate the method;
- unresolved foundational decisions are visible rather than silently assumed.

Success SHALL NOT be measured by the number of documents, directories, tools or rules created.

These are long-term success criteria for the WEM project. They are not all prerequisites for releasing WEM 1.0.0 unless explicitly identified as release criteria.

---

## Foundational Constraints

The WEM project SHALL comply with the foundational requirements defined in `WEM.md` and with the applicable principles defined in `ENGINEERING_PRINCIPLES.md`.

The following project-specific constraints apply:

- repository growth and artifact creation SHALL be governed by `WEM-P-001`;
- repository boundaries between engineering knowledge and functional product implementation SHALL be governed by `WEM-P-002`;
- the Project Owner SHALL retain the authority defined in the Ownership and Authority section;
- WEM validation through real adopting projects SHALL remain consistent with `WEM-P-005` and `WEM-P-008`.

---

## Relationship to Adopting Projects

Projects adopt WEM as an engineering method, not as a technical dependency.

An adopting project SHALL identify the WEM version and status it follows.

An adopting project SHALL follow the applicable normative specifications.

Any deviation SHALL follow the deviation governance defined in `ENGINEERING_PRINCIPLES.md`. Declaring a deviation does not by itself establish full conformity with WEM.

Each adopting project retains responsibility for its own:

- objectives and scope;
- architecture;
- implementation;
- technology choices;
- operations;
- risks;
- releases;
- outcomes.

WEM does not own or control adopting projects.

Adopting projects MAY contribute lessons, proposals and reusable knowledge back to WEM. Such contributions do not modify WEM until they pass through the applicable WEM governance and approval process.

No individual adopting project, technology or provider SHALL define WEM solely around its own needs.

Formal definitions of adoption, alignment and full conformity are outside the scope of this charter and MAY be established when that responsibility becomes active.

---

## Validation and Evolution

Validation SHALL evaluate whether WEM improves decision clarity, architectural consistency, knowledge preservation and sustainable evolution without creating disproportionate process overhead.

Feedback from adopting projects MAY result in changes to WEM. Foundational or structural changes SHALL follow the applicable ASI, Architectural Pause and ADR requirements.

A version number alone does not make a WEM specification released.

Release requires explicit approval by the Project Owner after the required cross-document coherence review.

---

## End of Specification
