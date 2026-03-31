# Motivation

## Who I am
I am Iswar Patra, a B.Tech student in Computer Science and Engineering at KIIT (expected 2028). I focus on simulation engines, system architecture, and performance-intensive scientific modeling. My summer availability is 30–35 hours/week with finals completed by mid-April.

## Why Mesa
Mesa 4.0’s agent-centric API and ContinuousSpace module are perfect for heavy scientific simulations that need reliable spatial indexing and reproducible benchmark results. I already contributed two Mesa-Examples PRs (#347, #348), including a modern predator-prey model with `self.agents.shuffle_do("step")` and `ContinuousSpaceAgent`.

## What I want to learn
I want to quantify how Mesa scales under extreme, real-world continuous-space stress: thousands of agents, high-frequency neighbor queries, and continuous agent add/remove cycles. The goal is to understand spatial index performance and memory behavior so we can provide measurable CI/CD performance checkpoints.

## Where I want to go
I aim to become a long-term mesa-examples maintainer and build gold-standard templates for bioscience, physics, and chemistry use cases with CI/CD grade performance tracking.

## Project Synopsis
**Modernizing Mesa: Continuous Space Benchmarking & API Standardization**

Mesa is strong for social science, but now with 4.0 it can support physics/chemistry-scale workloads. I observed that there is no standard stress benchmark for the continuous-space spatial index. For GSoC, I will build a high-stress benchmark suite with three models (biology, physics, chemistry) designed to push Mesa’s dynamic agent orchestration to the limit.

### 1. Biology
- Start from continuous predator-prey and add evolutionary drift.
- Each agent has mutable DNA vector attributes.
- Tests: high agent count, dynamic grouping, genetic divergence, memory pressure.
- Outcome: researcher-ready template for adaptation/extinction experiments.

### 2. Physics
- High-velocity particle collision model (10,000 agents, high vision radius).
- Evaluate spatial index vs brute-force O(n²) collision detection.
- Outcome: canonical benchmark for high-frequency neighbor queries.

### 3. Chemistry
- Continuous reactor where collisions transform reactants into products.
- High-volume agent creation and deletion in-step without scheduler breaks.
- Outcome: standard benchmark for dynamic reaction generation and deletion.

## Implementation strategy
- Build Mesa 4.0 agent-centric models that run in `ContinuousSpace`.
- Use custom time and memory metrics to log update time per step.
- Scale across 1k to 10k+ agents and capture performance inflection points.
- Provide academic-style README + CI performance scripts for each model.
- Based on inspiration from `mesa-examples` Discussion #417 (revival) to make benchmarks `Verified / Showcase` examples.
- Gist reference: https://gist.github.com/Ishwarpatra/a4b728b262184e4919eb1378eb9ddacc

## Why I’m qualified
- Existing working PRs in Mesa ecosystem.
- Continuously modernized continuous-space benchmark in current repo.
- Strong practical confidence with pre-commit, linting, and Mesa community standards.
- Commitment to build CI-ready scientific performance templates for maintainers.
