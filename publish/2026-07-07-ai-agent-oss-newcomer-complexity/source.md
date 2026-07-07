# AI Agent 让代码更复杂，但没有挤走开源新人：603 个仓库的因果证据

## 原文信息

- Title: Decoupling Code Complexity from Newcomer Participation: A Causal Study of AI Coding Agent Adoption in OSS
- Source: arXiv
- Link: https://arxiv.org/abs/2607.01810
- Publication date: 2026-07-02

## 核心洞察

这篇文章回答了一个很适合 AI Native Engineering 讨论的问题：当 Cursor、Claude Code 这类 AI coding agent 进入开源项目之后，它们会不会把新人的入口挤掉？直觉上有两种担心：一是 agent 最擅长处理小而清晰的任务，而这些任务原本常常是新人第一次贡献的入口；二是 agent 可能让代码结构更复杂，让新人更难读懂和修改代码。论文的结论很克制，也很有价值：代码复杂度确实上升了，但在这组可观察的开源项目里，没有发现新人参与被挤出的证据。

论文用 GitHub code search 识别出 1,888 个有 AI agent 可见采用信号的开源项目，采用信号是首次提交 `.cursorrules` 或 `CLAUDE.md` 这类 agent 配置文件。由于很多新项目是“born with the tool”，缺少真正的 agent 前历史，作者把主分析限制在 603 个至少有 6 个月采用前历史的项目，并匹配 1,784 个未采用项目做 difference-in-differences 分析。核心发现是：newcomer inflow 没有显著下降，onboarding 和 retention 没有变差，good-first-issue 这种 beginner-task 供给也没有观察到下降；同时，代码复杂度有上升，Python cognitive complexity 约 +11%，跨语言 cyclomatic complexity 约 +3% 到 +4%。

对我们来说，最重要的不是“AI agent 完全无害”，而是“不要只用速度指标或恐慌叙事管理 AI coding”。AI Native Engineering 的下一步应该同时看两类指标：一类是 velocity，比如 PR throughput、cycle time、review queue；另一类是 participation health，比如新人首个 PR 的响应时间、merge 率、留存、good-first-issue 供给、知识传递和复杂度预算。AI agent 可以提高产出，但组织仍然需要主动设计新人入口和复杂度治理，否则短期没有 crowd-out 不等于长期没有维护和学习成本。

## 重点内容

### 1. 论文讨论的不是“AI 会不会写代码”，而是“AI 会不会改变人的进入路径”

过去很多 AI coding 研究集中在 productivity：任务是否更快完成，PR 是否更多，开发者是否更满意。这篇论文换了一个角度：开源项目依赖持续的新贡献者流入，如果 AI coding agent 把简单任务做掉，或者让代码更难理解，新人可能失去练手机会，也更难完成第一次贡献。

作者把这个担心拆成三个可检验的问题。第一，AI agent adoption 之后，新人流入是否下降？第二，代码复杂度是否真的上升？第三，如果复杂度上升，它是否会在同一组项目里转化为新人参与下降？这个拆法很重要，因为它区分了“机制存在”和“机制造成伤害”。很多组织在讨论 AI adoption 时也会混淆这两件事：看到代码变多或复杂度变高，就直接推断新人培养会受损；或者看到产出变快，就推断组织能力一定增强。论文提供的是更细的因果链路分析。

### 2. 采用信号来自 `.cursorrules` 和 `CLAUDE.md`，这是可观察 adoption，不是使用强度

作者用 GitHub code search 找到首次提交 `.cursorrules` 或 `CLAUDE.md` 的仓库，并把这个 commit 日期当作项目可见采用 AI agent 的时间点。这个方法的好处是公开、可复现、可确定日期；局限是它只能代表 visible adoption，不能代表真实使用强度。一个项目有配置文件，不等于每天大量使用 agent；一个项目没有配置文件，也不等于没人用 AI 工具。

为了避免把 bot 或 agent 自己的 commit 算成人类贡献，作者还用稳定的 GitHub numeric user id 排除已知 bot 和 agent 账号，而不是只看容易伪装的用户名。这一点很适合放进我们的 AI coding measurement 方法库：当我们衡量 AI-assisted engineering 时，第一步不是看 dashboard，而是先定义哪些事件是人的行为、哪些是 agent 行为、哪些只是 adoption proxy。

### 3. 为什么主分析只看 603 个项目，而不是全部 1,888 个项目

论文最值得学习的方法点之一，是作者没有把 1,888 个采用项目全部拿来做 before/after 对比。因为很多仓库是在 AI agent 已经常见之后才创建的，也就是“born with the tool”。这些项目几乎没有 agent 前历史，不能用于判断采用前后变化。如果硬把它们纳入 before/after，会把项目生命周期、日历趋势和 agent adoption 混在一起。

所以主分析只保留 603 个至少有 6 个月采用前历史的项目，并用 1,784 个从未采用的项目作为匹配对照。匹配特征包括项目年龄、热度、语言、近期活跃度等，之后再用 difference-in-differences 估计采用后的变化。这个处理提醒我们：企业内部做 AI coding 效果评估时，也不能简单比较“用了 AI 的团队”和“没用 AI 的团队”。更可靠的做法是保留基线期、匹配相似团队、看趋势是否平行，再解释 adoption 之后的差异。

### 4. 新人参与没有显著下降：inflow、onboarding、retention 都没有变差

论文在人类参与侧看了几类结果：每月新人数量、新人第一个 PR 的处理情况、3 个月和 6 个月留存，以及 good-first-issue 这类 beginner-friendly task 的供给。结果是，主分析没有发现 visible agent adoption 之后新人流入显著下降；第一个 PR 的接受、响应和合并相关指标没有显示系统性恶化；新人留存也没有变差。good-first-issue 数据比较稀疏，作者也明确提醒不能过度解读，但观察上没有看到下降。

这并不意味着每个项目都不会受到影响。它更准确的含义是：在这些已建立、可观察、有足够历史的开源项目里，AI agent adoption 还没有表现出“把新人挤出去”的平均效应。对企业组织也类似：AI coding agent 不一定天然伤害 junior engineer 或新成员，但前提是项目仍然保留真实任务、review 互动、上下文讲解和反馈循环。如果组织把所有低风险任务都交给 agent，又没有重新设计学习路径，风险仍然存在。

### 5. 复杂度确实上升，但幅度比一些先前担忧更小

论文并没有否认复杂度问题。作者发现，adoption 后代码复杂度确实上升：Python 子集上的 cognitive complexity 约 +11%，跨语言 cyclomatic complexity 约 +3% 到 +4%。这说明 agent 生成或辅助修改代码时，可能带来更多嵌套、分支、控制流或局部结构复杂度。

但这个幅度也很关键。论文把它称为 modest increase，并指出它低于某些先前研究中更大的估计。我们不应该把这解读成“复杂度不用管”，而应该解读成“复杂度是可治理的问题”。如果团队有清晰的代码所有权、refactoring budget、架构约束、测试覆盖、review checklist 和复杂度阈值，AI agent 带来的复杂度增长可能不会直接转化为新人流失。反过来，如果团队本来就缺少这些机制，哪怕复杂度只上升几个百分点，也可能叠加成长期维护负担。

### 6. 最关键的发现是“decoupling”：复杂度机制存在，但没有传导到新人流失

这篇论文的题眼是 decoupling。AI agent adoption 后，代码复杂度上升这个机制是真实存在的；但在作者可观察到的同一组项目里，这个机制没有进一步传导为 newcomer inflow、first-PR activity 或 retention 的下降。换句话说，“代码更复杂”与“新人被挤出”不是自动连在一起的。

这个结论对 AI Native Engineering 很有启发。我们经常把一个局部指标当成整个系统的代理：代码生成更多等于效率提升，review 变慢等于 AI 失败，复杂度上升等于新人流失。真正成熟的工程管理应该看链路：生成速度如何影响 review，review 如何影响 merge，复杂度如何影响 onboarding，onboarding 如何影响长期维护和人才培养。链路中任何一个环节都可能被组织设计缓冲或放大。

### 7. 论文的边界也要写清楚

这篇研究不是在说 AI agent 对所有项目都安全。首先，它衡量的是 visible adoption，不是实际 token usage 或任务级 agent intensity。其次，主分析聚焦已经存在、至少有一段采用前历史的项目；对从一开始就围绕 agent 工作流创建的新项目，论文没有给出同样强的因果结论。第三，good-first-issue 标签本来就很稀疏，适合当辅助信号，不适合单独作为新人任务供给的完整度量。第四，研究对象是公开 GitHub OSS，不等同于企业内部代码库。

所以这篇文章更适合被当作“方法论和指标启发”，而不是一句结论。它告诉我们：AI agent adoption 的影响需要拆成 adoption signal、usage intensity、code complexity、onboarding experience、retention 和 task supply 多个层次来测量；只看一个层次，容易得出过度乐观或过度悲观的判断。

## 给我们的启示

第一，AI coding rollout 要加入“人类参与健康度”指标。除了 active users、AI-assisted PR 占比、PR throughput、review latency，我们还应该跟踪新人或新成员的首个任务完成时间、首个 PR response time、merge rate、3/6 个月留存、mentor/reviewer 互动量、good-first-issue 或 starter task 供给，以及高复杂度代码区域的新人成本。

第二，junior engineer 和新成员培养不能继续依赖“自然掉出来的小任务”。当 agent 可以快速处理简单 bug、脚手架、测试补齐和文档修改时，组织要主动设计学习任务：明确哪些任务适合新人做，哪些任务适合新人和 agent pair 做，哪些任务需要人工 review 中解释架构和业务背景。否则，短期 productivity 可能掩盖长期人才 pipeline 的空心化。

第三，复杂度要从 code review 的主观感受变成工程控制面。可以把 cyclomatic/cognitive complexity、函数长度、重复逻辑、测试覆盖、owner risk、变更范围、敏感目录等指标接进 PR 和 CI。对 AI-assisted changes，不一定要更慢，但要更可解释：为什么这样改，哪些测试证明它有效，有没有减少或增加复杂度。

第四，做 AI adoption 评估时要避免 naive before/after。论文处理 1,888 个项目时，专门把缺少采用前历史的 born-with-the-tool 项目与可识别样本区分开，这个方法很值得企业内部借鉴。我们做团队评估时，也应该区分新团队、老团队、强制 adoption、自然 adoption、轻量使用和深度使用，并尽量构造合理对照。

第五，AI Native Engineering 的成熟度不是“人被 agent 替代多少”，而是“人和 agent 的协作系统是否还能吸纳新人、传递知识、控制复杂度、稳定交付”。今天这篇论文给我们的好消息是，AI agent 带来的复杂度并不必然挤走新人；坏消息是，这个结果不是自动发生的，背后可能依赖项目本身的成熟度、review 机制和社区惯性。组织需要把这些机制显式化。

## 延伸阅读

- arXiv: Cheap Code, Costly Judgment: A Case Study on Governable Agentic Software Engineering — https://arxiv.org/abs/2607.01087
- arXiv: AI Writes Faster Than Humans Can Review: A Longitudinal Study of an Enterprise 2x Mandate — https://arxiv.org/abs/2607.01904
- arXiv: Adoption and Impact of Command-Line AI Coding Agents — https://arxiv.org/abs/2607.01418
- arXiv: Detecting AI Coding Agents in Open Source: A Validated Multi-Method Census of 180 Million Repositories — https://arxiv.org/abs/2606.22419
