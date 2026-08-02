---
Document: Repository Blueprint
Title: Workspace Engineering Method Repository Blueprint
Version: 1.0.0
Status: Draft
Type: Architecture
ASI: 4
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method Repository Blueprint

## Purpose

This specification defines the normative repository architecture for the Workspace Engineering Method.

It establishes the artifact responsibilities the repository may contain, their canonical locations, naming rules, directory activation rules, movement and retirement requirements, prohibited content and the requirements for adoption by other projects.

The architectural rationale for this specification is recorded in `WEM-ADR-001`.

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Status and Authority

This document remains Draft throughout Sprint 0 and until the required cross-document coherence review is complete.

While `WEM-ADR-001` remains Proposed, the repository architecture defined here is not governing and SHALL NOT be physically applied.

If `WEM-ADR-001` becomes Accepted, this architecture becomes authorized for controlled application while this specification remains Draft.

Publication of this Draft does not by itself authorize directory creation, file movement or artifact retirement.

---

## Scope

This specification governs:

- content permitted in the WEM repository;
- artifact responsibility classes;
- canonical artifact locations;
- root-level admission;
- directory and file naming;
- directory creation;
- artifact movement and retirement;
- prohibited repository content;
- repository-architecture adaptation by projects adopting WEM.

This specification does not define:

- the normative content of other WEM specifications;
- ADR lifecycle or approval semantics;
- coding rules;
- contribution workflow;
- licensing terms;
- product repository architecture;
- a required physical tree for every project adopting WEM.

Those concerns remain governed by their responsible specifications or future approved responsibilities.

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

## Repository Responsibility

The WEM repository is a knowledge repository for the definition, governance, explanation and evolution of the Workspace Engineering Method.

Every maintained artifact SHALL serve one explicit repository responsibility.

Every artifact SHALL have one canonical location determined by its responsibility.

Artifact classification SHALL be based on responsibility rather than perceived importance, author, tool or temporary workflow state.

---

## Artifact Classes

### Foundation Specifications

Foundation specifications define the identity, mission, authority or permanent principles of WEM.

They are normative, repository-wide and classified as `Type: Foundation`.

The current foundation specifications are:

- `WEM.md`;
- `PROJECT_CHARTER.md`;
- `ENGINEERING_PRINCIPLES.md`.

### Normative Specifications

Normative specifications define a distinct WEM system, governance responsibility or architectural responsibility that is not classified as Foundation.

Each normative requirement SHALL have one authoritative definition in a canonical specification.

A responsibility MAY span multiple coordinated specifications when their boundaries and authoritative requirements are explicit.

Examples include ADR governance and repository architecture.

### Architecture Decision Records

Architecture Decision Records preserve the context, decision, consequences, ASI classification and authority of significant decisions.

ADRs SHALL comply with `specifications/ADR_SPECIFICATION.md`.

An ADR is the authoritative historical record of why a decision was made. It SHALL NOT replace the normative specification responsible for the resulting rules.

### Standards

Standards define specialized, uniform and verifiable rules within an approved scope.

A standard is normative but does not replace the specification that defines the system or responsibility to which the standard applies.

### Knowledge

Knowledge artifacts preserve reusable lessons, research, analysis and patterns derived from engineering experience.

Knowledge artifacts are non-normative and SHALL NOT establish or redefine WEM requirements.

### Documentation

Documentation helps people understand, navigate, adopt or maintain WEM.

Documentation is non-normative. It MAY explain normative content but SHALL reference the canonical specification and SHALL NOT redefine it.

Knowledge preserves what has been learned. Documentation explains how to understand or use the maintained system.

### Templates

Templates provide reusable starting structures that apply a WEM specification or standard.

A template SHALL identify the canonical specification or standard it implements.

A template SHALL NOT add undisclosed normative requirements or replace its canonical source.

### Conceptual Examples

Conceptual examples illustrate the application of WEM without becoming functional products or normative templates.

Examples SHALL be clearly identifiable as illustrative and SHALL NOT become the canonical source of a requirement.

### Repository Interface and Control

Repository interface and control artifacts provide public entry points, legal terms, contribution controls, repository configuration or tool-required instructions.

They MAY remain at the repository root when an active responsibility or external convention requires that location.

Their existence SHALL NOT be inferred merely because similar repositories commonly contain them.

### Local and Transitional Context

Local session context, private coordination files, scratch material and transient experiments are not maintained WEM knowledge.

They SHALL NOT be committed unless a separate approved responsibility makes them canonical repository artifacts.

---

## Repository Architecture

WEM uses a hybrid, responsibility-based repository architecture.

Foundation specifications SHALL remain at the repository root.

Specialized responsibilities SHALL use the following canonical locations:

| Responsibility | Canonical location |
| --- | --- |
| Foundation specifications | Repository root |
| Other normative specifications | `specifications/` |
| Architecture Decision Records | `decisions/` |
| Standards | `standards/` |
| Reusable knowledge | `knowledge/` |
| Explanatory documentation | `documentation/` |
| Templates | `templates/` |
| Conceptual examples | `examples/` |
| Repository interface, legal and tool-required artifacts | Repository root when required by their responsibility or convention |

A responsibility's canonical location SHALL NOT be created physically until that responsibility has at least one real artifact.

---

## Root-Level Admission

The repository root SHALL remain intentionally limited.

An artifact MAY remain at the root only when at least one of the following applies:

- its metadata classifies it as `Type: Foundation`;
- it is the repository's active public entry point;
- it provides active repository-wide legal or contribution control whose conventional or required location is the root;
- a platform or tool requires its exact root location;
- an Accepted ADR authorizes a temporary root location during a controlled migration.

Root placement SHALL NOT be justified only by convenience, age, perceived importance or the absence of an existing directory.

---

## Directory Activation

A directory SHALL be created only when it receives its first real artifact in the same repository operation.

Empty directories, placeholder files and speculative indexes SHALL NOT be used to reserve future structure.

Defining a canonical location in this specification does not activate or create that directory.

A directory SHALL remain only while it serves at least one maintained responsibility.

---

## Naming Rules

### Directories

Directory names SHALL:

- use lowercase characters;
- use complete responsibility-based terms;
- use hyphens only when multiple words are necessary;
- remain independent from specific tools, providers or temporary workflow states.

Ambiguous or transitional names such as `core`, `misc`, `temp` and `sandbox` SHALL NOT be used as canonical responsibility directories.

### Foundation Specifications, Normative Specifications and Standards

Foundation specifications, other normative specifications and standards SHALL use:

```text
UPPER_SNAKE_CASE.md
```

Their version and status SHALL be recorded in document metadata rather than encoded in the filename.

### Architecture Decision Records

WEM ADR filenames SHALL use their permanent identifier:

```text
WEM-ADR-NNN.md
```

The ADR title SHALL be stored within the document and SHALL NOT be required in the filename.

### Knowledge, Documentation, Templates and Examples

Knowledge, documentation, templates and conceptual examples SHOULD use descriptive lowercase kebab-case filenames:

```text
descriptive-artifact-name.md
```

### Conventional Files

Repository interface and control artifacts SHALL retain an exact conventional filename when their responsibility or integration depends on it.

---

## Artifact Creation

Before creating an artifact, its responsible author or role SHALL identify:

- the responsibility it serves;
- whether it is normative, historical, informative or operational;
- its canonical location;
- its naming convention;
- its authoritative source when it summarizes or implements other knowledge;
- the applicable ASI and approval requirements.

An artifact SHALL NOT be created solely to anticipate possible future content.

---

## Artifact Movement

An artifact SHALL be moved when its approved responsibility changes or when the repository architecture assigns it a different canonical location.

A move SHALL:

- preserve version-control traceability whenever possible;
- update affected references in the same controlled operation;
- avoid leaving duplicate canonical copies;
- disclose temporary incompatibilities or deferred migrations;
- follow the ASI and ADR governance appropriate to its structural impact.

A move SHALL NOT silently change the normative meaning of the artifact.

---

## Artifact Retirement

An artifact MAY be retired when its responsibility no longer exists, has moved to a different canonical source or has been explicitly superseded.

Before retirement:

- reusable or normative knowledge SHALL be preserved in its responsible canonical source;
- affected references SHALL be updated;
- the applicable lifecycle and decision records SHALL identify the retirement when required;
- historical traceability SHALL be preserved.

ADRs SHALL NOT be removed merely because their status is no longer Accepted.

An artifact SHALL NOT be retained as an empty placeholder after its responsibility ends.

---

## Prohibited Repository Content

The WEM repository SHALL NOT contain:

- functional applications;
- project-specific business logic;
- runtime libraries or executable frameworks;
- derived product tools whose responsibility belongs in a separate repository;
- secrets, credentials or private operational data;
- build outputs or generated dependencies;
- transient experiments or sandbox content;
- empty directories or placeholder artifacts;
- duplicated normative definitions;
- files without an explicit maintained responsibility.

Conceptual examples and templates remain permitted only when they satisfy their defined non-product responsibilities.

---

## Structural Application

The repository architecture approved in `decisions/WEM-ADR-001.md` was physically applied on 2026-08-02 through the separately authorized ASI-4 operation recorded by commit `d7b2409`.

The controlled operation:

- activated `specifications/` by moving `ADR_SPECIFICATION.md` and `REPOSITORY_BLUEPRINT.md` into their canonical location;
- activated `decisions/` by moving `WEM-ADR-001.md` into its canonical location;
- preserved `WEM.md`, `PROJECT_CHARTER.md` and `ENGINEERING_PRINCIPLES.md` at the repository root;
- aligned the tracked continuity filename to `CURRENT_CONTEXT.md` without changing its root location;
- updated references affected by the new canonical paths;
- created no other canonical responsibility directory.

The physical application does not change this specification's Draft status.

The temporary retention of `CURRENT_CONTEXT.md` at the repository root does not make it canonical normative knowledge.

This specification does not determine the long-term responsibility, location or retirement of `CURRENT_CONTEXT.md`.

Future structural changes SHALL follow the applicable ASI, Architectural Pause and ADR governance.

---

## Adoption by Other Projects

Projects adopting WEM SHALL define a repository architecture that maps every applicable maintained artifact to an explicit responsibility and canonical location.

An adopting project SHALL define:

- where its normative specifications are maintained;
- where and how its ADRs are discovered;
- where standards, knowledge, documentation and templates are maintained when those responsibilities exist;
- which artifacts may remain at its repository root;
- how directories become active;
- its naming, movement and retirement rules.

An adopting project MAY use different directory names or an existing repository structure when it provides equivalent responsibility separation, canonicality, discoverability and traceability.

An adopting project SHALL NOT create directories merely to imitate the WEM repository tree.

Product repositories MAY contain product implementations because their responsibility differs from the WEM knowledge repository. They SHALL still preserve the applicable separation between canonical engineering knowledge and implementation-specific artifacts.

Any incompatible deviation SHALL follow the deviation governance defined in `ENGINEERING_PRINCIPLES.md`.

---

## Evolution

Changes to canonical responsibility classes, root-admission rules, directory locations, naming systems or adoption requirements affect repository architecture and SHALL be classified as ASI-4 or higher according to their actual scope and cost of change.

Changes that modify a foundational WEM principle or responsibility SHALL follow the applicable ASI-5 governance.

Editorial corrections that do not change normative meaning SHALL follow proportional governance.

---

## End of Specification
