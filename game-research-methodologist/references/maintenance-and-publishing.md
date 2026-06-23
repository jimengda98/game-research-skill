# Maintenance and Publishing

Use for tasks that update, publish, or release this skill.

## Update Rules

- Keep `SKILL.md` as the short operating protocol.
- Put detailed procedures in `references/` or repository-level `docs/`.
- Remove stale links, dead repositories, private paths, and unverifiable claims.
- Prefer seed references over exhaustive bibliographies.
- Keep wording direct: rules, checklists, tables, and output contracts. Avoid long explanations about why the skill exists.

## Research Refresh Workflow

1. Define the update target: papers, codebases, metrics, workflows, publication docs, or bilingual docs.
2. Search primary sources first: official papers, arXiv pages, project docs, maintained repositories, release notes.
3. Record only durable facts: project purpose, official URL, method family, validation use case, known caveat.
4. Mark unstable facts for verification: install commands, APIs, maintenance status, current benchmark support, paper venue, version numbers.
5. Update the smallest relevant file.
6. Validate `SKILL.md` with the skill validator.
7. Run three forward checks: paper review, experiment design, literature/code lookup.

## Bilingual Documentation Policy

- Keep skill runtime references in English unless a Chinese file is explicitly needed.
- Keep repository-level human docs bilingual: `README.md` with `README.zh-CN.md`, and paired files under `docs/`.
- When editing a bilingual pair, update both files in the same change.
- Chinese docs should be faithful, not word-for-word translations; preserve technical terms such as Nash equilibrium, exploitability, NashConv, PSRO, CFR, Shapley value, and core when they are standard.

## Online Publication Checklist

- Repository contains the skill folder, root README pair, and `docs/` pair files.
- Skill folder has no README, scripts, assets, generated caches, private paths, or legacy source metadata.
- `agents/openai.yaml` matches the current skill name and purpose.
- `papers-and-code.md` tells users to verify primary sources before citation, installation, or reproduction.
- Public release has a license decision, version tag, release notes, and optional citation metadata.
- Check current platform docs before changing GitHub Releases, GitHub Pages, package registry, or marketplace publication steps.

## Versioning

Use semantic versioning for public releases:

| Change | Version bump |
|--------|--------------|
| New reference section, new workflow, or new publication docs | minor |
| Corrections, link refresh, wording cleanup, bilingual sync | patch |
| Breaking rename, changed output contract, removed major workflow | major |

## Release Note Template

```text
vX.Y.Z
- Added: ...
- Changed: ...
- Updated references: ...
- Validation: quick_validate.py passed
- Forward checks: paper review; experiment design; literature/code lookup
- Known limitations: ...
```

