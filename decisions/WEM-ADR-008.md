---
Document: Architecture Decision Record
Identifier: WEM-ADR-008
Title: Release Workspace Engineering Method 1.0.0
Status: Accepted
Created Date: 2026-08-07
ASI Level: 5
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-008 — Release Workspace Engineering Method 1.0.0

## Identifier

`WEM-ADR-008`

---

## Title

Release Workspace Engineering Method 1.0.0

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
| 2026-08-07 | Proposed | Project Owner | ASI-5 Architectural Pause opened to evaluate release of WEM 1.0.0. |
| 2026-08-08 | Accepted | Project Owner | Coordinated WEM 1.0.0 release approved and release-candidate preparation authorized. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

Sprint 0.1 through Sprint 0.11 established the initial Workspace Engineering Method specification ecosystem and prepared it for a coordinated 1.0.0 release.

That work created and governed:

- the foundational WEM method and Project Charter;
- the permanent Engineering Principles;
- the Architecture Decision Record governance system;
- the responsibility-based repository architecture;
- provider-independent human and AI collaboration governance;
- provider-specific operational adapters for Codex and Claude Code;
- repository licensing under CC BY-SA 4.0;
- the non-normative public repository interface;
- automation-ready collaboration contracts;
- the final cross-document coherence review and its bounded remediation.

WEM-ADR-001 through WEM-ADR-007 are Accepted and their authorized decisions are implemented. They establish the repository architecture, collaboration governance, provider adapters, licensing, public interface, automation-ready collaboration architecture and canonical ADR governance boundary that compose the current WEM repository.

Sprint 0.11 completed the Cross-Document Coherence Review. Its remediation resolved:

- WEM-CR-001 by consolidating detailed ADR governance in `specifications/ADR_SPECIFICATION.md`;
- WEM-CR-002 by aligning the Repository Blueprint with the implemented retirement of `CURRENT_CONTEXT.md`;
- WEM-CR-003 by aligning the Codex adapter with the canonical Review Result semantics.

WEM-CR-004 remains the pending coordinated release operation. WEM-CR-005 remains the final visual verification of `documentation/wem-presentacio.pdf` during preparation of the release candidate.

Before this proposal was created, `main` and `origin/main` were synchronized at commit `c84c0b217caca61453cb7623ec2cdf4788671bde`, the working tree was clean and no `v1.0.0` tag existed.

The maintained specifications, Accepted ADRs, repository structure, public interface and licensing information have been reviewed from the repository. No known normative release blocker remains after the Sprint 0.11 remediation.

`ENGINEERING_PRINCIPLES.md` is already Version 1.0.0 with Status Released. Its prior ASI-5 release remains valid; the coordinated WEM release does not require that specification to be degraded to Draft, reopened or changed normatively.

The Project Charter defines long-term success criteria, including validation through real adopting projects. It explicitly states that those criteria are not all prerequisites for releasing WEM 1.0.0 unless separately identified as release criteria. Deferring release until a real adopting project completes validation is therefore an available policy choice, not a current normative prerequisite.

The Project Owner retains exclusive authority to approve and declare the release. Codex may prepare and review this proposal and a later release candidate, but cannot accept this ADR, close the Architectural Pause or declare the release on behalf of the Project Owner. After the separate explicit Project Owner repository-action authorization, Codex or another authorized collaborator MAY execute the release commit, annotated tag and push. Executing those actions SHALL NOT transfer release authority.

CC BY-SA 4.0 repository licensing was accepted through WEM-ADR-004 and is implemented by the unmodified root `LICENSE`. The current file matches the SHA-256 recorded by that decision.

WEM remains a technology-independent engineering methodology and maintained knowledge repository. Releasing WEM 1.0.0 does not create an executable product, orchestration implementation, certification scheme or guarantee of adopting-project quality.

This decision is ASI-5 because it establishes the first coordinated stable release of WEM's foundational and governance specifications and creates a permanent public version reference. The Project Owner accepted this ADR and closed the Architectural Pause on 2026-08-08.

---

## Decision

The decision is to perform a coordinated release of Workspace Engineering Method 1.0.0.

Acceptance of this ADR authorizes preparation of the bounded release candidate described below. It does not by itself authorize the release commit, tag, push or declaration of publication. Those repository actions require a separate explicit Project Owner gate after review of the complete implementation diff and verification evidence. An authorized collaborator MAY execute them only after that authorization, and their execution SHALL NOT transfer the Project Owner's release authority.

### Specification Status

Under this Accepted decision and the release-candidate preparation authorization, the following specifications transition from Draft to Released without changing their version:

- `WEM.md`;
- `PROJECT_CHARTER.md`;
- `specifications/ADR_SPECIFICATION.md`;
- `specifications/REPOSITORY_BLUEPRINT.md`;
- `specifications/AGENT_COLLABORATION.md`.

Each will remain Version 1.0.0.

`ENGINEERING_PRINCIPLES.md` will remain unchanged normatively with:

```text
Version: 1.0.0
Status: Released
```

### Internal Status Alignment

The release candidate will align current status statements with the Released specification lifecycle. It will:

- remove statements that a specification remains Draft throughout Sprint 0;
- replace obsolete Proposed or conditional authority statements with the current Accepted and Released state;
- preserve correct historical explanations;
- avoid indiscriminate replacement of every occurrence of `Draft`.

Historical references, examples and records will be evaluated according to their responsibility before any status wording changes.

### Public Repository Interface

`README.md` will be updated to:

- identify `WEM 1.0.0 — Released`;
- report Version 1.0.0 and Status Released in Current Status;
- remove the statement that the cross-document coherence review is pending;
- replace Draft evaluation-only guidance with adoption guidance for WEM 1.0.0 Released;
- retain its non-normative boundary;
- preserve licensing, requested attribution and valid navigation links.

The README will not add badges, a roadmap, release notes, a changelog or another responsibility.

### Presentation

`documentation/wem-presentacio.pdf` will be updated only as required to:

- change visible WEM 1.0.0 status from Draft to Released;
- change Draft to Released in applicable PDF metadata;
- preserve its existing content, style, pagination and structure except for those necessary status changes.

Every page will receive visual verification. The review will specifically check spacing, typography and titles that have previously required correction. The release candidate SHALL NOT replace the presentation with a lower-quality document or commit source files, temporary images or intermediate artifacts.

### Historical ADR Preservation

WEM-ADR-001 through WEM-ADR-008 will preserve the WEM Reference under which each decision was governed.

Historical references to `WEM 1.0.0 — Draft` will not be rewritten merely because WEM 1.0.0 becomes Released. Existing Status History entries will not be removed or overwritten. Accepted ADRs will remain Accepted unless a separately governed decision changes their lifecycle state.

### Git Release Publication

Only after:

- this ADR is Accepted by the Project Owner;
- the release candidate is implemented;
- the complete diff and verification evidence are reviewed;
- the PDF passes final visual verification;
- the Project Owner provides a separate explicit authorization for commit and publication;

the release operation will create exactly:

- commit message: `[ASI-5] Release WEM 1.0.0`;
- annotated tag: `v1.0.0`;
- tag message: `Workspace Engineering Method 1.0.0`;
- push of `main` and tag `v1.0.0`.

The release operation will not create a GitHub Release object, release notes, `CHANGELOG`, roadmap or other release artifact unless a separate future responsibility is explicitly authorized.

### Release Integrity

The release SHALL:

- correspond to one identifiable release commit;
- place annotated tag `v1.0.0` on that exact commit;
- leave `main` and `origin/main` synchronized;
- leave the working tree clean;
- preserve Git history;
- leave `LICENSE` unchanged;
- include no functional product implementation;
- create no speculative directory or artifact.

Once published, tag `v1.0.0` SHALL NOT be moved, deleted or reused.

Any correction to Released WEM content SHALL be governed as a new version rather than rewriting the published release tag.

### Failure and Escalation

Release-candidate preparation or publication SHALL stop and return to the Project Owner if it reveals:

- a new normative conflict;
- an unexpected broken link;
- a status contradiction;
- an unauthorized difference;
- inability to verify the PDF visually;
- degradation of the PDF;
- any licensing change;
- a need to expand the approved scope.

---

## Consequences

### Positive

- WEM will have a stable and referenceable 1.0.0 version;
- adopting projects will be able to declare explicit adoption of WEM 1.0.0 Released;
- foundational and governance specifications will expose one coordinated public status;
- the annotated Git tag will provide a stable and intentionally permanent release reference;
- the release will provide a stable basis for the first adopting projects;
- later real executions can validate and improve WEM collaboration and orchestration governance against a stable baseline.

### Negative

- future normative changes will require applicable governance and version evolution;
- any residual error will become part of the published release record;
- `README.md` and the presentation will remain public artifacts that must stay coherent with future WEM versions and status;
- release preparation requires coordinated status, documentation, Git and visual verification work.

### Risks and Limitations

- readers may mistake release for certification, compliance, project-quality assurance or completed real-project validation;
- broad status replacement could incorrectly rewrite historical Draft references;
- an incorrectly placed or lightweight tag could break the intended stable and intentionally permanent release reference;
- PDF modification could introduce spacing, typography, metadata or rendering regressions;
- specifications and non-normative public interfaces could drift during the status transition;
- a release commit could accidentally include unrelated files if staged scope is not verified exactly.

### New Responsibilities

- preserve the integrity and discoverability of the `v1.0.0` release reference;
- maintain public version and status declarations coherently as WEM evolves;
- govern future normative changes and version evolution proportionally;
- use feedback from adopting projects to validate WEM without rewriting the historical 1.0.0 release;
- keep executable products and future orchestration implementations outside the WEM knowledge repository.

---

## Alternatives Considered

### Alternative A — Remain Draft

WEM would remain at Version 1.0.0 with Draft status.

Advantages:

- more time would remain available for review and validation;
- no stable-release commitment would be created.

Disadvantages:

- a specification ecosystem that has completed coherence review and remediation would remain provisional;
- adopting projects would lack a stable WEM version reference.

This alternative was not selected because no known normative release blocker currently justifies indefinite Draft status.

### Alternative B — Partial specification release

Some specifications would transition to Released while others remained Draft.

Advantages:

- each specification could preserve an independent lifecycle;
- individual responsibilities could release when separately ready.

Disadvantages:

- the public WEM 1.0.0 status would remain fragmented;
- adopters could not determine whether WEM 1.0.0 represented a coordinated ecosystem;
- cross-specification adoption and governance would remain ambiguous.

This alternative was not selected because the reviewed specifications are intended to form one coordinated initial WEM release.

### Alternative C — Delay release until validation by a real adopting project

WEM would remain Draft until at least one real adopting project completed practical validation.

Advantages:

- the release would incorporate practical adoption evidence;
- initial ambiguities might be discovered before publication.

Disadvantages:

- `PROJECT_CHARTER.md` states that not all long-term success criteria are prerequisites for WEM 1.0.0;
- the delay would withhold the stable version reference needed for a project to declare Released adoption;
- practical validation can continue through later governed evolution without rewriting 1.0.0 history.

This alternative was not selected because real-project validation is a continuing WEM responsibility rather than a currently established release prerequisite.

### Alternative D — Coordinated WEM 1.0.0 release

All release-ready specifications will transition together, with the README and PDF aligned in the same release commit and annotated tag.

Advantages:

- WEM 1.0.0 will present one coherent public lifecycle state;
- adopters will receive stable specifications, navigation and documentation;
- one commit and tag will provide precise historical traceability.

Disadvantages:

- release integrity depends on coordinated editing and verification across normative and non-normative artifacts;
- the operation cannot complete until the Project Owner reviews the resulting evidence and authorizes publication.

This is the recommended alternative.

---

## ASI Level

ASI-5 — Foundational decisions

This decision is ASI-5 because it establishes the first stable release status of the WEM foundational specification ecosystem and creates a permanent public reference for adoption and future evolution.

---

## Related Principles

- `WEM-P-001` — Responsibility Before Structure: the release adds only the active ADR and later release artifacts explicitly required by the accepted responsibility;
- `WEM-P-002` — Separation of Knowledge and Products: WEM 1.0.0 releases maintained engineering knowledge without introducing functional product implementation;
- `WEM-P-003` — Explicit and Traceable Decisions: this ADR, the release commit and annotated tag preserve release context, authority and outcome;
- `WEM-P-004` — Proportional Governance: an ASI-5 Architectural Pause, ADR, complete review and separate publication gate match the scope and cost of the release decision;
- `WEM-P-005` — Technology-Independent Method: the released specifications remain independent from particular technologies, providers and executable orchestrators;
- `WEM-P-006` — Canonical Source of Normative Knowledge: specifications remain authoritative while README and PDF remain subordinate public documentation;
- `WEM-P-007` — Human Accountability: only the Project Owner may accept this ADR, close the Architectural Pause and authorize release publication;
- `WEM-P-008` — Knowledge Preservation Through Evolution: historical Draft references, ADR histories, Git history and the stable, intentionally permanent release tag remain preserved.

---

## Related Specifications and Decisions

- `WEM.md`, for the foundational method, ASI and Architectural Pause;
- `PROJECT_CHARTER.md`, for scope, success criteria and release authority;
- `ENGINEERING_PRINCIPLES.md`, for the Released permanent principles;
- `specifications/ADR_SPECIFICATION.md`, for ADR applicability, lifecycle and human decision authority;
- `specifications/REPOSITORY_BLUEPRINT.md`, for repository and release-artifact responsibilities;
- `specifications/AGENT_COLLABORATION.md`, for collaboration, review and repository-action gates;
- `README.md`, as the non-normative public repository interface;
- `documentation/wem-presentacio.pdf`, as non-normative WEM presentation documentation;
- `LICENSE`, as the implemented CC BY-SA 4.0 legal text;
- WEM-ADR-001 through WEM-ADR-007, as the Accepted decisions implemented before this release proposal.

---

## Implementation Notes

The Project Owner accepted this ADR on 2026-08-08, closed the Architectural Pause and authorized preparation and verification of the WEM 1.0.0 release candidate within the exact scope recorded in the Decision section.

That authorization permits the specification status, current status statements, public repository interface and presentation changes defined by this ADR. It does not authorize creation of the release commit or tag, push or declaration of publication.

Commit, annotated tag creation, push and release publication require a second explicit Project Owner gate after review of the complete implementation diff and the PDF visual-verification evidence.

The release candidate was prepared on 2026-08-08. The five specifications identified by this decision now report Status Released; `ENGINEERING_PRINCIPLES.md` remains unchanged with its previously Released status; and `README.md` now presents the coordinated Released state and adoption reference.

The presentation status and applicable metadata were updated without changing pagination or structure. Visual and render verification covered all four pages: pages 2 through 4 remain render-identical to the prior document, and the page 1 visual difference is limited to the status label. `LICENSE`, historical ADR references and Git history remain unchanged.

No release commit or tag has been created, no push has been performed and release publication remains pending the second explicit Project Owner gate.

---

## End of Record
