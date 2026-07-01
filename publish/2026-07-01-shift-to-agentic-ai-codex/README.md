# 从聊天到派工：OpenAI Codex 数据揭示 Agentic AI 的真实组织形态

## 原文信息

- Title: The Shift to Agentic AI: Evidence from Codex
- Source: arXiv / OpenAI, Columbia Business School, Wharton, Duke Fuqua authors
- Link: https://arxiv.org/abs/2606.26959
- Publication date: 2026-06-25

## ⭐ Tier 0 Special Attention

这是一篇值得做专题分析的 Tier 0 来源。它不是普通的产品发布或观点文章，而是基于 OpenAI Codex 使用数据的实证研究，覆盖个人用户、组织用户和 OpenAI 内部员工三个群体，并尝试回答一个关键问题：当 AI 从“聊天助手”变成能执行任务的 agentic system 时，工作组织方式会发生什么变化。

对 AI Native Engineering 来说，它的价值不在于证明“Codex 很火”，而在于给出了新的观测维度：谁在用、用来做什么、任务复杂度是否上升、是否开始并行运行多个 agent、是否把可复用 workflow 写成 skills/plugins。这些指标比“有多少人用了 AI”更接近我们真正关心的组织能力。

## 核心洞察

这篇论文的核心判断是：Agentic AI 的采用，不只是从一个 AI 产品切到另一个 AI 产品，而是从“向模型提问”转向“把工作派给系统执行”。在这个转变里，软件工程是最先发生变化的场景，因为代码天然是数字化、可验证、可拆分的工作对象；但当组织的采用摩擦降低后，agentic workflow 会从编码扩散到研究、文档、数据分析、沟通、招聘、销售和产品工作。

几个关键 takeaway：第一，Agentic AI 的 adoption 非常快，但极不均匀。Codex weekly active users 在 2026 年上半年增长超过 5 倍；但在最近 28 天内，个人用户中只有 0.7% 使用 Codex，组织用户是 17.3%，OpenAI 内部则达到 97.9%。如果看输出 token 占比，差异更明显：Codex 占 OpenAI 员工在 Codex+ChatGPT 中输出 token 的 99.8%，组织用户是 63.3%，个人用户是 16.5%。

第二，真正的分水岭不是“写代码更快”，而是“工作是否被委托出去”。论文把 Codex 使用定义为 delegated production：用户让系统去 debug、refactor、validate、配置应用、分析数据、生成文档，而不仅是问建议。

第三，重度用户已经开始像管理一组 agent 一样工作。OpenAI 内部只有 10.7% 的用户在观测周内始终只运行单一 workflow，28.6% 的用户曾同时管理 5 个或更多 agent。论文还观察到，OpenAI 员工在 2026-06-11 当天的中位数 Codex task runtime 为 2.5 小时，而 99 分位用户每天约有 71 agent-hours 的运行量。

第四，skills/plugins 是从零散使用走向 workflow infrastructure 的信号。到 2026-06-11，活跃 Codex 用户中 26.6% 使用过至少一种 skill；OpenAI 内部该比例达到 96.2%。这说明组织价值不只来自模型能力，也来自把团队规则、工具入口、文档流程和审查标准编码成可复用资产。

## 重点内容

### 1. 从 conversational AI 到 agentic AI：单位从“对话”变成“被委托的工作流”

论文开头区分了两类 AI 使用方式。ChatGPT 这类 conversational interface 的核心单位是一次对话：用户提问，模型回答。Codex 这类 agentic interface 的核心单位则是一个 delegated workflow：系统可以读取文件、调用工具、执行命令、修改 artifact，并在较长时间内替用户推进任务。

这意味着传统 AI adoption 指标会失真。只看活跃用户、消息数或聊天次数，无法解释 agentic AI 带来的产出变化。更合理的指标包括：delegated task complexity、agent runtime、workflow reuse、concurrency、production output，以及最终进入业务流程的验收结果。

### 2. Adoption 的差异说明：模型能力不是瓶颈的全部，组织上下文才是放大器

论文把用户分为个人用户、外部组织用户和 OpenAI 内部员工。三组用户使用同一个产品方向，但行为差异巨大。OpenAI 内部 Codex 几乎替代了 ChatGPT 作为工作 AI interface；外部组织用户正在快速迁移；个人用户采用率仍低，但采用者使用强度高。

这个差异说明 agentic AI 的价值并不只是“模型够不够强”。真正决定 adoption depth 的因素包括：是否能安全接入代码库和文件系统、是否有管理层预期、是否有足够熟悉 AI 的员工、是否有 review 和验证流程、是否能把高频任务沉淀成 skills/plugins。

### 3. 软件工程是 leading edge，但不是终点

在所有用户群体中，Codex 最常见的任务仍然围绕软件生产：code implementation、code understanding、code validation、engineering operations、application management。这说明 AI coding agent 已经从“生成一段代码”扩展到软件开发生命周期里的多个环节，包括理解系统、配置环境、验证改动、管理仓库和生成技术文档。

但在 OpenAI 内部，任务组合已经明显外溢到非工程场景：研究、planning、communication、data analysis、product work、recruiting、sales 等。论文的解释是，软件是 agentic AI 最容易起步的领域，因为产物可验证、任务可拆分、执行环境数字化；但当使用成本、权限和工作习惯摩擦下降后，同样的 delegation pattern 会扩散到更广泛的知识工作。

### 4. 任务复杂度正在上升：用户开始把“大块工作”交给 agent

论文使用自动分类器估计用户请求如果由有经验的人类完成需要多长时间。结果显示，个人用户中，至少提交过一个“人类需要 1 小时以上完成”的 prompt 的比例，从 2025 年 12 月的 35.4% 上升到 2026 年 5 月的 70.2%。更复杂任务的增长更明显：至少提交过一个“人类需要 8 小时完成”的 prompt 的用户比例，从 2.1% 上升到 25.6%。

这说明用户对 agent 的心理模型在变化：从“帮我补一个函数”变成“帮我完成一个 feature / investigation / migration / analysis”。这也解释了为什么 agentic tooling 对工作组织的影响会大于 autocomplete：它改变的是任务边界，而不只是输入速度。

### 5. 并行 agent 与长运行任务：人类角色变成 dispatch、review、integration

论文特别分析了 concurrency。外部个人和组织用户多数还没有形成并行 agent 工作方式；但 OpenAI 内部已经出现明显差异。观测周内，OpenAI 用户只有 10.7% 始终只使用单一 workflow，28.6% 曾同时管理 5 个或更多 agent。这种工作方式更像“一个人管理多个执行线程”，而不是“一个人和一个助手聊天”。

长运行任务也在出现。OpenAI 内部中位数员工在 2026-06-11 当天有 2.5 小时的 Codex turns 处于运行状态；99 分位用户则达到约 71 agent-hours/day，意味着任意时刻都有多个 agent 并行工作。

这对工程管理的启示很直接：AI Native Engineering 的核心能力会从“谁 prompt 写得好”逐步转向“谁能定义任务、切分上下文、设置 guardrail、并行推进、快速 review、整合结果”。这是一种 supervisory engineering work。

### 6. Skills/plugins：把临时 prompt 变成组织级生产系统

论文把 systematization 定义为从 ad hoc use 到 reusable workflow infrastructure。Codex 中的 skills/plugins 可以把说明、脚本、工具接入和团队偏好封装成可复用单元。到 2026-06-11，活跃 Codex 用户中 26.6% 使用过至少一种 skill；OpenAI 内部达到 96.2%，组织用户和个人用户分别约 30.4% 和 25.7%。

这一点非常重要。很多团队讨论 AI coding 时仍停留在“如何写 prompt”或“选哪个工具”。但论文显示，真正形成复利的是 workflow codification：把反复发生的任务写成可执行规范，把工程标准写成可验证规则，把常用数据源和工具链接入 agent，把 review checklist 固化到流程里。

## 给我们的启示

第一，AI Native Engineering 不应该把 AI coding adoption 当作一个工具采购项目，而应该当作 workflow redesign。工具上线只是第一步，真正的组织收益来自任务拆分、权限设计、自动验证、review 队列、上下文资产和复用机制。

第二，我们需要重建工程效能指标。传统的 PR 数、commit 数、代码行数、ticket throughput 都会被 agentic workflow 扭曲。更有用的指标应该包括：agent-hours、delegated task size、review latency、revert/rollback rate、test pass rate、human intervention count、skill reuse rate、从 agent output 到 merged/shipped 的通过率，以及被复用的 workflow 数量。

第三，团队应该尽快沉淀自己的 skills。每个团队都可以从三类开始：代码库理解 skill、变更验证 skill、发布/复盘文档 skill。它们不需要一开始很复杂，但要把团队约定、目录结构、测试命令、review 标准和输出模板写清楚。相比临时 prompt，skill 更像组织记忆。

第四，工程师的核心能力会向“监督型工程”迁移。未来优秀工程师不只是自己写代码快，而是能把问题切成 agent 可执行任务，能判断输出是否可靠，能设计自动化验证，能管理多个 agent 的并行工作，并能把结果整合进稳定的生产系统。

第五，采用节奏应该从低风险、高验证任务开始。适合先交给 agent 的任务包括代码理解、测试补齐、文档生成、静态检查、简单重构、数据整理、迁移方案草稿。涉及生产变更、权限扩展、架构决策和安全敏感逻辑时，必须保留人工 review 和自动化 gate。

## 延伸阅读

- Detecting AI Coding Agents in Open Source: A Validated Multi-Method Census of 180 Million Repositories — 用开源仓库视角衡量 AI coding agent 足迹，适合作为本文“组织内部使用数据”的外部对照：https://arxiv.org/abs/2606.15765
- AWS commits $1 billion toward new unit for embedded AI engineers — Reuters 对 AWS forward-deployed AI engineers 的报道，说明大型云厂商正在把 AI 工程落地变成组织服务形态：https://www.reuters.com/business/retail-consumer/amazons-aws-commits-1-billion-toward-new-unit-embedded-ai-engineers-2026-06-30/
- Writing Code vs. Shipping Code: Productivity Effects Across Generations of AI Coding Tools — 论文引用的 NBER 工作论文，适合作为“写代码”和“交付软件”之间差距的补充阅读：https://www.nber.org/papers/w35275
