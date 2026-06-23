# Iteration Guide

Use this guide when updating the skill after new research, new codebases, changed publication targets, or user feedback.

## Principles

- Keep the skill useful to AI agents, not just readable to humans.
- Prefer operational rules, tables, and output contracts over broad explanation.
- Keep `SKILL.md` short. Move detailed material into `references/` or repository-level docs.
- Update English and Chinese public docs together.
- Verify unstable facts from primary sources before publishing them.

## Update Workflow

1. Define the update target: research workflow, taxonomy, papers/code, review writing, publication, or bilingual docs.
2. Inspect the current file before editing.
3. Research from primary sources when updating papers, repositories, APIs, install commands, benchmark support, versions, or venues.
4. Edit the smallest relevant file.
5. Remove stale or duplicated guidance.
6. Run validation and forward checks.
7. Update release notes if the change is public-facing.

## Research Refresh Checklist

Use this when the agent independently researches updates:

- Start from official papers, arXiv pages, project documentation, and maintained repositories.
- Record the official URL and the reason the source belongs in the skill.
- Do not add unverified claims about repository activity, current APIs, package install commands, or paper venue status.
- Prefer a small seed index over a long bibliography.
- Mark facts that users must verify before citation, installation, or reproduction.

## Forward Checks

Run these after meaningful changes:

1. Paper review: “Review this MARL paper claim that the learned policy is Nash.”
2. Experiment design: “Design experiments for a PSRO/self-play method in a general-sum game.”
3. Literature/code lookup: “Find typical papers and codebases for exploitability evaluation in games.”

Expected behavior:

- The answer classifies the game and target concept.
- The answer separates assumptions, claims, metrics, and feasibility.
- The answer loads only relevant references.
- The answer avoids private/local paths.
- The answer flags primary-source verification for paper and code facts.

## Validation Commands

```powershell
python C:\Users\Tourist\.codex\skills\.system\skill-creator\scripts\quick_validate.py C:\Users\Tourist\Documents\game_skill\game-research-methodologist
python C:\Users\Tourist\.codex\skills\.system\skill-creator\scripts\generate_openai_yaml.py C:\Users\Tourist\Documents\game_skill\game-research-methodologist --interface display_name="Game Research Methodologist" --interface short_description="Research methods for games and multi-agent learning" --interface default_prompt='Use $game-research-methodologist to evaluate a game-theoretic claim, design an experiment, or find canonical papers and code.'
```

Adjust paths when validating outside this local machine.

## Versioning

- Patch: wording cleanup, link refresh, bilingual sync, minor correction.
- Minor: new reference section, workflow, topic area, or publication guidance.
- Major: skill rename, output contract change, removed workflow, or incompatible structure change.
