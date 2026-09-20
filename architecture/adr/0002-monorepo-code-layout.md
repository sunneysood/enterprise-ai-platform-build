# ADR-0002: Monorepo code layout for the eight projects and the flagship platform

- **Status:** Accepted
- **Date:** 2026-09-21
- **Decision area:** Repository structure

## Context

This repository will hold the code for all eight projects (P1–P8) as well as the documentation. P8 is the flagship platform, and it integrates the other seven. All of it stays in this one repository.

[ADR-0001](https://claude.ai/chat/0001-docs-first-monorepo-with-pr-workflow.md) chose a monorepo and a docs-first workflow. Code starts with P1 around Day 011. That raises four needs: a predictable place for every artifact, projects that build and test on their own, a way for P8 to compose the others without copying them, and CI that does not rebuild everything on every change.

## Decision

1. I will build all eight projects, including the flagship, in this repository.
2. Each project gets one self-contained directory, `projects/pN-<slug>/`, with its own dependency manifest, Dockerfile, tests and README. It builds and tests on its own. The slugs are `p1-api-foundation`, `p2-knowledge-system`, `p3-intake-workflow`, `p4-document-intelligence`, `p5-data-onboarding`, `p6-operations-ai`, `p7-llm-serving` and `p8-platform`.
3. A project directory is created when the project starts, not before.
4. Requirements stay at `projects/pN-requirements.md`. Threat models live at `architecture/threat-models/pN-<slug>.md`. ADRs stay in `architecture/adr/`.
5. Shared code goes into `libs/` only when a second project needs it. Projects may depend on libraries; libraries never depend on projects.
6. P8 composes the other projects through their published contracts (APIs, events, container images), not by copying their code. Each project is added to the platform as it finishes.
7. Infrastructure shared by several projects lives in `infrastructure/`. Deployment files specific to one project stay in its directory. Time-boxed spikes live in `experiments/`.
8. CI is path-scoped: a project's workflow runs when files under its directory or `libs/` change, and a documentation check runs when Markdown changes.

## Alternatives considered

| Option | Why it was not chosen |
|---|---|
| One repository per project | Rejected in ADR-0001, and the goal is one integrated repository. A cross-project contract change is one pull request here. |
| Top-level directories by domain (`ai/`, `data/`, `distributed-systems-lab/`) | They overlap with the projects. One project's code and evidence would scatter across directories. |
| One shared application containing every project | Couples the tests and releases of unrelated capabilities and hides the contracts. P1 could no longer run alone. |
| Build shared libraries up front | Premature. It conflicts with [Principles](https://claude.ai/PRINCIPLES.md) 3 and 17. |
| Copy project code into P8 | The copies diverge, and it drops the explicit-contract discipline of Principle 5. |

## Trade-offs

Gained: a predictable home for every artifact, project-level isolation, explicit contracts between projects, and CI that only runs what changed.

Given up: some duplication until a second project needs the same code, more directories to navigate, the discipline needed to stop `libs/` from becoming a dumping ground, and eventual monorepo tooling as the repository grows.

## Consequences

- The README repository map drops `ai/`, `data/` and `distributed-systems-lab/`, whose content now lives in `projects/` and `experiments/`, and adds `libs/`.
- [Projects](https://claude.ai/projects/README.md) documents the layout inside a project and where each kind of evidence lives.
- A threat-model template is added under `architecture/threat-models/`.
- CI workflows are added as code arrives. The documentation check comes first.
- This narrows the revisit clause in ADR-0001: the flagship stays in this repository. Revisit only if CI time or repository size becomes a real problem.

## Related

- [ADR-0001](https://claude.ai/chat/0001-docs-first-monorepo-with-pr-workflow.md)
- [Projects](https://claude.ai/projects/README.md)
- [Principles](https://claude.ai/PRINCIPLES.md)
