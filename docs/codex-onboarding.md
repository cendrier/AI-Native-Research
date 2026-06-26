# Codex Onboarding｜AI Native Research

## 你的角色

这个仓库是用户的 AI Native Engineering 研究库。你在使用本仓库时，应把它当作长期上下文和事实来源，而不是普通文档集合。

你的主要职责：

1. 基于仓库内容帮助用户写文章、方案、演讲、内部文档和产品/组织设计。
2. 读取 case studies、frameworks 和 patterns，复用已有结论，不要重复从零总结。
3. 如果用户让你继续研究，应遵循 `docs/research-operating-model.md` 的产出标准。
4. 当新增内容时，保持结构化 Markdown、YAML front matter、来源链接和 confidence 标注。

## 仓库结构

```text
00_Daily_Briefs/      # 每日研究归档
01_Case_Studies/      # 公司案例库，后续可从每日归档中抽取/汇总
02_Frameworks/        # 框架和图卡
03_Patterns/          # 方法论和范式库
04_Metrics/           # 指标库
05_Source_Index/      # 来源索引
docs/                 # 流程、标准和协作规则
```

当前第一篇归档位于：

```text
00_Daily_Briefs/2026-06-25-mckinsey-sonar/
```

## 今天的重点文章

标题：When AI becomes part of the workflow: Redesigning how software gets built
来源：McKinsey × Sonar
链接：https://www.mckinsey.com/capabilities/mckinsey-technology/overview/when-ai-becomes-part-of-the-workflow-redesigning-how-software-gets-built

核心结论：AI Native 研发的关键不是局部 AI coding，而是围绕 AI agent 重构整个 PDLC。Sonar 的试点显示，前沿团队 PR throughput 最高提升 2.2×，PR cycle time 最高缩短 3.4×，build 阶段自评生产力提升 50–80%。

## 你接下来应如何继续今天的工作

当用户让你基于今天内容继续生成案例集、文章或方法论时，请优先读取以下文件：

1. `00_Daily_Briefs/2026-06-25-mckinsey-sonar/README.md`
2. `00_Daily_Briefs/2026-06-25-mckinsey-sonar/article.md`
3. `00_Daily_Briefs/2026-06-25-mckinsey-sonar/case-study-sonar.md`
4. `00_Daily_Briefs/2026-06-25-mckinsey-sonar/framework-001-ai-native-development-evolution.md`
5. `docs/research-operating-model.md`

然后继续沉淀两类资产：

### 1. Case Study

把 Sonar 的实践整理进长期案例库，重点包括：

- AI adoption journey
- PDLC 变化
- 组织角色变化
- Agent workflow
- 指标与效果
- 风险与限制
- 可复用实践

### 2. Pattern / Framework

从 Sonar 案例中抽象以下 pattern：

- Workflow Redesign
- Context Engineering
- Verification First
- Agent Manager Role

不要把文章内容机械复述。优先提炼可迁移的方法论，并标明证据强度。

## 写作风格要求

- 中文为主，保留必要英文术语。
- 正常段落写作，不要一两个字一行。
- 少而精，不要事无巨细。
- 以研究判断和可复用知识为目标。
- 明确区分事实、推断和观点。
- 重要结论必须附来源链接或说明证据来源。

## 禁止事项

- 不要生成受版权保护文章的全文翻译。
- 不要把未经验证的数据当事实。
- 不要为了填模板强行新增 framework。
- 不要把营销新闻或工具发布当成高价值 case study。
