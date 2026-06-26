---
title: "Case Study 001: Sonar"
date: 2026-06-25
company: Sonar
source_title: "When AI becomes part of the workflow: Redesigning how software gets built"
source_url: "https://www.mckinsey.com/capabilities/mckinsey-technology/overview/when-ai-becomes-part-of-the-workflow-redesigning-how-software-gets-built"
topics:
  - AI Native PDLC
  - Agentic Development
  - Workflow Redesign
  - Verification
metrics:
  - "PR throughput: up to 2.2x"
  - "PR cycle time: up to 3.4x reduction"
  - "Self-reported build productivity: 50-80% gains"
confidence: "High"
---

# Case Study 001: Sonar

## 公司背景

Sonar 是代码质量、代码安全和代码治理平台，文章中提到其平台被超过 700 万开发者及其 AI agents 使用，并且每天分析超过 7500 亿行代码。这个背景很关键：Sonar 本身就是围绕代码理解、质量验证和技术债治理构建的公司，因此它天然具备进入 AI Native 研发的基础。

## 为什么开始做 AI Native PDLC

Sonar 与 McKinsey 的共同问题不是“如何让工程师更多使用 AI”，而是“如何让 AI 真正进入软件研发的端到端工作流”。传统 AI coding 工具主要提升局部任务效率，但难以改变整个组织的交付能力。Sonar 的目标是把 agent 嵌入 PDLC，让 AI 参与从 research、ideation、backlog、development 到 testing 和 remediation 的多个环节。

## 演进路径

| 阶段 | 重点 | 说明 |
|---|---|---|
| 基础阶段 | AI 工具采用 | 团队已有 coding assistant 等 AI 工具基础 |
| 标准化阶段 | 结构化输入 | 标准化 epic、job to be done、pain point、definition of finished |
| 工作流阶段 | Agent 嵌入 PDLC | Agent 参与 backlog、unit test、code production、quality remediation |
| 编排阶段 | Agent-to-agent workflow | 从 bug report 到 Jira ticket、需求澄清、draft PR 的多 agent 流程 |

## 组织变化

Sonar 的变化不是单点工具上线，而是角色边界变化。工程师逐渐承担 agent manager 的职责：指导 agent、检查输出、补充上下文、优化 workflow。产品经理和设计师也能借助 AI 更快地完成研究、定义和原型工作。这种变化使团队从“人执行任务”转向“人设计和监督人机协作系统”。

## Workflow 变化

Sonar 的核心实践可以简化为：

```text
Structured Inputs → Agent Execution → Continuous Verification → Feedback Loops
```

其中最关键的是 structured inputs。团队把过去依赖个人经验和上下文记忆的内容转化为模板化、可检查、可复用的工件。agent 在此基础上生成 backlog、代码、测试或修复建议，验证和反馈再反过来改进输入与 agent 行为。

## 关键指标

| 指标 | 结果 | 解读 |
|---|---:|---|
| Pull request throughput | 最高提升 2.2× | 交付吞吐改善 |
| Pull request cycle time | 最高缩短 3.4× | 从开发到合并的流动效率改善 |
| Build 阶段自评生产力 | 提升 50–80% | 个人感知效率明显提升 |

## 成功经验

1. **先整理上下文，再上 agent。** Agent 不是魔法，输入质量决定输出质量。
2. **把 AI 当作工作流参与者，而不是 IDE 插件。** 真正的收益来自跨环节协同。
3. **人仍然是质量和判断的负责人。** 生成速度提升后，验证能力必须同步提升。
4. **通过分享机制扩散经验。** AI experimentation hour、show and tell 等机制帮助团队减少孤岛。

## 风险与限制

这些结果来自前沿团队试点，不应直接推断到所有组织。对于技术债严重、测试薄弱、需求管理混乱的团队，AI agent 可能放大混乱而不是提升效率。此外，PR 指标并不等价于业务价值，需要继续观察质量、安全、用户反馈和长期维护成本。

## 可复用实践

- 为 epic、backlog、definition of finished 建立统一模板。
- 让 agent 主动识别缺失上下文，而不是默默生成低质量输出。
- 将 code quality、security、test coverage 和 remediation 放入 agent workflow。
- 建立 agent 使用经验分享机制，避免每个团队重复摸索。
- 用 PR throughput、cycle time、review burden、defect rate 等组合指标衡量效果。

## 支撑的 Patterns

- Workflow Redesign
- Context Engineering
- Verification First
- Agent Manager Role
