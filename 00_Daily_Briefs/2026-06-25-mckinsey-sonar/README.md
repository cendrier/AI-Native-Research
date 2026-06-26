---
title: "AI Native Research Brief #001"
date: 2026-06-25
source_title: "When AI becomes part of the workflow: Redesigning how software gets built"
source_url: "https://www.mckinsey.com/capabilities/mckinsey-technology/overview/when-ai-becomes-part-of-the-workflow-redesigning-how-software-gets-built"
company:
  - Sonar
  - McKinsey
topics:
  - AI Native Engineering
  - PDLC
  - Workflow Redesign
  - Verification
  - Agentic Development
importance: "★★★★★"
status: "archived"
---

# AI Native Research Brief #001

## 一句话总结

这篇 McKinsey × Sonar 的案例说明，AI Native 研发的关键不只是让工程师用 AI 写代码，而是把整个产品研发流程（PDLC）围绕 AI agent 重新设计：人负责目标、上下文、判断和验证，agent 负责更大比例的执行、生成和反馈循环。

## 为什么值得读

这篇文章符合本研究库当前最重要的筛选标准：它不是泛泛讨论 AI 提效，而是给出了一个已经落地的企业案例，并且覆盖了流程、工具和人的角色变化。Sonar 与 McKinsey 的试点显示，前沿团队在 pull request throughput、pull request cycle time 和自评生产力上都有显著改善。

## 关键数据

| 指标 | 结果 |
|---|---:|
| Pull request throughput | 最高提升 2.2× |
| Pull request cycle time | 最高缩短 3.4× |
| Build 阶段自评生产力 | 提升 50–80% |

## 3 个关键观点

1. **Workflow 比 Tool 更重要。** 大多数团队还停留在把 AI 加到局部任务中的阶段，例如写代码、补全、debug。Sonar 的案例强调，需要重新设计 PDLC 中的输入、交接、模板、验证和反馈循环。
2. **Context 是 AI Native 的基础设施。** Sonar 标准化 epic、backlog、definition of finished 等关键输入，让 agent 能基于结构化上下文工作，而不是依赖人的隐性知识。
3. **Verification 会成为新的瓶颈。** 当 agent 增加代码和研发产物的生成速度后，组织必须建立更强的质量、安全、正确性和治理机制，否则速度会转化成返工和技术债。

## 今日产物

- `article.md`：中文深度解读
- `case-study-sonar.md`：Sonar 案例条目
- `framework-001-ai-native-development-evolution.md`：四阶段演进框架
- `assets/framework-001-ai-native-development-evolution.png`：四阶段视觉卡片
- `docs/research-operating-model.md`：本研究库的流程、模式与产出标准
- `docs/codex-onboarding.md`：给 Codex 的仓库说明与后续工作指令

## 推荐阅读对象

适合 CTO、研发负责人、工程效能负责人、平台工程团队、AI Coding 工具推广负责人，以及正在设计 AI Native 研发流程的团队。

## Decision

**进入长期知识库：★★★★★ 必须保留。**

理由：该案例同时具备头部咨询机构框架、企业落地实践、量化指标、流程细节和可抽象方法论，适合作为 AI Native Engineering Playbook 的第一篇基准案例。
