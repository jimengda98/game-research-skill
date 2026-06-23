# Papers and Code Seed Index

Use this as a starting index, not a complete bibliography. Verify exact titles, authors, years, venues, repository health, APIs, and installation instructions from primary sources before citation or use.

## Use Pattern

1. Identify the subtopic: equilibrium computation, imperfect-information games, MARL, self-play, empirical games, coalition games, benchmarks, or tooling.
2. Select 3-6 seed papers or codebases.
3. Verify current facts from papers, arXiv pages, official docs, or repository READMEs.
4. Recommend a starting path instead of a citation dump.

## Foundational Game Theory

| Topic | Seeds | Why it matters |
|-------|-------|----------------|
| Nash equilibrium | Nash non-cooperative games | Unilateral strategic stability |
| Correlated equilibrium | Aumann correlated equilibrium | Mediated recommendations and regret links |
| Cooperative games | Shapley value; core and balanced games | Credit allocation and coalition stability |
| Repeated games | Folk theorem literature | Long-run incentives and history dependence |
| Mechanism design | VCG, Myerson auction theory | Incentives and strategic reporting |

## Equilibrium Computation

| Topic | Seeds | Code/tool anchors |
|-------|-------|-------------------|
| Matrix games | Support enumeration, Lemke-Howson, minimax LP | Nashpy: https://github.com/drvinceknight/Nashpy |
| General finite games | Gambit documentation and related papers | Gambit: https://gambitproject.org/ |
| Extensive-form games | Sequence form, CFR, MCCFR | OpenSpiel: https://github.com/google-deepmind/open_spiel |
| Learning dynamics | Fictitious play, replicator dynamics, regret matching | Nashpy and OpenSpiel examples |

## CFR, PSRO, and Empirical Games

| Topic | Seeds | Code/tool anchors |
|-------|-------|-------------------|
| CFR | Counterfactual regret minimization; CFR+; MCCFR | OpenSpiel CFR implementations |
| Neural game solving | Deep CFR, NFSP, ReBeL-style work | OpenSpiel examples and paper-specific repos |
| PSRO | Policy Space Response Oracles; Double Oracle; empirical game-theoretic analysis | OpenSpiel PSRO modules |
| Population ranking | Alpha-Rank and evolutionary dynamics | OpenSpiel evaluation tools |
| Exploitability/NashConv | Best-response and empirical-game evaluation papers | OpenSpiel and custom BR solvers |

## MARL

| Topic | Seeds | Code/tool anchors |
|-------|-------|-------------------|
| Value decomposition | VDN, QMIX, QTRAN, QPLEX, WQMIX | PyMARL: https://github.com/oxwhirl/pymarl; EPyMARL: https://github.com/uoe-agents/epymarl |
| Actor-critic MARL | MADDPG, COMA, MAPPO, HAPPO/HATRPO | EPyMARL; MARLlib: https://github.com/Replicable-MARL/MARLlib |
| Self-play MARL | Fictitious self-play, prioritized fictitious self-play, neural best response | OpenSpiel and environment-specific repos |
| Offline MARL | Conservative/offline MARL methods | Verify maintained repos per paper |
| Benchmarks | SMAC, MPE/PettingZoo, Hanabi, matrix games | SMAC: https://github.com/oxwhirl/smac; PettingZoo: https://github.com/Farama-Foundation/PettingZoo |

## Tool Defaults

| Tool | Use for | Notes |
|------|---------|-------|
| OpenSpiel | General game research, extensive-form games, CFR/PSRO, exploitability, Alpha-Rank | Default anchor for game-theoretic validation |
| PettingZoo | Multi-agent RL environment API and reference environments | Good for environment wrapping and interoperability |
| SMAC | Cooperative partially observable StarCraft micromanagement | Verify StarCraft II dependency requirements |
| PyMARL | Historical SMAC baseline framework | Useful baseline reference; check maintenance state |
| EPyMARL | Extended PyMARL with more algorithms/environments | Often a better modern starting point than original PyMARL |
| MARLlib | Broader MARL training framework | Verify dependency stack and reproducibility |
| Nashpy | Two-player matrix game computation and learning dynamics | Good for small exact sanity checks |
| Gambit | General finite-game analysis and equilibrium computation | Good for exact small-game analysis |

## Starting Recommendations

- Exact game-theoretic validation: OpenSpiel plus Nashpy or Gambit for small games.
- MARL benchmark implementation: PettingZoo for API clarity; EPyMARL or MARLlib for algorithm baselines.
- PSRO: OpenSpiel first, then decide whether a custom oracle is needed.
- Exploitability claims: small exact game and trusted best response before neural-scale experiments.
- Paper literature: use this file for seed selection, then verify citations from primary sources.
