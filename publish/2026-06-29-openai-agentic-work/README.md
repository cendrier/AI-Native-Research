# OpenAI 最新研究：AI Coding 正在进入 Agentic Work 时代

## 原文信息

- **主文标题**：How agents are transforming work  
- **来源**：OpenAI / arXiv  
- **发布日期**：2026-06-25  
- **原文链接**：https://arxiv.org/abs/2606.26959  
- **配套白皮书**：Codex-maxxing for long-running work  
- **白皮书链接**：https://cdn.openai.com/pdf/8a9f00cf-d379-4e20-b06f-dd7ba5196a11/OAI_WhitePaper_Codex-maxxing26.pdf

## Editor's Note

如果今天只记住一个判断，那就是：AI Coding 的竞争优势正在从“更快生成代码”转向“更好地管理长期工作”。真正重要的已经不是 prompt 本身，而是能否把任务定义、上下文、工具调用、审查、记忆和自动化串成一个可持续运转的 agentic work system。

## 为什么值得读

这组 OpenAI 材料很重要，因为它同时给出了 **证据** 和 **方法**。研究文章用 Codex 使用数据说明，AI 的使用单位正在从单次对话变成长期委派任务；配套白皮书则告诉我们，怎样把 Codex 从一个问答工具变成长期工作空间。对 AI Native Engineering 来说，这意味着组织关注点将从“AI 能否帮工程师快一点”转向“团队能否用 agent 管理更复杂、更长期、可复用的工作流”。

## 核心洞察

1. **AI adoption 的衡量单位正在改变。** 重点不再是问了多少次 AI，而是委派了多少可持续执行的工作包。
2. **长任务成为主流。** 在 OpenAI 抽样个人 Codex 用户中，80.6% 至少提交过一次估计超过 30 分钟人工工作的任务，70.2% 提交过超过 1 小时的任务，25.6% 提交过超过 8 小时的任务。
3. **高阶用户开始管理多个并发 agent。** 超过 10% 的用户每周某个时点会管理 3 个或更多并发 Codex agents。
4. **非开发者增长更快。** Codex 不再只是 coding tool，而是在向通用知识工作执行层扩展。
5. **长期工作需要 durable thread + memory + review surface。** 这也是 Codex-maxxing 白皮书最重要的方法论。

![Card 1 — Executive Summary](assets/card-01-executive-summary.png)

## 重点内容提取

### 1. 原文主题：Agentic AI 正在把工作从“短对话”推向“长任务”

**原文关键点**  
OpenAI 在研究里指出，agentic AI 的基本单位不再是单轮对话，而是可以持续数分钟、数小时甚至更久的委派任务。Codex 能在任务执行过程中调用工具、操作环境并迭代产出，而不是只返回一个回答。

**我的解释**  
这说明未来工程效率的关键不再是“问得好不好”，而是“任务定义得好不好”。组织需要重新设计任务拆分、上下文准备、验收标准和审查流程。

### 2. 原文主题：Codex 用户正在提交更复杂的工作

**原文关键点**  
到 2026 年 5 月，抽样个人 Codex 用户里：80.6% 至少提交过一次预计超过 30 分钟人工工作的任务；70.2% 至少提交过一次超过 1 小时的任务；25.6% 至少提交过一次超过 8 小时的任务。

**我的解释**  
这组数据很重要，因为它说明 AI 工具不再只是做零散辅助，而是在吞掉原本需要人类长时间完成的完整工作包。

### 3. 原文主题：OpenAI 内部已经从 ChatGPT-first 转向 Codex-first

**原文关键点**  
OpenAI 表示，Codex 已经成为内部各部门的主要 AI 工作工具。Legal、Finance、Recruiting 等非技术部门也跨过了多数使用门槛，说明 agentic tools 正在变成组织级执行层，而不是局限于工程团队。

**我的解释**  
AI Native Organization 的分界线不是“有没有部署聊天工具”，而是“agent 是否已经进入真实业务流程”。

### 4. 原文主题：高阶使用不是单个 agent，而是 agent orchestration

**原文关键点**  
研究显示，超过 10% 的用户每周某个时点会管理 3 个或更多并发 agents；skills 的使用率也在提升，表明用户开始把复杂流程系统化、复用化。

**我的解释**  
这意味着下一阶段的能力不是会用 AI，而是会管理多个 AI 工作流，并将成功流程沉淀为团队资产。

![Card 2 — Long-running Agent Loop](assets/card-02-long-running-agent-loop.png)

### 5. 配套白皮书主题：Codex-maxxing 给出了长期工作的方法论

**原文关键点**  
白皮书强调 durable threads、voice input、steering、memory、connectors、thread automations、verifiable goals 和 side panel。重点是让工作保留在同一个长期上下文中，持续推进，而不是每次从零开始。

**我的解释**  
这是从 prompt engineering 走向 workflow engineering 的分水岭。长期工作流不是单点技巧，而是一个完整系统：目标、上下文、执行、审查、记忆、自动化和复用。

## AI Native Engineering 解读

对 AI Native Engineering 来说，这组材料至少带来五个启发：

1. **Measure delegation, not usage.** 不要只看使用人数、prompt 数量或 token 数量，要看委派任务的复杂度和被验证后的产出。  
2. **Design for verification.** 每个 agent work package 都要有明确的 done criteria、review owner 和回滚路径。  
3. **Build memory as infrastructure.** 长期上下文不能只藏在聊天记录里，而要变成可审查、可编辑、可复用的组织记忆。  
4. **Prepare for non-engineer technical execution.** 非开发团队会越来越多地通过 agent 做技术执行，平台和治理要提前跟上。  
5. **Turn workflows into skills.** 复用的单位将从脚本和文档，升级为 skills、playbooks 和 agentic workflows。

![Card 3 — Engineering Implications](assets/card-03-engineering-implications.png)

## Case

### OpenAI Codex 内部采用

- **类型**：Frontier internal adoption case  
- **关键现象**：Codex 正在替代大量 ChatGPT 工作场景；非开发部门快速采用；并发 agent 管理成为高阶使用特征。  
- **代表意义**：展示了 agentic work 从工程场景向组织级工作系统扩散的趋势。

## Pattern

### Long-running Agentic Work Loop

```text
Goal → Context → Durable Thread → Tools → Agent Execution → Review → Memory → Automation → Reuse
```

这个 Pattern 适合沉淀到团队知识库，用于定义未来的 AI Coding / AI Native Engineering 工作流标准。

## 视觉卡片

- Card 1 — Executive Summary：从 Prompt 到 Delegated Work  
- Card 2 — Long-running Agent Loop：长期工作循环  
- Card 3 — Engineering Implications：对研发组织的 6 个启发

## 延伸阅读

- How agents are transforming work： https://arxiv.org/abs/2606.26959  
- Codex-maxxing for long-running work： https://cdn.openai.com/pdf/8a9f00cf-d379-4e20-b06f-dd7ba5196a11/OAI_WhitePaper_Codex-maxxing26.pdf
