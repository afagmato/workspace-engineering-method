---
Document: Architecture Decision Record
Identifier: WEM-ADR-005
Title: Establish the WEM public repository interface
Status: Accepted
Created Date: 2026-08-06
ASI Level: 2
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-005 — Establish the WEM public repository interface

## Identifier

`WEM-ADR-005`

---

## Title

Establish the WEM public repository interface

---

## Status

Accepted

---

## Created Date

2026-08-06

---

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-08-06 | Proposed | Project Owner | ASI-2 WEM public repository interface proposal opened for evaluation. |
| 2026-08-06 | Accepted | Project Owner | WEM public repository interface approved and implementation authorized. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

The WEM repository contains the maintained specifications, Engineering Principles, Architecture Decision Records, provider-specific collaboration adapters and documentation that define, govern and explain the Workspace Engineering Method.

When this proposal was opened, the repository did not have a primary public human-facing entry point. External readers had to infer the repository's identity, current status, document responsibilities, adoption entry information and licensing from the individual maintained artifacts.

`specifications/REPOSITORY_BLUEPRINT.md` permits an active public entry point at the repository root as a repository-interface artifact. The public-interface responsibility is now active and requires a concise artifact that helps people orient themselves without becoming an alternative source of WEM governance.

The interface must:

- identify Workspace Engineering Method and its current version and Draft status;
- provide a concise, technology-independent orientation to WEM;
- distinguish maintained engineering knowledge from functional product implementations;
- make canonical specifications and Architecture Decision Records discoverable;
- link to the WEM overview presentation;
- provide accurate evaluation and adoption entry information while WEM remains Draft;
- make repository licensing and requested attribution discoverable;
- remain non-normative and subordinate to canonical specifications and Accepted ADRs;
- avoid reproducing normative definitions, provider instructions, transient context or future governance responsibilities.

This decision is ASI-2 because `README.md` will be the primary public repository interface consumed by external readers and will affect how they discover and interpret WEM. Its conventional root placement is already permitted by the Accepted repository architecture, and the decision does not modify that architecture or another ASI-4 or ASI-5 responsibility. An ADR is required for ASI-2 under `specifications/ADR_SPECIFICATION.md`; an Architectural Pause is not required.

---

## Decision

The decision is to establish `README.md` as the primary public human-facing entry point of the WEM repository.

`README.md` is a non-normative repository-interface artifact located at the repository root. It remains subordinate to canonical WEM specifications and Accepted ADRs and does not become an independent source of WEM governance.

The README is responsible for:

- identifying Workspace Engineering Method (WEM) and presenting the motto `Design. Build. Evolve.`;
- providing a concise, non-normative explanation of WEM;
- identifying the current version and status as `WEM 1.0.0 — Draft` and clearly stating that WEM is not yet Released;
- explaining at a high level that WEM is technology-independent;
- distinguishing WEM engineering knowledge from executable products;
- navigating readers to canonical specifications and the `decisions/` collection;
- linking to `documentation/wem-presentacio.pdf` as the WEM overview presentation;
- explaining how an evaluating project identifies the WEM version and status it follows without claiming stable release adoption;
- linking to the root `LICENSE` and identifying CC BY-SA 4.0;
- identifying the requested attribution as `Workspace Engineering Method (WEM), by Arç Fontrodona`;
- stating that canonical WEM specifications and Accepted ADRs govern if a README summary conflicts with them.

The README references canonical sources rather than reproducing their normative definitions. It does not redefine ASI, Architectural Pauses, the ADR lifecycle, Engineering Principles, repository architecture, collaboration roles or human and AI authority.

The README does not introduce normative requirements, Sprint planning, transient project context, provider implementation instructions, contribution governance, a product roadmap, certification claims, compliance guarantees or duplicated license text.

This Accepted decision authorizes creation and maintenance of `README.md` within the public-interface responsibility and content boundaries recorded here.

---

## Consequences

### Positive

- external readers gain a clear and conventional starting point for understanding WEM;
- WEM identity, Draft status, navigation, evaluation guidance and licensing become easier to discover;
- canonical specifications and ADRs remain the authoritative sources behind concise public summaries;
- the distinction between engineering knowledge and functional products becomes visible at repository entry;
- the presentation and license become discoverable without duplicating their content.

### Negative

- the README becomes another maintained artifact that must remain coherent with version, status, paths and licensing decisions;
- concise explanations may omit nuance available only in the canonical specifications;
- changes to canonical paths or public status require corresponding interface maintenance.

### Risks and Limitations

- readers may mistake a concise summary for normative WEM governance despite an explicit authority statement;
- duplicated wording could drift from canonical definitions if the README expands beyond orientation and navigation;
- the public interface may become stale when WEM changes version, status, document structure or licensing information;
- presenting evaluation guidance while WEM is Draft may be misunderstood as stable release adoption;
- a repository README alone does not establish certification, conformity or project quality.

### New Responsibilities

- maintain `README.md` as the primary public human-facing repository entry point;
- keep its links, version, status, attribution and licensing discovery accurate;
- review its summaries for accidental normative duplication when canonical WEM knowledge changes;
- preserve its non-normative repository-interface boundary.

---

## ASI Level

ASI-2 — Public interfaces

---

## Related Principles

- `WEM-P-001` — Responsibility Before Structure: `README.md` is introduced only after its public-interface responsibility becomes active;
- `WEM-P-002` — Separation of Knowledge and Products: the interface distinguishes maintained WEM knowledge from functional product implementation;
- `WEM-P-003` — Explicit and Traceable Decisions: this ADR preserves the public-interface decision, its scope and its authority;
- `WEM-P-004` — Proportional Governance: ASI-2 ADR governance records the durable public interface without requiring an Architectural Pause;
- `WEM-P-005` — Technology-Independent Method: the public orientation presents WEM independently from particular technologies and providers;
- `WEM-P-006` — Canonical Source of Normative Knowledge: the README remains non-normative and resolves readers to authoritative specifications and Accepted ADRs;
- `WEM-P-007` — Human Accountability: the Project Owner retains authority to accept the ADR and authorize implementation and publication;
- `WEM-P-008` — Knowledge Preservation Through Evolution: stable navigation and explicit status help maintained WEM knowledge remain discoverable as it evolves.

---

## Related Specifications and Decisions

- `WEM.md`, for the canonical method definition, status and engineering lifecycle;
- `PROJECT_CHARTER.md`, for mission, scope, authority and the relationship to adopting projects;
- `ENGINEERING_PRINCIPLES.md`, for the authoritative Engineering Principles;
- `specifications/ADR_SPECIFICATION.md`, for ADR applicability, lifecycle and decision authority;
- `specifications/REPOSITORY_BLUEPRINT.md`, for repository-interface responsibility and root-level placement;
- `specifications/AGENT_COLLABORATION.md`, for canonical human and AI collaboration governance referenced at a high level;
- `decisions/WEM-ADR-001.md`, for the Accepted repository architecture;
- `decisions/WEM-ADR-002.md`, for the Accepted collaboration governance decision;
- `decisions/WEM-ADR-003.md`, for the Accepted provider-specific adapter decision and distinction between provider interfaces and canonical governance;
- `decisions/WEM-ADR-004.md`, for repository licensing scope, CC BY-SA 4.0 and requested attribution.

---

## Implementation Notes

The Project Owner accepted this decision on 2026-08-06 and authorized implementation of the WEM public repository interface.

Implementation creates only the root `README.md` and preserves the Proposed and Accepted transitions in this record's Status History.

No contribution policy, code of conduct, changelog, roadmap, badge, directory, image, template or script is part of this decision.

---

## End of Record
