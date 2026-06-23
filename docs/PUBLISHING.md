# Publishing Guide

Publish this work as a small, versioned skill package with bilingual repository documentation.

## Public Repository Shape

Keep the repository shallow and copy-friendly:

```text
game-research-methodologist/
README.md
README.zh-CN.md
CHANGELOG.md
.gitignore
docs/
```

The skill folder must remain directly copyable into an agent runtime. Keep release notes, publishing notes, and human-facing bilingual docs at repository level.

## Recommended Online Path

1. Use the public GitHub repository `jimengda98/game-research-skill`: https://github.com/jimengda98/game-research-skill.
2. Initialize local git if needed, add remote `origin`, then push the repository contents as-is.
3. Add a license after choosing the reuse policy:
   - MIT or Apache-2.0 for broad reuse as an agent/software package.
   - CC-BY-4.0 if treating the repository mainly as research documentation.
4. Add repository topics: `game-theory`, `multi-agent-learning`, `marl`, `psro`, `equilibrium`, `codex-skill`, `ai-agents`.
5. Publish `v0.1.0` through GitHub Releases after validation passes.
6. Add `CITATION.cff` only after author name, citation title, versioning policy, and optional DOI policy are decided.

## Documentation Site

Start with the README pair as the public landing page. Add GitHub Pages only when the docs need navigation beyond README and `/docs` files.

If a Pages site is added later:

- Keep `README.md` and `README.zh-CN.md` as the canonical landing documents.
- Publish from `/docs` or a dedicated site branch only after checking current GitHub Pages docs.
- Do not make the Pages site required for installing or copying the skill.

## Bilingual Documentation Contract

- Every public human-facing doc should have an English file and a `zh-CN` counterpart when it contains durable guidance.
- Update paired docs in the same change.
- Keep technical terms stable across languages: Nash equilibrium, exploitability, NashConv, PSRO, CFR, Shapley value, core.
- English docs can be more distribution-oriented; Chinese docs can be more usage-oriented, but the factual content should match.

## Public Quality Checklist

Before release:

- `SKILL.md` passes the skill validator.
- `agents/openai.yaml` matches the current name and purpose.
- No personal local paths, private project names, generated caches, or legacy source metadata remain.
- README pair explains use cases, structure, installation, maintenance, license status, and release notes.
- `docs/ITERATION.md` and `docs/ITERATION.zh-CN.md` exist and describe update workflow.
- `papers-and-code.md` marks paper and repository facts as seeds requiring primary-source verification.
- Online links are checked against official docs or official repositories.
- The skill can be copied as a single folder without relying on repository-level docs.

## Release Notes Template

```text
vX.Y.Z
- Added: ...
- Changed: ...
- Updated references: ...
- Validation: quick_validate.py passed
- Forward checks: paper review; experiment design; literature/code lookup
- Known limitations: ...
```

## Publication Boundaries

Do not publish the repository as a solver library unless scripts, tests, and reproducible examples are added later. The current package is a research-methodology skill: routing rules, review checks, source anchors, and output contracts.


## Initial Push Commands

Run from the repository root after choosing whether to add a license:

```powershell
git init
git branch -M main
git add .
git commit -m "Initial game research skill release"
git remote add origin https://github.com/jimengda98/game-research-skill.git
git push -u origin main
```

If the remote already contains files, inspect and reconcile them before pushing.

