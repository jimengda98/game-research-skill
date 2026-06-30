# Model and Algorithm Selection

Use this reference when the task is to choose a game model, select a solver or learning algorithm, or justify why one modeling route is better than another.

## Selection Rule

Choose in this order:

1. Interaction structure: simultaneous, sequential, repeated, stochastic, leader-follower, coalition, or mechanism.
2. Information structure: full information, imperfect information, partial observation, private type, or decentralized execution.
3. Payoff structure: zero-sum, general-sum, fully cooperative, mixed-motive, transferable utility, or empirical payoff table.
4. Scale and representation: exact finite game, sampled simulator, neural policy, policy pool, or unknown black-box environment.
5. Required claim: equilibrium, no-regret, robustness, ranking, credit allocation, coalition stability, or benchmark performance.

Do not choose an algorithm until the model and claim are explicit.

## Model Choice Matrix

| Research situation | Preferred model | Use when | Avoid when |
|--------------------|-----------------|----------|------------|
| One-shot strategic decision with finite actions | Normal-form game | Payoff matrix is available or estimable | State/history matters |
| Learned policies evaluated by pairwise matches | Empirical game over policies | Policies are the strategic actions | Policy pool is too narrow to support broad claims |
| Sequential perfect-information interaction | Extensive-form perfect-information game | Full history is visible | Hidden information or private observations dominate |
| Sequential hidden-information interaction | Extensive-form imperfect-information game | Information sets and perfect recall can be defined | State abstraction destroys recall or belief meaning |
| Multi-state multi-agent environment | Stochastic/Markov game | Transitions and policies matter | The problem is actually one-shot or purely static |
| Repeated strategic interaction | Repeated game | Long-run incentives and history-dependent strategies matter | Stage-game payoffs alone answer the question |
| Leader commits and followers respond | Stackelberg game | Commitment and follower best response are central | Moves are simultaneous or commitment is unrealistic |
| Agents form coalitions or allocate value | Cooperative/coalition game | Coalition value, credit, or blocking matters | Only unilateral strategic deviation matters |
| Incentive-compatible allocation or reporting | Mechanism/Bayesian game | Private types and truthful reporting matter | No private information or allocation rule is involved |

## Algorithm Choice Matrix

| Model | Small exact setting | Scaled or approximate setting | Primary validation |
|-------|---------------------|-------------------------------|--------------------|
| Zero-sum normal-form | Minimax linear programming | Online mirror descent, regret matching, policy-gradient self-play | Exploitability, value gap |
| General-sum normal-form | Support enumeration, Lemke-Howson | Regret dynamics, replicator dynamics, empirical game analysis | NashConv, CE/CCE gap, support checks |
| Empirical game over policies | Meta-game equilibrium solver | PSRO, double oracle, Alpha-Rank, population-based training | NashConv, oracle gain, payoff uncertainty |
| Perfect-information extensive-form | Backward induction, minimax | MCTS, alpha-beta, search plus learning | Game value, exploitability or head-to-head with search baseline |
| Imperfect-information extensive-form | Sequence-form LP, tabular CFR | MCCFR, CFR+, Deep CFR, NFSP, ReBeL-style search/learning | Exploitability, counterfactual regret |
| Stochastic/Markov game, zero-sum | Shapley stochastic game DP, minimax-Q | Self-play RL, robust RL, PSRO over policies | Exploitability or best-response value in evaluated game |
| Stochastic/Markov game, general-sum | Nash-Q, CE-Q for small tabular cases | MAPPO, MADDPG, independent RL plus empirical-game evaluation | NashConv, BR value, return, seed sensitivity |
| Fully cooperative Markov game | Centralized planning, tabular value iteration | QMIX, VDN, QPLEX, MAPPO, HAPPO/HATRPO | Return, win rate, decentralized execution checks |
| Repeated game | Fictitious play, no-regret dynamics | Self-play, PFSP, population training | Regret, exploitability, held-out historical opponents |
| Stackelberg game | Bilevel enumeration, MILP/LP when structure allows | Differentiable best response, RL follower oracle, Stackelberg PSRO | Follower BR, leader value, tie-breaking sensitivity |
| Coalition game | Exact Shapley, core LP, least-core LP | Monte Carlo Shapley, sampled coalition constraints, relaxed-core optimization | Shapley error, core violation, blocking-coalition rate |
| Mechanism/Bayesian game | Incentive-constraint LP, auction-specific solver | Differentiable mechanism design, simulation-based mechanism search | Incentive compatibility regret, welfare/revenue, individual rationality |

## Practical Defaults

| User goal | Default recommendation |
|-----------|------------------------|
| Audit a Nash claim for learned MARL policies | Model as an empirical game over policies; compute/estimate best-response gain or NashConv before using Nash language |
| Design PSRO experiments | Model as an empirical policy-space game; use PSRO/double oracle with a documented meta-solver, oracle, payoff estimator, and stopping rule |
| Compare cooperative MARL baselines | Model as a cooperative Markov game; use MAPPO plus value-decomposition baselines when action spaces and observations fit |
| Study hidden-information strategic reasoning | Model as an imperfect-information extensive-form game; start with tabular CFR/MCCFR before neural variants |
| Study long-run self-play behavior | Model as a repeated or stochastic game; evaluate historical opponents, exploitability/BR value, and population diversity |
| Study credit allocation | Model as a cooperative/coalition game layered on the task; separate Shapley attribution from core stability |
| Build a small sanity-check implementation | Start with a normal-form matrix game or tiny extensive-form game; solve exactly before adding RL or neural policies |

## Fallback Baselines

Always include at least one baseline that can fail visibly if the proposed model is wrong:

- Uniform/random strategy for matrix or empirical games.
- Exact minimax or support-enumeration solution for small normal-form cases.
- Tabular CFR before Deep CFR or neural game solving.
- Random, latest-self, and historical-self opponents for self-play.
- MAPPO or QMIX-family baseline for cooperative MARL, depending on action/observation structure.
- Monte Carlo Shapley and unconstrained allocation baseline for coalition allocation.

## Claim Discipline

| Claim | Required model and algorithm evidence |
|-------|---------------------------------------|
| "The policy is Nash" | Strategy class, game/payoff definition, best-response computation, exploitability or NashConv |
| "The algorithm converges" | Exact game class, dynamics, assumptions, convergence metric, finite-sample behavior |
| "The self-play method is robust" | Opponent distribution, historical/held-out opponents, best-response or population metric |
| "The allocation is fair" | Coalition value definition, Shapley or fairness axiom, approximation error |
| "The allocation is stable" | Core/least-core constraints, blocking-coalition check, relaxation if core is empty |
| "The method scales" | Payoff-estimation cost, oracle cost, sample budget, sensitivity to policy-pool size |

## Output Template

```text
Recommended model: ...
Why this model: ...
Rejected alternatives: ...
Algorithm family: ...
Exact/small baseline: ...
Scaled method: ...
Validation metrics: ...
Failure modes: ...
Primary-source/code anchors to verify: ...
```
