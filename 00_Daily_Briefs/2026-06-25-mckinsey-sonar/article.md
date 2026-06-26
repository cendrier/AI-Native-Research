---
title: "When AI becomes part of the workflow｜中文深度解读"
date: 2026-06-25
source_title: "When AI becomes part of the workflow: Redesigning how software gets built"
source_url: "https://www.mckinsey.com/capabilities/mckinsey-technology/overview/when-ai-becomes-part-of-the-workflow-redesigning-how-software-gets-built"
company:
  - Sonar
  - McKinsey
topics:
  - Workflow Redesign
  - PDLC
  - Verification
  - Context Engineering
  - Agentic Development
confidence: "High"
---

# When AI becomes part of the workflow｜中文深度解读

## 1. 核心判断

这篇文章最重要的价值，不在于证明 AI coding 能提升个人效率，而在于提出了一个更系统的判断：AI 的真正价值来自产品研发流程（PDLC）的端到端重构。换句话说，企业如果只是给工程师配一个 AI 编程工具，收益通常会停留在局部任务层面；只有当需求、上下文、开发、测试、验证、反馈和组织角色都围绕 AI 重新设计时，才会出现更大幅度的效率提升。

Sonar 的案例显示，AI Native 研发不是一个工具采购问题，而是一个 operating model 问题。它要求团队重新定义工作如何流动、输入如何结构化、agent 如何参与执行、人如何验证结果，以及组织如何把局部经验扩散成系统能力。

## 2. 背景：为什么局部 AI 使用不够

多数团队今天的 AI 应用仍然是“AI-assisted development”：工程师在现有流程中使用 AI 完成局部任务，例如代码补全、生成单元测试、解释代码、debug 或重构。这个阶段有价值，但上限明显，因为原有流程中的瓶颈没有消失：需求仍然模糊，知识仍然隐性，交接仍然低效，review 和验证仍然依赖人工。

McKinsey 的观点是，AI 价值的主要来源并不是某个环节的局部加速，而是整个系统吞吐的提升。软件研发本质上是一个多角色、多工件、多反馈循环的系统。如果只优化 coding，一旦代码生成变快，瓶颈很快会转移到需求澄清、代码 review、安全验证、测试覆盖、发布质量和知识同步上。

## 3. Sonar 做了什么

Sonar 与 McKinsey 合作，让三个前沿团队重新设计 PDLC，使 AI agent 进入研发流程的多个环节。这个试点不是简单推广某个工具，而是同时改造了 process、tooling 和 people 三个维度。

在流程层面，团队围绕 agent 重新设计工作流、工件和仪式。一个典型变化是标准化关键输入，例如要求每个 epic 明确目标用户、job to be done、痛点和 definition of finished。这样做的目的不是让文档更漂亮，而是把过去依赖人的隐性知识转化为 agent 可执行的结构化上下文。

在工具层面，团队将 agent 扩展到 research、ideation、backlog definition、unit-test generation、code production、quality remediation 等环节。例如，backlog generation agent 会根据标准模板生成条目、发现缺失上下文，并提示团队补齐信息。还有一些 agent-to-agent workflow 能从协作渠道中的 bug report 出发，创建 Jira ticket、澄清需求，并生成 draft pull request。

在人的角色层面，工程师、产品经理和设计师的边界开始变化。工程师不再只是代码生产者，而越来越多承担 context provider、agent manager、reviewer 和 workflow designer 的角色。产品和设计也能更快完成原型与定义工作，参与到更高频的研发反馈循环中。

## 4. 关键结果

试点结束后，Sonar 前沿团队在速度和质量上都看到改善。文章披露的主要指标包括：pull request throughput 最高提升 2.2 倍，pull request cycle time 最高缩短 3.4 倍，build 阶段自评生产力提升 50–80%。这些指标需要谨慎解读，因为文章也说明并非所有改善都能完全归因于试点本身，但整体信号明确：当 AI 被嵌入工作流，而不是孤立地用于写代码时，团队能从相似输入中产生更好的结果。

对我们而言，最有价值的不是数字本身，而是数字背后的机制：更清晰的输入、更少的交接摩擦、更高比例的并行工作、更强的自动化反馈，以及人把注意力转向判断和验证。

## 5. 四阶段演进模型

文章提出了一个非常适合作为长期框架的演进模型：从人工研发，到局部 AI 增强，到 AI Native workflow，再到端到端 agentic workflow。这个模型的重要性在于，它把“是否使用 AI”转化成“工作系统被 AI 重构到什么程度”。

Stage 1 是传统研发。人负责几乎所有环节，AI 没有实质参与。系统瓶颈主要来自人工执行、人工交接和信息损耗。

Stage 2 是 AI 辅助研发。AI 被用于局部任务，例如 coding、testing、debug。这个阶段可以带来 modest productivity gains，但工作流主体仍然不变。

Stage 3 是 AI Native Workflow。团队围绕 agent 重新设计 PDLC，人负责提供上下文、设定目标、验证结果，agent 负责生成、执行和反馈。Sonar 的试点主要属于这个方向。

Stage 4 是 Agentic Organization。人不再逐项协调 agent，而是定义业务目标和约束，由 agent 系统完成端到端协同。人的角色从任务管理者进一步转向系统编排者、意图设定者和结果监督者。

配套图片见：`assets/framework-001-ai-native-development-evolution.png`。

## 6. 可抽象的方法论：Workflow Redesign

这篇文章沉淀出的第一个核心 pattern 是 Workflow Redesign。它的定义是：不要把 AI 简单加入现有流程，而要围绕 AI 重新设计工作如何被定义、拆解、执行、验证和反馈。

这个 pattern 有四个关键组成：Spec First、Context First、Agent Execute、Human Verify。Spec First 解决目标和验收标准的问题；Context First 解决隐性知识外显的问题；Agent Execute 让 AI 承担可自动化的执行任务；Human Verify 保证质量、判断、责任和组织学习不会丢失。

它适合已经有一定 AI 使用基础、代码质量和工程基础较好的团队。如果一个团队的需求管理混乱、代码库技术债严重、测试和验证体系薄弱，直接进入高强度 agentic workflow 反而可能放大问题。

## 7. 我的点评

这篇文章对 AI Native 组织最重要的启发是：模型能力正在变得越来越普及，真正的差异会出现在组织如何为 AI 设计上下文、验证和反馈系统。也就是说，未来领先团队的优势未必来自“用哪个 coding agent”，而来自“组织知识是否结构化”“研发流程是否 agent-ready”“验证系统是否足够自动化”“团队是否能持续学习和复用 agent”。

我认为这篇文章还提示了一个未来角色变化：工程师会从 code producer 逐渐变成 workflow manager、context engineer 和 verification owner。管理者也会从管理人的任务进度，转向设计人和 agent 的协作系统。这个变化不会一夜之间完成，但它已经开始成为头部团队的新竞争维度。

## 8. Key Patterns

| Pattern | 说明 | Confidence |
|---|---|---:|
| Workflow Redesign | 围绕 AI 重构端到端 PDLC，而不是局部加速 coding | ★★★★★ |
| Context Engineering | 把隐性知识转化为 agent 可执行的结构化输入 | ★★★★☆ |
| Verification First | 当生成速度提升后，验证成为新的研发瓶颈 | ★★★★☆ |
| Agent Manager Role | 人从执行者转向 agent 的目标设定、监督和反馈者 | ★★★★☆ |

## 9. 适合后续追踪的问题

1. Sonar 的这些指标在更大范围推广后是否仍能保持？
2. Pull request throughput 和 cycle time 提升是否会带来长期质量风险？
3. 哪些验证能力必须自动化，哪些仍应保留人工判断？
4. Agent library、prompt library、workflow library 应该如何治理？
5. 组织如何衡量 AI Native workflow 对业务结果的影响，而不仅是工程过程指标？
