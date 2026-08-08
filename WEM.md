---
Document: WEM
Title: Workspace Engineering Method
Version: 1.0.0
Status: Released
Type: Foundation
ASI: 5
Language: English
Owner: Workspace Engineering Method
Methodology: WEM
---

# Workspace Engineering Method (WEM)

## Purpose

The Workspace Engineering Method (WEM) defines the engineering principles, governance model and decision-making process used to design, build, evolve and maintain software systems.

WEM is technology independent.

It does not prescribe programming languages, frameworks or platforms.

Instead, it defines how engineering decisions are made.

Projects adopting WEM SHALL follow the specifications that compose the WEM ecosystem.

---

## Scope

WEM applies to:

- engineering governance
- software architecture
- repository organization
- documentation
- knowledge management
- software quality
- AI-assisted engineering

Implementation details remain the responsibility of each individual project.

---

## Normative Language

The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119 and RFC 8174) when, and only when, they appear in all capitals.

---

## Vision

Software should improve with time.

Engineering decisions SHALL prioritize clarity, maintainability and long-term evolution over short-term convenience.

---

## Core Philosophy

Software quality is determined before implementation begins.

Thinking precedes architecture.

Architecture precedes implementation.

Knowledge preserves both.

---

## Engineering Lifecycle

Every WEM project follows the same engineering lifecycle.

Thinking

↓

Architecture

↓

Implementation

↓

Evolution

↓

Knowledge

Knowledge generated during development SHALL become reusable whenever possible.

---

## Modular Specification

WEM is composed of modular specifications with distinct responsibilities.

This document defines the engineering method only.

Additional specifications are introduced only when a distinct normative responsibility becomes real, in accordance with `WEM-P-001`.

The Repository Blueprint governs how specification responsibilities and canonical locations are represented in the WEM repository.

The public repository interface provides non-normative navigation to the currently maintained specifications, decisions and supporting artifacts.

Documents SHALL reference the canonical source responsible for normative knowledge instead of duplicating it.

---

## Engineering Principles

Engineering principles are defined and governed by `ENGINEERING_PRINCIPLES.md`.

WEM and adopting projects SHALL interpret, apply and reference engineering principles in accordance with that specification.

---

## Architectural Stability Index

An engineering decision SHALL receive an Architectural Stability Index (ASI) when it constrains future work, affects multiple components or projects, modifies an established contract or structure, or requires coordinated effort to reverse.

Routine, local and readily reversible implementation choices MAY remain unclassified.

When the scope or future impact of a decision is uncertain, the decision SHOULD receive an ASI.

ASI measures the expected scope and cost of changing a decision. It does not measure the perceived importance of the decision.

| Level | Meaning |
| --- | --- |
| ASI-5 | Foundational decisions |
| ASI-4 | Repository and architectural structure |
| ASI-3 | Framework architecture |
| ASI-2 | Public interfaces |
| ASI-1 | Internal implementation |

Higher ASI levels require greater engineering scrutiny.

---

## Architectural Pause

Changes affecting ASI-4 or ASI-5 SHALL trigger an Architectural Pause.

During an Architectural Pause:

- implementation stops
- alternatives are evaluated
- consequences are documented
- the applicable ADR requirements defined in `specifications/ADR_SPECIFICATION.md` are applied

Implementation SHALL NOT continue until the pause is complete.

---

## Architecture Decision Records

Architecture Decision Records (ADR) preserve the context, decision, consequences, classification and responsible authority of engineering decisions that require durable traceability.

`specifications/ADR_SPECIFICATION.md` is the canonical source for:

- ADR applicability;
- required content;
- lifecycle;
- decision authority;
- identifier governance;
- the relationship between ADRs and ASI;
- the relationship between ADRs and Architectural Pauses.

WEM and adopting projects SHALL apply the ADR governance defined in that specification.

---

## Documentation

Documentation is part of the engineering process.

Outdated documentation SHALL be treated as a defect.

Documentation SHALL evolve together with the software.

---

## Knowledge

Knowledge is an engineering asset.

Lessons learned SHALL be preserved whenever they can improve future projects.

Knowledge SHALL remain independent from implementation whenever possible.

---

## Artificial Intelligence

AI agents are engineering collaborators.

AI agents SHALL:

- preserve architectural consistency
- follow WEM specifications
- question decisions that violate WEM
- document significant architectural proposals

Human decision-makers retain final responsibility.

---

## Repository

Repositories adopting WEM SHALL comply with the Repository Blueprint specification.

Repository organization reflects engineering architecture.

---

## Governance

Engineering decisions SHALL be explicit.

Significant decisions SHALL remain traceable.

Foundational changes require architectural review.

---

## Evolution

WEM is intended to evolve.

Future versions SHALL preserve engineering knowledge whenever possible.

Breaking changes SHALL be explicitly justified and documented.

---

## End of Specification
