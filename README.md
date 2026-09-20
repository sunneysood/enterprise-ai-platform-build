# Enterprise AI Platform Build

> A hands-on journey from system design to production-grade Enterprise AI architecture.

This repository is a public build log: a roadmap, the decisions made along the way, and the code and evidence behind them.

The objective is to develop the ability to **understand, design, build, break, measure, secure, and explain** production AI systems.

## North Star

By the end of the journey, I should be able to demonstrate a coherent capability stack:

**System Design → Distributed Systems → API Design → Data → AI Systems → RAG → Agents → Evaluation → LLM Infrastructure → Cloud/DevOps → Security/Governance → Enterprise Architecture**

All of these converge into **one flagship Enterprise AI platform**.

## Working Method

Work is driven by gaps. A gap is something the build exposed that I could not yet answer, decide or prove. Each one is logged in [GAPS.md](./GAPS.md) and closed by a decision or by evidence. I study only what is needed to close the current gap.

**Build → Break → Measure → Decide → Document**

The repository values:

- architectural reasoning
- trade-offs
- working implementations
- production failure modes
- implementation evidence via project development

## Repository Map

```
architecture/              Architecture artifacts and decisions
system-design/             (planned) Distributed systems and real-world system studies
api-design/                Production API architecture
data/                      (planned) Data engineering and governance
ai/                        (planned) LLMs, RAG, agents, evaluation, inference
distributed-systems-lab/   (planned) Hands-on distributed systems implementation
projects/                  Progressive capability slices
experiments/               (planned) Focused technical experiments
days/                      Day-by-day journal of gaps found and closed
docs/                      Durable technical notes
infrastructure/            (planned) Docker, Kubernetes, Terraform, Azure
.github/                   PR template (CI, security and evaluation automation planned)
```

## The 100-Day Structure

A 'day' is one working session (about 2-3 hours), roughly 3-4 per week, over about 6-8 months.

| Days | Focus |
|---|---|
| 001–010 | Architecture foundations & system design |
| 011–035 | Distributed systems |
| 036–045 | Data & messaging |
| 046–055 | Enterprise RAG |
| 056–065 | Agents & stateful workflows |
| 066–072 | Document intelligence & data pipelines |
| 073–080 | AI evaluation & security |
| 081–090 | LLM infrastructure & serving |
| 091–100 | Enterprise AI architecture synthesis |

The sequence is intentionally progressive. Earlier capabilities become building blocks for later ones.

## Core Engineering Questions

For every system, ask:

1. What problem is being solved?
2. What are the functional requirements?
3. What are the quality attributes and NFRs?
4. What are the expected load and growth assumptions?
5. What can fail?
6. What should be synchronous vs asynchronous?
7. Where does state live?
8. How are identities, data, tools and tenants secured?
9. How is the system observed and evaluated?
10. What does it cost?
11. How does it recover?
12. Why is this architecture preferable to the alternatives?

## Flagship Platform

The journey ultimately converges into a production-oriented Enterprise AI platform containing:

- multi-tenant identity and authorization
- API and AI gateway
- enterprise knowledge/RAG
- stateful agent workflows
- document intelligence
- customer/data onboarding
- operational AI workflows
- model routing and LLM serving
- evaluation and regression testing
- observability and tracing
- security and governance
- FinOps and cost controls
- resilience, scaling and disaster recovery

The flagship is the **proof of integration**: everything built along the way, working together.

## Current Status

### Day 0 — Preparation

The preparation period runs until the official start (target: 1 November 2026). Status and the readiness checklist are tracked in [PROGRESS.md](./PROGRESS.md).

## Guiding Principle
**“What architectural problem can I solve now that I could not solve before?”**
