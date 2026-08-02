---
Document: Architecture Decision Record
Identifier: WEM-ADR-004
Title: License WEM repository content under CC BY-SA 4.0
Status: Accepted
Created Date: 2026-08-02
ASI Level: 4
Decision Authority: Project Owner
WEM Reference: WEM 1.0.0 — Draft
---

# WEM-ADR-004 — License WEM repository content under CC BY-SA 4.0

## Identifier

`WEM-ADR-004`

---

## Title

License WEM repository content under CC BY-SA 4.0

---

## Status

Accepted

---

## Created Date

2026-08-02

---

## Status History

| Date | Status | Decision Authority | Reason |
| --- | --- | --- | --- |
| 2026-08-02 | Proposed | Project Owner | ASI-4 Architectural Pause opened for WEM repository licensing. |
| 2026-08-02 | Accepted | Project Owner | CC BY-SA 4.0 repository licensing approved and implementation authorized. |

---

## Decision Authority

Project Owner

---

## WEM Reference

WEM 1.0.0 — Draft

---

## Context

The WEM repository is public and contains maintained engineering knowledge, including specifications, Engineering Principles, Architecture Decision Records, provider-specific repository adapters and explanatory documentation.

The repository currently has no public license. Copyright protection generally attaches automatically when eligible creative work is fixed, so public availability alone does not grant clear permission to copy, redistribute or adapt repository content.

WEM is intended to be studied, applied, translated and improved. A standardized public license would make those permissions explicit while preserving attribution and requiring shared adaptations to retain equivalent licensing conditions.

The license must match the repository's responsibility as maintained engineering knowledge rather than executable software. Functional products, software libraries and software repositories remain outside the WEM repository responsibility and require licensing appropriate to software when they become real.

The licensing decision must also distinguish material that WEM has authority to license from third-party material, preserve human authority over publication and licensing, avoid implied endorsement and account for rights that Creative Commons licenses do not grant.

This decision is ASI-4 because it establishes repository-wide legal terms, affects publication and reuse of all maintained WEM content, grants permissions that cannot be withdrawn retroactively from material already distributed under them and would require coordinated legal and repository changes to replace in the future.

The Architectural Pause opened while this decision was Proposed and is complete following explicit approval by the Project Owner.

---

## Decision

The decision is to license WEM repository content under the Creative Commons Attribution-ShareAlike 4.0 International Public License.

The SPDX identifier is:

```text
CC-BY-SA-4.0
```

The license applies to material maintained by WEM in the following repository responsibilities:

- WEM specifications;
- Engineering Principles;
- Architecture Decision Records;
- standards, when created;
- repository documentation and presentations;
- templates and conceptual examples, when created;
- provider-specific repository adapters.

The license applies only to material for which the licensor has authority to grant the Licensed Rights.

Material explicitly identified as third-party material or as excluded from the repository-wide license will remain governed by its own applicable terms. Contributors must have authority to license their contributions under the repository license.

Executable products, software libraries and software repositories are outside this licensing decision. Future software repositories will require a suitable software license chosen within their own responsibilities.

The requested attribution identity will be:

```text
Workspace Engineering Method (WEM), by Arç Fontrodona
```

Users who share licensed material must comply with the attribution requirements of CC BY-SA 4.0, including retaining the supplied creator identification, identifying the applicable license and indicating modifications when required.

Adaptations that are shared must comply with the applicable ShareAlike conditions, including use of an authorized Adapter's License under the terms of CC BY-SA 4.0.

Patent and trademark rights are not licensed by CC BY-SA 4.0. The license will not imply that Arç, WEM or another attribution party sponsors, endorses or grants official status to a user or use.

Privacy, publicity, moral and other rights may require separate consideration or permission where applicable.

A future change in WEM licensing strategy will not terminate permissions already granted for material previously distributed under CC BY-SA 4.0.

This Accepted decision authorizes creation of a conventional root `LICENSE` file containing the official, unmodified plain-text CC BY-SA 4.0 legal code downloaded directly from:

```text
https://creativecommons.org/licenses/by-sa/4.0/legalcode.txt
```

No attribution header, custom clause, paraphrase, translation or other modification will be inserted into the official legal code.

---

## Consequences

### Positive

- public reuse rights become explicit;
- translation and adaptation are permitted;
- attribution is mandatory when the license conditions apply;
- ShareAlike preserves equivalent licensing conditions for shared adaptations;
- the license type aligns with the repository's responsibility as maintained knowledge;
- standardized international terms reduce dependence on custom licensing language.

### Negative

- commercial reuse remains permitted;
- permissions granted for distributed material cannot be retroactively revoked;
- ShareAlike may reduce compatibility with material under different licenses;
- third-party material must be identified and governed carefully;
- the requested attribution information must remain accurate and maintained.

### Risks and Limitations

- contributors must have authority to license their contributions;
- provider-specific or third-party content may require separate rights verification;
- Creative Commons licenses are not intended as the default license for executable software;
- trademark, patent, privacy, publicity and moral rights may require separate treatment;
- a future WEM logo or trademark policy would be a separate responsibility;
- applying a repository-wide license does not guarantee that every element is eligible for copyright protection or controlled by the licensor;
- this ADR records WEM's licensing decision and official-source analysis but does not constitute legal advice.

### New Responsibilities

- maintain the conventional root `LICENSE` file;
- preserve the requested attribution identity;
- identify material excluded from the repository-wide license;
- review licensing implications before adding third-party material;
- verify that contributors have authority to license their contributions;
- use separate licensing decisions for future software repositories.

---

## Alternatives Considered

### Alternative A — No public license

WEM would continue without a public license.

Copyright would remain reserved by default for eligible material, and public availability would not provide explicit general authorization to copy, redistribute or adapt the repository content.

This alternative avoids granting public permissions but conflicts with WEM's goal of enabling study, adoption, translation and improvement.

It was not selected because it leaves reuse rights unclear and requires prospective users to rely on exceptions, limitations or individual permission.

### Alternative B — CC BY 4.0

WEM content would use Creative Commons Attribution 4.0 International.

This alternative permits sharing and adaptation, including commercial use, subject to attribution and the other applicable license terms. It does not require shared adaptations to preserve equivalent licensing through a ShareAlike condition.

This alternative provides broad interoperability but offers less assurance that adaptations of WEM knowledge remain available under comparable terms.

It was not selected because WEM intends shared adaptations to preserve equivalent open licensing conditions.

### Alternative C — CC BY-SA 4.0

WEM content would use Creative Commons Attribution-ShareAlike 4.0 International.

This alternative permits sharing and adaptation, including commercial use, subject to attribution, indication of changes and the applicable ShareAlike conditions.

It was selected because it supports public reuse and translation while requiring shared adaptations to remain under the same license, a later version with the same license elements or a recognized BY-SA Compatible License as permitted by the legal code.

### Alternative D — Apache License 2.0

WEM content would use the Apache License 2.0.

This alternative is designed for software and is suitable for many executable software projects. The current WEM repository, however, is a maintained engineering-knowledge repository and explicitly excludes executable products, runtime libraries and functional implementations.

It was not selected because a software-oriented license does not match the repository's current responsibility. Future software repositories will require their own licensing decisions.

---

## ASI Level

ASI-4 — Repository and architectural structure

---

## Related Principles

- `WEM-P-001` — Responsibility Before Structure;
- `WEM-P-002` — Separation of Knowledge and Products;
- `WEM-P-003` — Explicit and Traceable Decisions;
- `WEM-P-004` — Proportional Governance;
- `WEM-P-005` — Technology-Independent Method;
- `WEM-P-006` — Canonical Source of Normative Knowledge;
- `WEM-P-007` — Human Accountability;
- `WEM-P-008` — Knowledge Preservation Through Evolution.

---

## Related Specifications and Decisions

- `WEM.md`;
- `PROJECT_CHARTER.md`;
- `ENGINEERING_PRINCIPLES.md`;
- `specifications/ADR_SPECIFICATION.md`;
- `specifications/REPOSITORY_BLUEPRINT.md`;
- `specifications/AGENT_COLLABORATION.md`;
- `decisions/WEM-ADR-001.md`;
- `decisions/WEM-ADR-002.md`;
- `decisions/WEM-ADR-003.md`.

---

## Official Sources

- Creative Commons deed for CC BY-SA 4.0: `https://creativecommons.org/licenses/by-sa/4.0/`;
- Creative Commons legal code for CC BY-SA 4.0: `https://creativecommons.org/licenses/by-sa/4.0/legalcode.en`;
- official plain-text CC BY-SA 4.0 legal code: `https://creativecommons.org/licenses/by-sa/4.0/legalcode.txt`;
- Creative Commons FAQ on applying CC licenses to software: `https://creativecommons.org/faq/#can-i-apply-a-creative-commons-license-to-software`;
- Creative Commons deed for CC BY 4.0: `https://creativecommons.org/licenses/by/4.0/`;
- SPDX license identifier record: `https://spdx.org/licenses/CC-BY-SA-4.0.html`.

The official sources verify that CC BY-SA 4.0 permits sharing and adaptation, including commercial use; requires attribution, indication of changes and ShareAlike when applicable; does not license patent or trademark rights; prohibits implied endorsement; and limits the grant to rights the licensor has authority to license.

Creative Commons states that its licenses are irrevocable, subject to their terms, and recommends software-specific licenses for software itself while permitting Creative Commons licenses for software documentation.

The SPDX license list identifies `CC-BY-SA-4.0` as the short identifier for Creative Commons Attribution Share Alike 4.0 International.

---

## Implementation Notes

The Architectural Pause completed on 2026-08-02 when the Project Owner accepted this decision.

The Project Owner approved CC BY-SA 4.0 repository licensing and authorized creation of the root `LICENSE` file.

The official plain-text legal code was downloaded byte-for-byte from `https://creativecommons.org/licenses/by-sa/4.0/legalcode.txt` and created as the root `LICENSE` file.

An independent second download matched `LICENSE` by byte length and SHA-256 hash.

The verified `LICENSE` SHA-256 is:

```text
28A9529C7D0BB4DC51F4BF5C116A3D16EF247A052F7591466768DDF563FD1CF5
```

No attribution header, custom clause or other content was inserted into the official legal code.

During Phase 1, no repository file other than this ADR was changed.

---

## End of Record
