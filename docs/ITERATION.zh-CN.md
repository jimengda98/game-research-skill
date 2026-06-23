# 迭代指南

当需要根据新研究、新代码库、发布渠道变化或用户反馈更新本 skill 时，使用这份指南。

## 原则

- 让 skill 对 AI Agent 可执行，而不只是对人类可读。
- 优先使用操作规则、表格和输出契约，少写泛泛解释。
- `SKILL.md` 保持短小；细节放入 `references/` 或仓库级 `docs/`。
- 英文和中文公开文档同步更新。
- 对不稳定事实，在发布前从 primary sources 验证。

## 更新流程

1. 明确更新目标：研究工作流、博弈分类、论文/代码索引、审稿写作、发布流程或双语文档。
2. 编辑前先阅读当前文件。
3. 更新论文、仓库、API、安装命令、benchmark 支持、版本或 venue 信息时，先查 primary sources。
4. 只修改最相关的文件。
5. 删除过时或重复的指导。
6. 运行校验和 forward checks。
7. 如果变化面向公开发布，更新 release notes。

## 自主调研检查表

Agent 自行调研并更新文档时，按以下规则执行：

- 优先使用官方论文、arXiv 页面、项目文档和维护中的官方仓库。
- 记录官方 URL，以及该来源为什么应该进入 skill。
- 不写未经验证的仓库活跃度、当前 API、安装命令、论文 venue 或版本状态。
- 优先维护小型种子索引，而不是长篇 bibliography。
- 对引用、安装或复现实验前必须验证的事实显式标注。

## Forward Checks

重要更新后运行三类检查：

1. 论文审查：“Review this MARL paper claim that the learned policy is Nash.”
2. 实验设计：“Design experiments for a PSRO/self-play method in a general-sum game.”
3. 文献/代码查找：“Find typical papers and codebases for exploitability evaluation in games.”

期望行为：

- 回答能分类 game model 和 target concept。
- 回答能分开 assumptions、claims、metrics 和 feasibility。
- 只加载相关 references。
- 不出现私人路径或本地项目路径。
- 对论文和代码事实提示 primary-source verification（原始来源验证）。

## 校验命令

```powershell
python C:\Users\Tourist\.codex\skills\.system\skill-creator\scripts\quick_validate.py C:\Users\Tourist\Documents\game_skill\game-research-methodologist
python C:\Users\Tourist\.codex\skills\.system\skill-creator\scripts\generate_openai_yaml.py C:\Users\Tourist\Documents\game_skill\game-research-methodologist --interface display_name="Game Research Methodologist" --interface short_description="Research methods for games and multi-agent learning" --interface default_prompt='Use $game-research-methodologist to evaluate a game-theoretic claim, design an experiment, or find canonical papers and code.'
```

在其他机器上校验时，按实际路径调整命令。

## 版本策略

- Patch：措辞清理、链接刷新、双语同步、小修正。
- Minor：新增 reference section、workflow、topic area 或发布指导。
- Major：skill 改名、输出契约变化、移除主要 workflow 或结构不兼容变化。

