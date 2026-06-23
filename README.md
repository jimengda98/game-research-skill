# Game Research Skill

[中文说明](README.zh-CN.md)

A bilingual Codex-style skill package for game-theoretic research work. It helps AI agents classify games, audit equilibrium claims, design game/MARL/self-play/PSRO experiments, select validation metrics, review papers, and find canonical papers or codebases.

Repository: `jimengda98/game-research-skill`

Packaged skill: `game-research-methodologist`

## What Is Included

```text
game-research-methodologist/
  SKILL.md
  agents/openai.yaml
  references/
    research-workflows.md
    game-taxonomy-and-methods.md
    papers-and-code.md
    review-and-writing.md
    maintenance-and-publishing.md
docs/
  PUBLISHING.md
  PUBLISHING.zh-CN.md
  ITERATION.md
  ITERATION.zh-CN.md
CHANGELOG.md
README.md
README.zh-CN.md
```

The skill folder stays lean: no README, no scripts, no assets, and no personal local paths. Repository-level documents explain publication and maintenance.

## Use Cases

- Review a claim that a learned policy is a Nash equilibrium.
- Design an experiment for PSRO, self-play, or empirical game analysis.
- Choose between exploitability, NashConv, regret, Alpha-Rank, win rate, and return.
- Plan implementation checks for matrix games, extensive-form games, or MARL baselines.
- Find seed papers and codebases for game theory and multi-agent learning.
- Repair paper framing when game-theoretic claims are vague or under-tested.
- Maintain and publish the skill with bilingual documentation.

## Installation

Copy `game-research-methodologist/` into the skill directory used by your agent runtime, or point the runtime directly at this folder if path-based skill loading is supported.

For Codex-style layouts, the folder itself is the package. The required entry point is `game-research-methodologist/SKILL.md`.

## Maintenance and Publication

Use [docs/ITERATION.md](docs/ITERATION.md) for the update workflow. Use [docs/PUBLISHING.md](docs/PUBLISHING.md) before publishing the repository online. See [CHANGELOG.md](CHANGELOG.md) for release notes.

## License

Released under the MIT License. See [LICENSE](LICENSE).

## Status

This is a research-methodology skill, not a solver library. It provides routing, checks, reference anchors, and output contracts. Agents should still verify paper metadata, repository status, APIs, and installation commands from primary sources before citation or use.

