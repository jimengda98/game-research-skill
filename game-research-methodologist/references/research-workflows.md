# Research Workflows

Pick one output contract and keep the answer scoped.

## Diagnostic Memo

Use for claims, proposals, abstracts, methods, or paper excerpts.

| Section | Required content |
|---------|------------------|
| Classification | Game model, information structure, payoff structure, policy space, target concept |
| Supported claims | What follows under the stated assumptions |
| Weak assumptions | Missing or fragile modeling assumptions |
| Validation gap | Metric, theorem, baseline, or experiment needed |
| Fixes | Concrete changes to model, method, experiment, or wording |

Tie every critique to a missing assumption, unsupported claim, or missing validation.

## Experiment Plan

Use for game-theoretic, MARL, self-play, and PSRO experiments.

| Section | Required content |
|---------|------------------|
| Research question | One falsifiable question |
| Game/environment | Game type, observation model, payoff convention, horizon, player symmetry |
| Methods | Proposed method, baselines, solver/oracle if applicable |
| Metrics | Performance metrics plus stability/equilibrium metrics when relevant |
| Ablations | Minimal tests of the claimed mechanism |
| Sanity checks | Exact toy game, random/uniform policy, trusted solver comparison, seed sensitivity |
| Acceptance criteria | Results that support or falsify the claim |

For PSRO, include meta-game solver, payoff-table estimation, best-response oracle, duplicate-policy handling, and stopping rule.

For MARL, include CTDE/DTDE assumptions, centralized training information, decentralized execution interface, and whether evaluation is per-policy, per-population, or per-agent.

## Model and Algorithm Recommendation

Use when the user asks what game model to use, what algorithm should solve it, or how to justify a modeling route.

| Section | Required content |
|---------|------------------|
| Candidate models | Plausible models and why each could fit |
| Recommended model | The model that best matches interaction, information, payoff, and scale |
| Rejected alternatives | Why close alternatives are weaker or require different assumptions |
| Algorithm family | Exact method for small cases and approximate/learning method for scale |
| Validation metrics | Equilibrium, regret, robustness, return, or coalition-stability checks |
| Fallback baseline | Small exact solver, random/uniform policy, tabular method, or trusted benchmark |

Use `model-algorithm-selection.md` for the detailed decision matrix.

## Implementation Handoff

Use for algorithm implementation or validation planning.

| Section | Required content |
|---------|------------------|
| Minimal instance | Small exact game where the answer is known |
| Data structures | Payoff table, game tree, information state, policy pool, or trajectory format |
| Algorithm path | Exact baseline first, approximate/scaled method second |
| Validation | Solver comparison, exploitability/NashConv/regret checks, deterministic seeds |
| Failure modes | Numerical instability, weak oracle, payoff noise, invalid information state |
| Done criteria | Tests or plots that make the implementation credible |

Always include the smallest trusted comparison point before scaling.

## Paper Review

Use for papers, introductions, methods, rebuttals, or reviewer comments.

| Section | Required content |
|---------|------------------|
| Major issues | Prioritized argument or evidence failures |
| Claim audit | Claim, assumption, support, missing validation |
| Experiment audit | Baselines, metrics, ablations, seeds, failure cases |
| Writing fixes | Specific narrative or wording changes |
| Residual risk | What remains unproven |

For review-style requests, put findings first and order them by severity.

## Maintenance or Publication Note

Use for skill updates, online publication, bilingual documentation, or release preparation.

| Section | Required content |
|---------|------------------|
| Change summary | Files or sections changed |
| Publication impact | Whether README, docs, release notes, or links need updates |
| Bilingual sync | English/Chinese document pairs checked or updated |
| Validation | Skill validator, route checks, and link/source verification status |
| Release readiness | Remaining blockers before tagging or publishing |

Keep this note short. Point to `maintenance-and-publishing.md` for the full checklist.
## Literature and Code Lookup

Use for papers, codebases, benchmarks, or starting points.

| Section | Required content |
|---------|------------------|
| Topic map | Subtopics in the request |
| Seed papers | Representative starting papers, not an exhaustive bibliography |
| Code anchors | Repositories/libraries and their use cases |
| Verification notes | Facts that require primary-source checks |
| Starting recommendation | One or two best starting points |

When dates, venues, APIs, or install commands matter, verify against official pages or primary papers before presenting them as current facts.

