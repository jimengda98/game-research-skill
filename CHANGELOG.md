# Changelog

## Unreleased

- Added model and algorithm selection reference for mapping research situations to game models, solver families, learning algorithms, validation metrics, and fallback baselines.
- Updated the skill route and README file tree to expose model/algorithm recommendation as a first-class workflow.

## v0.1.0 - Initial Public Release

- Added `game-research-methodologist` skill package.
- Added research workflow contracts for diagnostics, experiment design, implementation handoff, paper review, literature/code lookup, and publication maintenance.
- Added game taxonomy, solution concept, method selection, and metric selection references.
- Added curated seed index for canonical papers, benchmarks, and codebases.
- Added review and writing guidance for game-theoretic research claims.
- Added bilingual README and publication/iteration documentation.

Validation:

- `quick_validate.py` passes for `game-research-methodologist`.
- Static checks found no private local paths or legacy source metadata.

Known limitations:

- No solver code or experiment scripts are included.
- Paper metadata, repository status, APIs, and installation commands must be verified from primary sources before citation or use.
