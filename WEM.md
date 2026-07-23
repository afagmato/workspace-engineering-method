\---


Document: WEM



Title: Workspace Engineering Method



Version: 1.0.0



Status: Draft



Type: Foundation



ASI: 5



Language: English



Owner: Workspace Engineering Method



Methodology: WEM



\---







\# Workspace Engineering Method (WEM)







\## Purpose







The Workspace Engineering Method (WEM) defines the engineering principles, governance model and decision-making process used to design, build, evolve and maintain software systems.







WEM is technology independent.







It does not prescribe programming languages, frameworks or platforms.







Instead, it defines how engineering decisions are made.







Projects adopting WEM SHALL follow the specifications that compose the WEM ecosystem.







\---







\# Scope







WEM applies to:







\- engineering governance



\- software architecture



\- repository organization



\- documentation



\- knowledge management



\- software quality



\- AI-assisted engineering







Implementation details remain the responsibility of each individual project.







\---







\# Normative Language







The keywords SHALL, SHALL NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in RFC 2119.







\---







\# Vision







Software should improve with time.







Engineering decisions SHALL prioritize clarity, maintainability and long-term evolution over short-term convenience.







\---







\# Core Philosophy







Software quality is determined before implementation begins.







Thinking precedes architecture.







Architecture precedes implementation.







Knowledge preserves both.







\---







\# Engineering Lifecycle







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







\---







\# Modular Specification







WEM is composed of independent specifications.







This document defines the engineering method only.







Additional specifications define:







\- Engineering Principles



\- Repository Blueprint



\- Project Charter



\- AI Agents



\- Standards



\- Architecture Decision Records



\- Coding Standards







Documents SHALL reference each other instead of duplicating knowledge.







\---







\# Engineering Principles







Engineering principles are defined in a dedicated specification.







Each principle SHALL have:







\- permanent identifier



\- title



\- statement



\- rationale







Projects SHALL reference principles by identifier.







\---







\# Architectural Stability Index







Every engineering decision SHALL receive an Architectural Stability Index (ASI).







ASI-5 — Foundational decisions







ASI-4 — Repository and architectural structure







ASI-3 — Framework architecture







ASI-2 — Public interfaces







ASI-1 — Internal implementation







Higher ASI levels require greater engineering scrutiny.







\---







\# Architectural Pause







Changes affecting ASI-4 or ASI-5 SHALL trigger an Architectural Pause.







During an Architectural Pause:







\- implementation stops



\- alternatives are evaluated



\- consequences are documented



\- ADR creation is evaluated







Implementation SHALL NOT continue until the pause is complete.







\---







\# Architecture Decision Records







Significant engineering decisions SHALL be documented using Architecture Decision Records (ADR).







Each ADR SHALL include:







\- Identifier



\- Title



\- Status



\- Context



\- Decision



\- Consequences



\- ASI Level



\- Related Principles







\---







\# Documentation







Documentation is part of the engineering process.







Outdated documentation SHALL be treated as a defect.







Documentation SHALL evolve together with the software.







\---







\# Knowledge







Knowledge is an engineering asset.







Lessons learned SHALL be preserved whenever they can improve future projects.







Knowledge SHALL remain independent from implementation whenever possible.







\---







\# Artificial Intelligence







AI agents are engineering collaborators.







AI agents SHALL:







\- preserve architectural consistency



\- follow WEM specifications



\- question decisions that violate WEM



\- document significant architectural proposals







Human decision-makers retain final responsibility.







\---







\# Repository







Repositories adopting WEM SHALL comply with the Repository Blueprint specification.







Repository organization reflects engineering architecture.







\---







\# Governance







Engineering decisions SHALL be explicit.







Significant decisions SHALL remain traceable.







Foundational changes require architectural review.







\---







\# Evolution







WEM is intended to evolve.







Future versions SHALL preserve engineering knowledge whenever possible.







Breaking changes SHALL be explicitly justified and documented.







\---







\# End of Specification



