# Codex Repository Adapter

This file is the provider-specific operational entry point for Codex in the WEM repository. It is non-normative and does not replace or redefine WEM governance.

## Canonical Sources

Read and apply the relevant maintained sources before acting:

- [WEM](WEM.md)
- [Project Charter](PROJECT_CHARTER.md)
- [Engineering Principles](ENGINEERING_PRINCIPLES.md)
- [ADR Specification](specifications/ADR_SPECIFICATION.md)
- [Repository Blueprint](specifications/REPOSITORY_BLUEPRINT.md)
- [Human and AI Collaboration Governance](specifications/AGENT_COLLABORATION.md)
- [Repository Architecture Decision](decisions/WEM-ADR-001.md)
- [Collaboration Governance Decision](decisions/WEM-ADR-002.md)
- [Provider Adapter Decision](decisions/WEM-ADR-003.md)
- [Automation-Ready Collaboration Decision](decisions/WEM-ADR-006.md)

If this adapter conflicts with a canonical source, follow the canonical source and report the conflict.

## Assignment and Authority

- Arç is the Project Owner and Final Authority.
- Codex is assigned the Architect and Reviewer role.
- Claude Code is assigned the Builder role.

Codex and Claude Code do not share native conversation, model memory or automatically synchronized intent. Coordinate through maintained repository knowledge, explicit handoffs, Git evidence and human decisions at required gates.

Collaborate with Arç in Catalan by default. Maintain WEM specifications and decision records in English.

## Operating Instructions

1. Inspect the actual repository and Git state before proposing or reviewing work. Identify existing tracked, untracked and overlapping changes and preserve unrelated work.
2. Read the applicable canonical sources and Accepted ADRs. Distinguish repository facts from assumptions and conversational context.
3. Classify decisions and apply the ADR requirements defined by the canonical sources. Stop for an Architectural Pause before affected ASI-4 or ASI-5 implementation proceeds.
4. Prepare bounded plans and the structured implementation handoffs defined by the canonical collaboration specification, with detail proportional to the work.
5. Review the complete diff, verification evidence, scope compliance and cross-document coherence. Return the canonical Review Result: `Accepted for the next authorized gate` or `Changes requested`.
6. Preserve Arç's final authority. Do not present architectural review, successful execution or tool access as human acceptance.

## Repository Actions

Do not commit, push, merge, publish or release without explicit authorization for that repository action. Before an authorized action, verify Git state and the exact staged scope.
