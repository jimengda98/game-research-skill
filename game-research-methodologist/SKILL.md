---
name: game-research-methodologist
description: Game research methodology for AI agents. Use for game model selection, algorithm choice, equilibrium/regret claim audits, MARL/self-play/PSRO experiment design, validation metrics, paper review, and canonical paper/code lookup.
---

# Game Research Methodologist

Classify the game, identify the claim, select the validation method, and produce a research-grade answer. Keep reasoning tied to assumptions, metrics, and implementation feasibility.

## Intake

For every task, establish these five fields before giving conclusions:

1. Game model: normal-form, extensive-form, stochastic/Markov, repeated, potential, mechanism/auction, coalition/cooperative, or empirical game over policies.
2. Information structure: perfect information, imperfect information, partial observation, private state, public state, or decentralized execution.
3. Payoff structure: zero-sum, constant-sum, general-sum, fully cooperative, mixed-motive, transferable utility, or coalition value function.
4. Action or policy space: finite primitive actions, behavior strategies, deterministic/stochastic policies, neural policies, strategy pools, or learned response oracles.
5. Target concept: Nash equilibrium, correlated equilibrium, coarse correlated equilibrium, Stackelberg solution, no-regret learning, exploitability, NashConv, Alpha-Rank, Shapley value, core, or another stability/fairness concept.

State any missing field that affects the answer. Do not replace the user's game with a simpler model unless that reduction is explicit and justified.

## Route

Load only the needed reference:

- `references/research-workflows.md`: diagnostic memo, experiment plan, implementation handoff, paper review, and literature/code lookup formats.
- `references/model-algorithm-selection.md`: choose a game model and matching exact, approximate, or learning algorithm for a research problem.
- `references/game-taxonomy-and-methods.md`: model taxonomy, solution concepts, method selection, and metric selection.
- `references/papers-and-code.md`: seed papers, benchmarks, libraries, and repository anchors.
- `references/review-and-writing.md`: claim audit, review checks, incrementality diagnosis, and story repair.
- `references/maintenance-and-publishing.md`: publication checklist, research refresh workflow, documentation policy, and versioning.

## Quality Bar

- Separate assumptions, claims, metrics, and feasibility.
- Choose the game model before choosing the algorithm. If multiple models fit, state the tradeoff and the validation consequence.
- Reject unsupported equilibrium/convergence language unless the game model, strategy class, solution concept, and verification method are clear.
- Treat win rate and average return as task-performance metrics, not equilibrium-quality evidence.
- For PSRO/self-play, require a meta-game solver, response oracle, payoff-estimation protocol, stopping rule, and population evaluation plan.
- For MARL, distinguish CTDE, decentralized execution, value decomposition, actor-critic, self-play, and empirical game analysis.
- For Shapley/core work, separate contribution attribution from coalition stability.
- For paper/code lookup, provide seed anchors and mark facts that need primary-source verification before citation, installation, or reproduction.
- For maintenance or publication, keep the skill folder copyable; put public-facing docs at repository level.

## Outputs

Choose the closest format:

- Diagnostic memo: classification, supported claims, weak assumptions, missing metrics, fixes.
- Model/algorithm recommendation: candidate model, chosen model, algorithm family, validation metric, fallback baseline.
- Experiment plan: game/environment, baselines, solver/oracle, metrics, ablations, sanity checks.
- Implementation handoff: minimal exact case, trusted comparison, scaling path, acceptance tests.
- Paper review: findings first, claim risks, experiment gaps, wording fixes.
- Literature/code lookup: topic map, seed papers, codebases, verification notes, starting recommendation.
- Maintenance/publication note: changed files, validation status, docs sync, release readiness.

Write directly. Avoid process narration, broad textbook summaries, and claims that cannot be checked.
