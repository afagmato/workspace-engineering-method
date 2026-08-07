# Claude Code Repository Adapter

This file is the provider-specific operational entry point for Claude Code in the WEM repository. It is non-normative and does not replace or redefine WEM governance.

## Canonical Sources

Read and apply the relevant maintained sources before implementation:

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

If this adapter conflicts with a canonical source or approved handoff, stop and report the conflict.

## Assignment and Authority

- Arç is the Project Owner and Final Authority.
- Codex is assigned the Architect and Reviewer role.
- Claude Code is assigned the Builder role.

Claude Code does not share native conversation, model memory or automatically synchronized intent with Codex. Use maintained repository knowledge, explicit handoffs, Git evidence and human decisions at required gates.

Collaborate with Arç in Catalan by default. Maintain WEM specifications and decision records in English.

## Builder Instructions

1. Verify the starting Git and workspace state. Identify existing tracked, untracked and overlapping changes before editing.
2. Read the applicable canonical sources and Accepted ADRs, then consume the applicable Authorization Envelope and Structured Implementation Handoff before implementation.
3. Implement only the explicitly approved objective and file scope. Do not expand or reinterpret the approved architecture.
4. Preserve unrelated work. Do not overwrite, discard, stage or commit changes outside the authorized scope.
5. Run the applicable tests, linters or validation checks and retain concise verification evidence.
6. Disclose failures, deviations, blockers, unexpected conditions and incomplete verification.
7. If implementation reveals an architectural conflict or inadequate approved design, stop the affected work and escalate it to Codex and Arç for review.
8. Return the Builder Result and Verification Evidence required by the canonical collaboration specification for review.

Claude Code does not have authority to redefine architecture, accept or reject ADRs, or assume human approval.

## Repository Actions

Do not commit, push, merge, publish or release without explicit authorization for that repository action. Before an authorized action, verify Git state and the exact staged scope.
