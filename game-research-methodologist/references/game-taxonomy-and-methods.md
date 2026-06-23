# Game Taxonomy and Methods

Map the request to the correct model, solution concept, method, and metric.

## Model Classification

| Model | Use when | Watch for |
|-------|----------|-----------|
| Normal-form game | One-shot simultaneous actions or empirical payoff matrix | Mixed strategies and support constraints |
| Extensive-form game | Sequential decisions with histories | Information sets and perfect recall |
| Stochastic/Markov game | Multi-state interaction with transition dynamics | Stationarity, observability, horizon |
| Repeated game | Same stage game repeats | Discounting and history dependence |
| Potential game | Unilateral deviations align with a potential function | Potential existence must be shown |
| Stackelberg game | Leader commits before followers respond | Commitment power and tie-breaking |
| Coalition/cooperative game | Coalitions receive values | Transferable utility, core existence, blocking coalitions |
| Empirical game | Payoffs are estimated over learned policies | Sampling noise and policy-pool coverage |

## Key Axes

| Axis | Choices | Consequence |
|------|---------|-------------|
| Information | perfect, imperfect, partial observation, private state, public state | Determines whether CFR, belief methods, or decentralized policies fit |
| Payoff | zero-sum, general-sum, cooperative, mixed-motive, transferable utility | Determines equilibrium concept, metric, and baselines |
| Action/policy space | finite actions, behavior strategies, neural policies, policy pools | Determines exact solver vs approximate oracle design |
| Time | one-shot, finite horizon, discounted infinite horizon, average reward | Determines value definition and convergence claim |

## Solution Concepts

| Concept | Appropriate setting | Required validation |
|---------|---------------------|---------------------|
| Nash equilibrium | Unilateral strategic stability | Best-response gain, exploitability, NashConv, or exact solver proof |
| Correlated equilibrium | Mediated recommendations | CE constraints or regret-to-CE argument |
| Coarse correlated equilibrium | No pre-signal deviation incentive | External regret or CCE constraint check |
| Stackelberg equilibrium | Leader-follower commitment | Follower best response and tie-breaking convention |
| No-regret outcome | Learning dynamics claim | Regret curve and valid mapping to CE/CCE/NE when applicable |
| Shapley value | Attribution or marginal contribution | Coalition value definition and approximation error |
| Core | Coalition stability | Core constraints, emptiness check, or relaxation |
| Alpha-Rank | Population ranking with cycles | Empirical payoff table and sensitivity analysis |

## Method Selection

| Method | Use for | Prerequisites |
|--------|---------|---------------|
| Minimax linear program | Small zero-sum matrix games | Correct payoff convention |
| Support enumeration | Small general-sum matrix games | Manageable support sizes |
| Lemke-Howson | Two-player general-sum matrix games | Degeneracy handling |
| CFR/CFR+ | Extensive-form imperfect-information games | Information sets and perfect recall |
| MCCFR/Deep CFR | Large extensive-form games | Sampling/function approximation validation |
| Fictitious play | Learning dynamics or simple iterative baseline | Convergence only in specific game classes |
| Self-play | Improvement against historical policies | Opponent sampling and forgetting control |
| PSRO | Large policy spaces | Meta-game solver, oracle, payoff-estimation protocol |
| Value decomposition MARL | Cooperative CTDE tasks | Joint reward and decentralized execution assumptions |
| Actor-critic MARL | Continuous/mixed MARL tasks | Centralized critic inputs and execution constraints |
| Coalition optimization | Credit allocation or coalition rationality | Characteristic function and coalition sampling scheme |

## Metric Selection

| Metric | Measures | Use when | Do not use as |
|--------|----------|----------|---------------|
| Exploitability | Distance from zero-sum equilibrium via best response | Zero-sum or clearly defined two-player settings | General performance metric without BR definition |
| NashConv | Sum of unilateral improvement incentives | Multi-player empirical games | Substitute for reward curves |
| Best-response value | Vulnerability to a response policy | Solver/oracle evaluation | Proof of equilibrium if oracle is weak |
| Regret | Learning deviation incentive | No-regret or online learning claims | Final policy quality without mapping |
| Alpha-Rank | Population ranking under evolutionary dynamics | Cyclic/nontransitive policy sets | Equilibrium proof |
| ELO/TrueSkill | Pairwise competitive rating | Tournament summaries | Stability evidence |
| Win rate | Success against chosen opponents | Benchmark reporting | Equilibrium evidence |
| Average return | Task performance | RL learning curves | Strategic robustness evidence |
| Core violation | Coalition blocking incentive | Coalition stability claims | Attribution metric |
| Shapley error | Marginal-contribution attribution error | Credit assignment claims | Coalition stability evidence |

## Red Flags

- Nash equilibrium claim with only win rate or average return.
- CFR language without information sets and perfect recall.
- PSRO without meta-game solver or oracle-quality discussion.
- Game-theoretic MARL claim without solution concept or stability metric.
- Shapley values presented as core stability.
- Self-play evaluated only against the latest policy.
