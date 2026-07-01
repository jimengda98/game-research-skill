# Game Research Skill

[English README](README.md)

面向博弈研究的 Codex skill：用于模型选择、算法选择、实验设计和论文审查。

仓库：`jimengda98/game-research-skill`

内含 skill：`game-research-methodologist`

## 包含内容

```text
game-research-methodologist/
  SKILL.md
  agents/openai.yaml
  references/
    research-workflows.md
    model-algorithm-selection.md
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

skill 目录保持精简：不放 README、不放脚本、不放 assets、不放个人本地路径。公开发布和维护流程放在仓库级文档中。

## 适用场景

- 审查“学习策略是 Nash equilibrium”这类声明是否成立。
- 为 PSRO、self-play 或 empirical game analysis 设计实验。
- 在 exploitability、NashConv、regret、Alpha-Rank、win rate、return 之间选择合适指标。
- 为矩阵博弈、扩展式博弈或 MARL baseline 规划实现验证。
- 查找博弈论和多智能体学习的种子论文与代码库。
- 修复论文中过于宽泛或缺少验证的博弈论叙事。

## 安装

把 `game-research-methodologist/` 复制到你的 Agent runtime 使用的 skills 目录；如果 runtime 支持按路径加载 skill，也可以直接指向这个目录。

对于 Codex 风格布局，这个目录本身就是 skill 包，必需入口是 `game-research-methodologist/SKILL.md`。

## 维护与发布

迭代流程见 [docs/ITERATION.zh-CN.md](docs/ITERATION.zh-CN.md)。公开发布前按 [docs/PUBLISHING.zh-CN.md](docs/PUBLISHING.zh-CN.md) 检查。发布记录见 [CHANGELOG.md](CHANGELOG.md)。

## License

本项目使用 MIT License 发布。详见 [LICENSE](LICENSE)。

## 状态

这是一个研究方法论 skill，不是求解器代码库。它提供任务路由、审查清单、参考入口和输出格式。Agent 在引用论文、安装代码库或复现实验前，仍应从 primary sources 验证论文信息、仓库状态、API 和安装命令。

