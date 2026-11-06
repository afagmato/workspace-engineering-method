# WEM 1.1.0 and 1.2.0 Release Assurance Audit

Status: Retrospective evidence audit

Audit date: 2026-11-03

Governing decision: WEM-ADR-012

> Non-normative audit knowledge. This record reports recoverable evidence and explicit gaps. It does not rewrite historical decisions, tags or release claims.

## Scope

This audit evaluates the durable repository evidence available for WEM 1.1.0 and WEM 1.2.0 against the release assurance model accepted after those releases.

The later model is not applied retroactively as a condition that those historical releases were required to satisfy. It is used to identify which assurance facts can and cannot now be recovered.

## WEM 1.1.0

### Recoverable evidence

- Governing decision: WEM-ADR-009, Accepted on 2026-10-27.
- Recorded authority: Project Owner.
- Recorded classification: ASI-5.
- Release commit: `add50b13948841d38ceae06f0465d276b5830f18`.
- Commit timestamp: 2026-10-27T09:27:36+01:00.
- Commit subject: `[ASI-5] Release WEM 1.1.0`.
- Annotated tag: `v1.1.0`.
- Tag message: `Workspace Engineering Method 1.1.0`.
- Tag target matches the release commit.
- Changed scope from `v1.0.0`: seven files, 400 insertions and 24 deletions.
- WEM-ADR-009 records completion of coherence review and explicit Project Owner release approval.

### Evidence gaps

- reviewed candidate base and final staged file list are not preserved as a dedicated assurance record;
- reviewer identity and independence disposition are not recoverable from maintained evidence;
- detailed verification commands and results are not recoverable;
- review findings, corrections and explicit technical Review Result are not recoverable;
- compatibility analysis is asserted by the decision but its complete evidence is not maintained.

## WEM 1.2.0

### Recoverable evidence

- Governing decision: WEM-ADR-010, Accepted on 2026-10-27.
- Recorded authority: Project Owner.
- Recorded classification: ASI-3.
- Release commit: `0a51a7d1d0a79de1432d14579749105328f8fb2c`.
- Commit timestamp: 2026-10-27T09:58:47+01:00.
- Commit subject: `[ASI-3] Release automated project initiation workflow`.
- Annotated tag: `v1.2.0`.
- Tag message: `Workspace Engineering Method 1.2.0`.
- Tag target matches the release commit.
- Changed scope from `v1.1.0`: six files, 683 insertions and 22 deletions.
- WEM-ADR-010 records Project Owner acceptance and release authorization.

### Evidence gaps

- reviewed candidate base and final staged file list are not preserved as a dedicated assurance record;
- reviewer identity and independence disposition are not recoverable from maintained evidence;
- detailed verification commands and results are not recoverable;
- review findings, corrections and explicit technical Review Result are not recoverable;
- no maintained evidence explains how the new 455-line Project Initiation specification was independently reviewed;
- no durable compatibility review identifies inherited assumptions from the release completed thirty-one minutes earlier.

## Rapid-release observation

The release commits are separated by thirty-one minutes and eleven seconds. The interval alone does not establish inadequate review, and WEM-ADR-012 rejects fixed waiting periods as a substitute for evidence.

The lack of durable reviewer, finding and verification evidence prevents this audit from assessing the depth or independence of the two reviews. This is an assurance limitation, not evidence that the published tags or decisions are invalid.

## Current structural checks

A read-only audit on 2026-11-03 found:

- all current relative Markdown links resolved;
- WEM-ADR-001 through WEM-ADR-010 contained their required ADR sections;
- ASI-4 and ASI-5 ADRs contained Alternatives Considered;
- the known stale `candidate` wording and WEM-ADR-009 `proposed alternative` wording were identified for correction.

These current checks cannot substitute for release-time evidence because the working repository has evolved since each tag.

## Disposition

- Preserve `v1.1.0` and `v1.2.0` unchanged.
- Do not fabricate historical reviewer identity, findings or commands.
- Treat the missing durable evidence as a known limitation of those release records.
- Apply WEM-ADR-012 prospectively to the next WEM release.
- Give the WEM 1.3.0 Draft an explicit independent-review disposition and durable assurance record before release.
