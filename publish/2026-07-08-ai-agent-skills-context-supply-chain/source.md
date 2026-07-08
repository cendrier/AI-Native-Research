# AI Agent 的新依赖不是库，而是 SKILL.md：从 4.1 万个 Skills 看上下文供应链

## 原文信息

- Title: From Registry to Repository: How AI Agent Skills Are Written, Adapted, and Maintained
- Source: arXiv
- Link: https://arxiv.org/abs/2607.00911
- Publication date: 2026-07-01；revised 2026-07-06

## 核心洞察

这篇论文讨论的不是“AI coding agent 能不能写代码”，而是更底层的问题：当 agent 要稳定执行某类任务时，它依赖的上下文、流程、脚本、边界条件和恢复策略，正在被打包成一种新的工程制品：`SKILL.md`。如果说 package.json、Dockerfile、runbook 和 README 是传统软件工程的依赖与操作说明，那么 agent skills 正在变成 AI Native Engineering 的“上下文依赖”。它们不是给人看的静态文档，而是会被 agent 读入、触发并执行的操作规程。

论文的价值在于，它第一次把 skills 当作 engineered artifacts 来研究，而不是只把它们当作 agent capabilities。作者从 skills.sh 挖掘了 18,463 个 centralized skills，又从 5,876 个 GitHub 仓库收集了 23,199 个 personal-use skills，并识别出 3,709 条 registry-to-repository 的复用链接。核心发现很值得警惕：skills 的复用大量表现为一次性复制；在可识别的复用关系里，70.3% 的 pair 相似度大于等于 0.99，几乎是原样复制；超过一半的复用 skills 在采用后没有本地更新；即使 upstream 后续变化，本地 copy 也经常不同步。

这对我们做 AI coding 平台和内部工程效率建设很关键。AI agent 的可靠性不只取决于模型，也取决于它运行时拿到的“可执行上下文”是否新、准、可追溯、能验证。一个过期的 README，人看到后可能会发现不对；一个过期的 SKILL.md，agent 可能会直接照做。下一阶段的 AI Native Engineering，不只是给团队发 Cursor、Claude Code、Codex，也不是堆更多 prompt，而是建设一个可治理的 skill supply chain：有 owner、有版本、有评审、有测试、有引用来源、有失效检测、有同步机制。

## 重点内容

### 1. Skill 是 agent 时代的“上下文包”，不是普通提示词

论文把 AI agent skills 定义为结构化的 context bundles，通常由一个带 YAML frontmatter 的 `SKILL.md` 文件、Markdown 正文，以及可选的 scripts、references、assets 等文件组成。它们的用途是把某类任务所需的领域知识、执行步骤、工具调用、产出格式和失败恢复策略，在需要时加载给 agent。

这和一次性 prompt 最大的区别是：skill 是可复用、可分发、可复制到仓库里的制品。它的 frontmatter 决定是否被激活，正文决定 agent 如何行动，scripts 可能被直接执行，references 和 assets 可能成为任务证据或模板。也就是说，skill 既像文档，又像轻量依赖包，还像局部 runbook。把它只当成“提示词模板”会低估风险，也会低估它的工程价值。

Agent Skills specification 也体现了这种制品化方向：一个 skill 至少需要 `SKILL.md`，其中包含 `name` 和 `description` 等 frontmatter；可选目录包括 `scripts/`、`references/`、`assets/`；加载方式强调 progressive disclosure，即先加载 metadata，触发后再加载完整说明，必要时再拉取资源文件。这种设计本质上是在把 agent 能力从模型权重里外移到可管理的上下文资产里。

### 2. 论文的研究设计：从 registry 到 repository 追踪 skill 生命周期

作者研究了两类 skills。第一类是 centralized skills，来自 skills.sh 这样的公开 registry。作者选取截至 2026-03-04 至少 20 次 installs 的 skills，最终成功获取 18,463 个。第二类是 personal-use skills，来自公开 GitHub 仓库中的 `SKILL.md`。作者去掉 fork、archive、低星项目、教程集合和 skill marketplace 聚合仓库后，得到 5,876 个真实项目中的 23,199 个 skills。

为了识别“某个仓库里的 skill 是否来自 registry”，作者利用 YAML 的 `name` 字段做候选匹配，再用最长公共子序列相似度判断文本复用关系。阈值边界还做了人工验证：在 [0.1, 0.3) 这个最容易误判的区间，两位作者独立审查后有 90% 一致率，并认为 30 个样本中的 28 个是真复用。最终识别出 3,709 个 linked pairs，覆盖 1,673 个 centralized skills。

这个方法本身也给内部平台一个启发：skill governance 的第一步不是写更多模板，而是建立可观测性。我们需要知道哪些 skill 是内部原创，哪些来自外部，哪些被改过，哪些仍接近原版，哪些已经和上游脱钩。否则，agent 的行为依赖会散落在仓库里，既不容易审查，也不容易更新。

### 3. Registry 提供通用能力，仓库里沉淀项目生命周期知识

论文用 SWEBOK 知识领域对 skills 分类后发现，Software Construction 是最大类：centralized skills 中占 28.3%，personal-use skills 中占 22.1%。这很符合直觉：公开 registry 更容易沉淀通用的写代码、重构、生成组件、执行某类开发任务的能力。

但 personal-use skills 的分布明显更偏项目内生命周期活动。比如 Software Configuration Management 在 personal-use skills 中占 9.4%，而 centralized skills 中是 4.1%；Testing 是 6.4% vs. 4.9%；Software Quality 是 5.7% vs. 3.8%；Maintenance 是 3.9% vs. 2.6%。这说明仓库本地的 skills 更像项目自己的 operational memory：怎么跑测试，怎么处理配置，怎么遵守质量标准，怎么维护本仓库的特殊流程。

对企业内部来说，这个差异很重要。公开市场可以提供通用技能，但真正让 agent 在内部代码库里稳定工作的，是本地化的执行知识：服务拓扑、CI 入口、灰度规则、依赖版本、目录边界、数据权限、回滚流程、owner 规则。这些东西通常不会出现在公开 registry，却决定 agent 是否能安全完成任务。

### 4. 一个成熟 skill 通常包含六类内容

论文对 180 个 skills 做主题分析，归纳出六类内容。第一是 scoping and orchestrating，定义 skill 适用场景、触发条件和任务流程；第二是 running execution lifecycle，说明如何准备环境、使用工具和脚本、收集输入、形成产出；第三是 ensuring output quality，提供检查清单、验证方法和失败恢复；第四是 governing agent conduct，告诉 agent 哪些动作应该做、哪些动作禁止做；第五是 grounding domain knowledge，补充概念、机制、参数、默认值和参考资料；第六是 user/agent coordination，规定什么时候要问用户、什么时候移交给其他 agent 或人工专家。

这六类内容可以直接变成我们内部写 skill 的 checklist。一个只写“帮我重构 React 组件”的 skill 不是工程制品；一个可运营的 skill 应该说明它何时触发、输入是什么、执行步骤是什么、要用哪些工具、哪些目录不能改、如何验证结果、失败时如何降级、何时必须请求确认、哪些参考文件是 source of truth。

论文还发现，mandatory frontmatter 的合规率很高，比如 `SKILL.md` 存在、frontmatter 有效、description 类型和长度基本都在 99% 左右。但 optional fields 和目录使用很少：license、compatibility、metadata、allowed-tools 大多只在 3% 到 16% 的范围，`references/`、`scripts/`、`assets/` 的使用率也明显低于 mandatory 字段。这说明生态已经形成基本格式，但还没有形成成熟的依赖治理习惯。

### 5. 最大风险：skills 常常是一次性复制，而不是持续同步的依赖

论文最有工程警示意义的部分，是 reuse 和 maintenance。作者在 SE skills 过滤后得到 2,462 个复用 pair，其中 1,841 个在采用时几乎原样复制，相似度大于等于 0.99，只有 621 个在进入仓库时被明显改过。换句话说，很多团队不是“引入一个持续维护的依赖”，而是“复制一份说明书到本地”。

后续维护也呈现出明显分化。所有 personal-use SE skills 中，58.8% 至少有过一次后续更新；本地原创或未匹配到上游的 skills 更新率是 60.8%，中位数是 2 次 follow-up commits；而 reused skills 的本地更新率只有 47.4%。更关键的是，上游和本地经常脱钩：1,295 个从未本地更新的 reused skills 中，40.2% 的上游后来变过，但本地 copy 没有收到这些变化；在本地和上游都发生变化的 reused skills 里，62.3% 是独立分叉，而不是重新吸收上游更新。

这和传统依赖管理的区别很大。npm package 至少还有版本号、lockfile、升级提示和漏洞扫描；但复制来的 `SKILL.md` 往往没有版本，也没有同步提醒。它的风险不一定表现为 build failure，而是 agent 在某一天继续执行过期流程、引用旧路径、调用被替换的工具、使用已废弃的 API，或者在本该请求确认的地方直接行动。

### 6. Skill 维护主要是“往上加”，而不是及时清理

论文对 444 个 skill diffs 做定性编码后发现，维护行为主要集中在 reworking operational specifications 和 adapting knowledge and resources：也就是改流程、改工具、补上下文、换 reference、加示例、调输出。总体上，additions 比 removals 多 2.7 倍；如果只看 evolution 场景，增加与删除的比例达到 6.1:1。

这很像文档演化的常见问题：为了让 agent 更稳定，大家不断补规则、补例外、补提醒、补 caveat，但很少系统性删掉过时内容。短期看，这会让 skill 更“懂项目”；长期看，它会积累成 skill debt。过长的 skill 可能降低触发准确性，增加冲突规则，让 agent 更难判断优先级，也让人更难 review。

更值得注意的是，最稳定、最少被改的部分，恰恰是 runtime interaction、progress monitoring 和 failure recovery 这类行为契约。论文指出，这些规则通常随着 skill 一起迁移，下游很少改。也就是说，一个 skill 一开始怎么规定“何时问用户”“如何监控状态”“失败时怎么恢复”，很可能长期影响 agent 行为。内部团队写 skill 时，最不能草率的不是格式，而是这些行为契约。

### 7. 论文的边界：这是公开生态快照，不是企业内部全景

这篇研究的边界也要讲清楚。首先，它研究的是公开 GitHub 上可见的 `SKILL.md`，无法覆盖公司私有仓库和未公开的 agent 配置。其次，它主要围绕 skills.sh 这个 central registry，不能代表所有 skill marketplace 或内部平台。第三，linkage 依赖 `name` 字段和内容相似度，因此会漏掉被大幅改写、改名或从其他渠道复制的 skills。第四，研究时间也有窗口：skill 内容截至 2026-03-04，仓库历史截至 2026-05-04。

所以这篇文章不应该被解读为“所有 skill 生态都已经这样”，而应该被当成一个强信号：skills 已经足够多、足够像依赖、足够会被复制和漂移，因此值得进入工程管理视野。对企业内部，真正要做的是把这个信号转化成制度和平台能力。

## 给我们的启示

第一，把 skill 当成依赖，而不是 prompt。内部如果开始沉淀 Codex、Claude Code、Cursor、Copilot 或自研 agent 的 skills，就应该建立统一 registry：每个 skill 有 owner、用途、适用仓库、版本、变更记录、兼容 agent、需要的工具权限、风险等级和最后验证时间。不要让关键 skill 只散落在各仓库里，靠复制传播。

第二，skill review 应该独立于普通文档 review。评审清单至少包含：触发描述是否具体，是否有误触发风险；是否明确输入、输出和边界；是否引用最新 source of truth；scripts 是否可重复执行并有错误处理；是否声明 compatibility 和 allowed tools；是否包含验证步骤；是否有明确 failure recovery；涉及删除、发布、迁移、权限、线上资源时是否要求人工确认。

第三，把稳定行为契约和本地绑定分离。论文显示，下游经常会修改环境、路径、工具和项目知识，但很少改用户交互、监控和失败恢复规则。内部写 skill 时，可以把“通用行为契约”做成可复用模板，把“本地项目绑定”单独放到 references 或配置区。这样既能减少重复，也能避免大家在复制时无意继承不合适的风险规则。

第四，建立 skill drift 监控。对来自外部或中央 registry 的 skills，要能检测上游是否更新、本地是否同步、本地改动是否太大、引用文件是否失效、脚本是否还能跑、activation 是否发生异常。可以把这些指标接进平台 dashboard：skill version distribution、stale skill count、broken reference count、script validation pass rate、agent activation precision、manual override rate、incident-linked skill count。

第五，skill 不只是工程效率工具，也是组织知识基础设施。过去很多知识存在 README、runbook、wiki、Slack 历史和老员工脑子里；AI agent 需要把这些知识转成可加载、可验证、可更新的执行上下文。谁能把组织知识变成高质量 skills，谁就能让 agent 更快进入真实生产流程，而不是永远停留在 demo 和局部代码生成。

## 延伸阅读

- Specification - Agent Skills: https://agentskills.io/specification
- The Agent Skills Directory: https://www.skills.sh/
- Cheap Code, Costly Judgment: A Case Study on Governable Agentic Software Engineering: https://arxiv.org/abs/2607.01087
- RESOURCE2SKILL: Distilling Executable Agent Skills from Human-Created Multimodal Resources: https://arxiv.org/abs/2606.29538
- SkillsBench: Benchmarking How Well Agent Skills Work Across Diverse Tasks: https://arxiv.org/abs/2602.12670
