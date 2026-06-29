# OpenAI 最新研究：AI Coding 正在进入 Agentic Work 时代

## 原文信息

- **标题**：How agents are transforming work
- **来源**：OpenAI / arXiv
- **链接**：https://arxiv.org/abs/2606.26959
- **发布日期**：2026-06-25

配套参考：OpenAI 白皮书 *Codex-maxxing for long-running work*  
https://cdn.openai.com/pdf/8a9f00cf-d379-4e20-b06f-dd7ba5196a11/OAI_WhitePaper_Codex-maxxing26.pdf

## 核心洞察

这组 OpenAI 材料值得关注，是因为它把 AI Coding 的讨论从“写代码更快”推进到了“长期工作如何被委派、执行和管理”。研究文章提供了 Codex 的使用数据，白皮书则给出了实践方法。合起来看，一个重要变化正在发生：AI 的使用单位不再只是 prompt 或 chat，而是可以持续推进、可以并行管理、可以沉淀复用的工作流。

关键判断有五个。第一，AI adoption 的衡量对象正在从“使用次数”转向“委派任务”。第二，Codex 用户正在提交越来越复杂的工作，不少任务已经接近原本需要人类连续工作数小时才能完成的工作包。第三，OpenAI 内部的 Codex 使用已经从工程部门扩展到 Legal、Finance、Recruiting 等非技术团队。第四，高阶使用方式不是单个 agent，而是同时管理多个 agent。第五，长期工作需要 durable thread、memory、review surface 和 verifiable goals，而不是每次从一个新 prompt 开始。

![Card 1 — Executive Summary](assets/card-01-executive-summary.png)

## 重点内容

### 1. 从单次对话到长期委派任务

OpenAI 在研究中把 agentic AI 和传统聊天式 AI 区分开来。传统 AI 使用更多是单次问答、文本生成或局部辅助；agentic AI 则可以持续运行，调用工具，操作环境，并围绕一个目标迭代执行。Codex 的使用数据说明，越来越多用户不是让 AI 回答一个问题，而是把一个完整工作包交给 Codex 推进。

这也是整篇文章最核心的逻辑：当 AI 可以持续执行任务时，真正发生变化的不是“回答速度”，而是“工作组织方式”。一个任务如何被描述、如何提供上下文、如何设定边界、如何验收结果，会变得比 prompt 本身更重要。

### 2. Codex 用户正在提交更复杂的工作

研究中一个重要指标，是估算用户请求如果由有经验的人类完成需要多久。到 2026 年 5 月，在抽样个人 Codex 用户中，80.6% 至少提交过一次预计超过 30 分钟人工工作的请求，70.2% 至少提交过一次超过 1 小时的请求，25.6% 至少提交过一次超过 8 小时的请求。

这些数字说明，Codex 已经不只是处理“小修小补”。用户开始把更长、更复杂、更接近完整交付的任务交给 agent。对组织来说，这意味着要重新思考任务拆分、验收标准、审查容量、权限边界和交付责任。

### 3. Codex 使用正在从工程团队扩展到整个组织

OpenAI 的内部使用情况显示，Codex 不再只是工程团队的工具。Legal、Finance、Recruiting 等非技术团队也开始把 Codex 用于自动化、数据处理、分析、脚本和流程支持。研究里还提到，非开发者用户增长很快，说明 agentic tools 正在跨过传统的“开发者工具”边界。

这点很关键。AI Native Organization 的分界线，不是有没有部署聊天机器人，而是 agent 是否进入了真实业务流程。当非工程团队也可以通过 agent 完成技术性工作，组织需要提供更清晰的 guardrails、模板、权限控制和审查机制。

### 4. 高阶使用方式是管理多个 agent

研究显示，超过 10% 的用户每周某个时点会管理 3 个或更多并发 Codex agents。与此同时，skills 的使用也在增长。skills 可以把复杂工作流的指令、脚本、参考材料和流程规范打包复用，让团队不必每次重新发明同一个工作方式。

这意味着 AI 能力的进阶路径正在变化。初级使用者会问问题；中级使用者会委派任务；高阶使用者会并行管理多个 agent；组织级能力则是把成功的流程沉淀为 skills、playbooks 和可复用的工作系统。

![Card 2 — Long-running Agent Loop](assets/card-02-long-running-agent-loop.png)

### 5. Codex-maxxing：让长期工作有一个持续存在的地方

配套白皮书 *Codex-maxxing for long-running work* 强调，重要工作不应该每次从一个新对话开始。长期工作需要 durable thread 承载上下文，需要 memory 记录项目状态和历史决策，需要 steering 在执行过程中不断校正方向，需要 connectors / tools 进入真实工作表面，也需要 verifiable goals 让结果可以被验证。

白皮书背后的核心思想是：Codex 的价值不只是“生成内容”，而是成为一个可以持续推进工作的空间。这个空间里有目标、有上下文、有工具、有审查、有记忆，也有自动化回访。换句话说，Codex-maxxing 的重点不是 prompt 技巧，而是 workflow engineering。

## 给我们的启示

对 AI Native Engineering 来说，这组材料至少有五个借鉴点。

第一，衡量 AI 价值时，不应只看使用人数、prompt 数、token 数或生成代码量，而要看被委派任务的复杂度、完成率、审查成本和最终交付质量。第二，每个 agent work package 都应该有明确的 done criteria、review owner 和 rollback path。第三，memory 应该成为基础设施，重要决策和项目状态不能只藏在聊天历史里，而要可编辑、可审查、可复用。第四，非工程团队通过 agent 进行技术执行会越来越普遍，平台团队需要提前设计权限、模板和审查机制。第五，可复用的单位会从文档和脚本升级为 skills、playbooks 和 agentic workflows。

这对我们自己的 AI Native Research 也有直接启发：GitHub 不只是归档材料，而可以成为 Codex 的 memory vault；每日文章不是单次产物，而是长期研究流的一部分；视觉卡片、source links、handoff、发布状态都应该进入同一个可追踪的工作循环。

![Card 3 — Engineering Implications](assets/card-03-engineering-implications.png)

## 延伸阅读

- OpenAI / arXiv：How agents are transforming work  
  https://arxiv.org/abs/2606.26959
- OpenAI：Codex-maxxing for long-running work  
  https://cdn.openai.com/pdf/8a9f00cf-d379-4e20-b06f-dd7ba5196a11/OAI_WhitePaper_Codex-maxxing26.pdf
