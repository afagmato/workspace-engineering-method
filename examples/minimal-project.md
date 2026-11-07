# Minimal WEM Project Example

> Non-normative conceptual example. It illustrates proportional adoption and does not define WEM requirements.

## Scenario

`Tiny Notes` is a personal command-line application maintained by one developer. It stores short notes locally. It has no public API, remote service, AI participant or release automation.

## Initial foundation

The project starts with one maintained artifact:

```text
/
└── PROJECT_CHARTER.md
```

Its Charter declares:

```text
Project: Tiny Notes
Type: Executable software product
Methodology: WEM 1.3.0 — Released
Project Owner and Final Authority: Maintainer
Mission: Provide reliable local capture and retrieval of short text notes.
```

The initial scope excludes synchronization, accounts, encryption and plugins. Those exclusions prevent speculative architecture; they do not permanently prohibit future governed evolution.

The WEM 1.3.0 Initiation Run also evaluates structural validation. It records:

```text
Validator Adoption Disposition: Adopt
Implementation: WEM Validator
Compatibility profile: wem-1.2.0
Authorized effects: local read-only validation of maintained WEM artifacts
Deferred effects: maintained configuration and CI integration
Limitation: structural evidence does not certify the project or replace human review
```

The maintainer accepts this disposition with the foundation. The validator can therefore run within the stated read-only scope, but the decision does not authorize additional repository or CI changes.

## First Milestone

Outcome: a local command can add and list notes from one explicit data file.

The maintainer records:

- scope: one executable package and focused tests;
- acceptance: add then list returns the same Unicode text;
- verification: format, unit tests and one CLI smoke test;
- human-reserved decisions: changing storage outside the local file boundary;
- stop condition: any requirement for credentials, networking or destructive migration.

The implementation-language choice is local and reversible, so the maintainer records it in the Milestone rather than creating an ADR.

## First architectural decision

Later, synchronization becomes a real objective. It introduces an externally consumed protocol and affects storage, conflict handling and migration. The project creates its first ADR before implementation:

```text
decisions/
└── TINY-ADR-001.md
```

The ADR evaluates local-only operation, provider-owned synchronization and a provider-independent synchronization boundary. Only after the required decision is accepted does the project introduce the corresponding structure.

## What the project does not create initially

- empty `decisions/`, `documentation/`, `templates/` or `knowledge/` directories;
- an ADR for formatting or a private helper function;
- provider adapters without an active provider responsibility;
- duplicated summaries of WEM governance.

This example demonstrates that WEM adoption starts from responsibilities and decisions, not from reproducing the WEM repository tree.
