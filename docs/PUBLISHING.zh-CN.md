# 发布指南

将本项目发布为一个小型、可版本化的 skill 包，并配套中英文仓库文档。

## 公开仓库结构

仓库保持扁平，方便复制使用：

```text
game-research-methodologist/
README.md
README.zh-CN.md
CHANGELOG.md
.gitignore
docs/
```

skill 目录必须能直接复制到 Agent runtime 中。release notes、发布说明和面向人的双语文档放在仓库级目录。

## 推荐在线发布路径

1. 使用公开 GitHub 仓库 `jimengda98/game-research-skill`：https://github.com/jimengda98/game-research-skill。
2. 如本地尚未初始化 git，先初始化并添加 `origin`，再原样推送当前仓库内容。
3. 确定复用策略后添加 license：
   - 如果作为 Agent/software package 广泛复用，选 MIT 或 Apache-2.0。
   - 如果主要作为研究文档复用，选 CC-BY-4.0。
4. 添加 repository topics：`game-theory`、`multi-agent-learning`、`marl`、`psro`、`equilibrium`、`codex-skill`、`ai-agents`。
5. 校验通过后，用 GitHub Releases 发布 `v0.1.0`。
6. 只有在作者、引用标题、版本策略和可选 DOI 策略确定后，再添加 `CITATION.cff`。

## 文档站

初版让 README 中英文对作为公开入口即可。只有当文档规模超过 README 和 `/docs` 文件时，再考虑 GitHub Pages。

如果后续添加 Pages：

- `README.md` 和 `README.zh-CN.md` 仍作为 canonical landing documents。
- 从 `/docs` 或专门分支发布前，先检查当前 GitHub Pages 官方文档。
- 不要让 Pages 成为安装或复制 skill 的必要条件。

## 双语文档约定

- 面向公开用户、且包含长期指导的文档，应同时提供英文文件和 `zh-CN` 对应文件。
- 修改成对文档时，同一轮更新两个文件。
- 技术术语保持稳定：Nash equilibrium、exploitability、NashConv、PSRO、CFR、Shapley value、core。
- 英文文档可以更偏分发和发布；中文文档可以更偏使用说明，但事实内容应一致。

## 公开前检查

- `SKILL.md` 通过 skill validator。
- `agents/openai.yaml` 与当前名称和定位一致。
- 不含个人本地路径、私有项目名、生成缓存或旧来源元数据。
- README 中英文对说明用途、结构、安装、维护、license 状态和发布记录。
- `docs/ITERATION.md` 与 `docs/ITERATION.zh-CN.md` 存在，并说明更新流程。
- `papers-and-code.md` 明确论文和仓库信息只是种子入口，需要 primary-source verification（原始来源验证）。
- 在线链接已对照官方文档或官方仓库检查。
- skill 可以作为单独目录复制使用，不依赖仓库级文档。

## Release Notes 模板

```text
vX.Y.Z
- Added: ...
- Changed: ...
- Updated references: ...
- Validation: quick_validate.py passed
- Forward checks: paper review; experiment design; literature/code lookup
- Known limitations: ...
```

## 发布边界

除非后续加入脚本、测试和可复现实例，不要把本仓库发布成 solver library。当前包是研究方法论 skill：任务路由、审查清单、来源入口和输出契约。



## 首次推送命令

选择是否添加 license 后，在仓库根目录执行：

```powershell
git init
git branch -M main
git add .
git commit -m "Initial game research skill release"
git remote add origin https://github.com/jimengda98/game-research-skill.git
git push -u origin main
```

如果远程仓库里已经有文件，先检查并合并差异，不要直接覆盖。

