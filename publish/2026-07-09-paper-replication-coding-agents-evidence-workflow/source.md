# AI Agent 的交付物不是最终回答，而是可验证工作区：Paper-replication 的启示

## 原文信息

- Title: Coding-agents can replicate scientific machine learning papers
- Source: arXiv
- Link: https://arxiv.org/abs/2607.02134
- Publication date: 2026-07-02

## 核心洞察

这篇论文最值得读的地方，不是它说“coding agent 可以复现论文”，而是它把一个更通用的工程问题讲清楚了：当 AI agent 执行长链路、高不确定性的工作时，我们不能再把“agent 最后说完成了”当成交付物。真正的交付物应该是一个可检查、可恢复、可追溯、可复跑的工作区：里面有目标清单、任务账本、方法重构、运行记录、产物哈希、证据对比、报告覆盖，以及独立于 agent 最终回答的 validation gate。

作者提出的 Paper-replication workflow，把科学机器学习论文复现拆成 target-level evidence task，并实现成一个 coding-agent skill。它要求 agent 从论文材料出发，记录要复现的 claims，重构方法，运行实验，把每个输出链接到命令、代码、配置、seed、论文段落和接受规则，再通过外部检查确认每个 target 是否真的有证据支撑。论文在 4 篇 scientific machine learning papers 上做了 12 次独立运行，所有 workspace 都通过 completion gate，158 个 recorded targets 都有 report coverage。

这对 AI Native Engineering 的启示很直接：AI agent 的下一阶段，不只是更会写代码、更会跑命令，而是要能留下“证据链”。内部如果要让 agent 处理研发分析、代码迁移、性能优化、线上排障、安全修复、论文复现或复杂评估，就不能只看最终 diff 或最终总结。我们需要把每一次 agent run 设计成 evidence-producing workflow：输出可以被人 review，过程可以被审计，失败路径可以被复盘，完成标准由外部 gate 判断，而不是由 agent 自己宣布。

## 重点内容

### 1. Prompt 不够，因为最终回答不是证据

论文从科学论文复现切入。对于 scientific machine learning paper，论文里的数字、图、表和结论不仅依赖公式和文字描述，也依赖代码、数据、solver、preprocessing、随机种子、训练细节、采样策略和实现选择。很多论文材料并不会完整提供这些细节，agent 即使读懂了论文，也必须做假设、实现方法、运行实验，并判断输出是否足以支持原始 claim。

直接给 agent 一个 prompt，让它“复现这篇论文”，问题在于 prompt 本身不会保存进度，也不会强制检查证据。agent 可能只复现一部分就报告完成，可能忘记哪些 target 没做，可能把论文原始图片当成自己生成的结果，也可能用替代方法做出一个看起来相似的图，然后把相似性当成复现成功。

所以作者把核心标准从“agent 是否给出令人信服的 final message”改成“workspace 是否包含足够证据”。这是一个很关键的范式变化：最终回答只是摘要，不能当作完成证据；真正的证据必须存在于可检查的文件、记录、运行产物和 validation result 里。

### 2. Paper-replication 的核心：把论文 claim 拆成 target-level evidence contract

Paper-replication 把论文复现定义成一个 target-level evidence task。每个 target 可以是一个 figure、table、reported scalar、learned field、distribution、trajectory、discovered equation，或者某个结构性 statement。对于每个 target，agent 都必须记录它来自论文哪里，需要用哪部分方法和数据，应该产生什么输出，用什么规则判断，当前状态是什么，以及最终报告里在哪里覆盖。

论文把证据 bundle 写成一个明确结构：candidate output、execution record、provenance record、comparison evidence、report coverage。也就是说，单独一个生成出来的图或表不算证据；只有当它能连接到成功运行、实现文件、配置、seed、论文段落、比较规则和报告位置时，才有资格被标记为 matched。

这和我们内部做 AI coding / AI R&D workflow 很像。agent 生成的 patch、benchmark 图、incident diagnosis、architecture proposal，本身都只是 output。真正能交付给团队的，是 output 背后的证据合同：它解决了哪个目标，基于哪些输入，执行了哪些命令，改了哪些文件，跑过哪些测试，哪些检查通过，哪些假设仍然不确定。

### 3. Workflow 结构：agent work、workspace records、validation checks 三层分离

论文 Figure 1 很适合作为这篇文章的 source proof。它把 Paper-replication workflow 拆成三层。第一层是 agent work：inspect paper materials、record target list、record method reconstruction、run experiments、compare and report。第二层是 workspace records：source inventory + hashes、reproduction matrix + task ledger、specification files、run record + provenance record + comparison、report coverage + replication report。第三层是 validation checks：paper-asset checks、active-target check、specification check、provenance + comparison checks、report-coverage check + completion gate。

这个三层结构的价值在于解耦。agent 负责执行复杂工作，但 workspace records 负责保存事实，validation checks 负责决定哪些事实达标。这样即使 agent 中途断线、上下文丢失、重新打开任务，也可以通过 workspace 恢复状态，而不是依赖聊天记录。更重要的是，人可以审查工作区，而不是只能读一个漂亮总结。

这也解释了为什么作者把它实现成 coding-agent skill。skill 不是一段普通提示词，而是一套可复用的任务说明和 workspace utilities。它包括 `SKILL.md`、面向 Codex 和 Claude Code 的适配 prompt、`references/` 里的 workspace contract，以及 `scripts/paper_replication.py` 这样的初始化、记录和检查工具。skill 不替 agent 做科学实现；它改变 agent 工作的环境，让 agent 必须按照证据结构行动。

### 4. 结果：12 次运行全部完成，但“完成”被定义得很克制

论文在 4 篇 scientific machine learning papers 上做了 12 次独立运行，覆盖 PIFT、PINN-I、PINN-II 和 SINDy 四类案例。所有 12 个 workspace 都通过 completion gate，158 个 recorded targets 都被 matched，并且都出现在最终 replication report 里。作者还发布了 Paper-replication 的 Codex / Claude Code skills、12 个 agent-generated case-study workspaces、分析脚本和结果文件。

但这篇论文最谨慎的地方在于，它没有把“matched”宣传成“完全复现”。对于 13 个 standardized numeric anchors，三次运行合计 39 个 anchor-run observations，其中 37 个落在固定的 paper-anchored threshold 内，2 个在这个独立标尺下超出阈值，但仍然在 workspace 自己记录的 target-specific acceptance rule 下被接受。换句话说，同一个 target 可以在某个合理规则下 matched，但在更严格或不同的数字标尺下仍有差异。

这恰恰是工程上最有价值的部分。AI agent 的完成状态不是一个二值标签，而是一组可解释证据：哪些 target 做到了，哪些阈值采用了什么规则，哪些数字在 paper-reported accuracy class 之内，哪些结果只是结构上吻合，哪些缺失来自原论文没有提供 seed、sampled training set、optimizer state 或 preprocessing convention。

### 5. 过程差异比最终标签更重要：耗时、修正和判断都会漂移

虽然 12 次运行都完成，但工作区记录显示，重复运行之间存在明显差异。论文提到，observed elapsed replication time 从 1.2 小时到 13.0 小时不等；PINN-II 和 PINN-I 的 posterior median elapsed time 分别是 6.9 小时和 5.0 小时，而 PIFT 和 SINDy 分别是 2.2 小时和 1.9 小时。即使控制同一篇论文，重复运行的 elapsed replication time 也可能相差约 2 倍。

修正工作也很关键。整个 corpus 里有 25 个 superseded tracked executions，也就是 agent 一开始用于实现或检查 target、后来又被修正工作替换掉的执行记录。其中 21 个出现在两个 PINN paper 里。这说明更难的 agent workflow 不一定只是“跑得久”，而是需要多轮假设测试、失败替换、重新训练、重新比较和重新接受证据。

还有一个容易被忽略的点：acceptance rule 本身也会漂移。不同运行对同一个 paper claim 的判断方式可能不同，有时把它当成 numeric target，有时当成 structural target。论文里 SINDy 的 same-rule fraction 最高，为 19/20；PINN-II 最低，为 5/11。这说明即使所有工作区都完成了，agent 的分解方式、判断规则和证据路径仍然需要被记录下来，否则团队只会看到“完成”，看不到完成背后的不确定性。

### 6. 论文边界：这是方法论样本，不是 agent 复现能力的最终评测

这篇论文的边界需要说清楚。它只研究了 4 篇 scientific machine learning papers，每篇 3 次运行，并且主要使用一个 coding-agent / skill workflow。paper-anchored fidelity 分析也只有 13 个 scalar anchors；对于 distributional / structural targets，未来还需要更严格的独立判断设计。

因此，这篇文章不应该被解读为“AI agent 已经能可靠复现所有科学论文”。更准确的解读是：当我们把复杂任务设计成 persistent workspace + evidence contract + validation gate 时，agent 的工作就从不可审计的聊天输出，变成可以被检查、复盘和改进的工程过程。这才是它对 AI Native Engineering 最有价值的地方。

## 给我们的启示

第一，内部 AI agent workflow 要把“完成标准”外部化。不要让 agent 自己决定“我完成了”，而是让任务有独立的 checklist、test、lint、eval、security check、benchmark comparison、review coverage 或 report coverage。agent 可以建议完成，但 gate 才能接受完成。

第二，复杂任务要有 workspace contract。对于代码迁移、性能优化、线上排障、架构评审、数据分析、实验复现这类工作，建议每次 agent run 都生成固定结构：`manifest` 记录输入和环境，`task-ledger` 记录当前目标和未决问题，`evidence/` 存放运行记录和产物，`provenance/` 连接命令、代码、配置和来源，`comparison/` 记录接受规则，`report.md` 汇总最终结论。这样 review 的对象不是 chat transcript，而是工作区。

第三，AI Native R&D 的关键能力不是“让 agent 写更多”，而是“让 agent 交出可验证研究过程”。如果我们用 agent 做行业研究、技术选型、benchmark、故障分析或竞品复盘，最危险的不是它给不出结论，而是给出一个看似完整但无法追溯的结论。Paper-replication 的启发是：每个结论都应该能追到 source、method、run、comparison 和 caveat。

第四，agent skill 的价值在于把这些规则产品化。昨天我们关注 skill 作为上下文供应链，今天这篇论文说明了 skill 的另一个方向：把复杂工作沉淀成 evidence-producing harness。好的内部 skill 不只是告诉 agent 怎么做，还应该提供目录结构、记录脚本、检查脚本、失败恢复策略和完成 gate。

第五，评估 agent 产出时，不要只看最终 throughput，也要看 correction work。一个 agent 任务可能最终成功，但中间替换了多少次执行、覆盖了多少假设、依赖了多少人工判断、用了多少阈值妥协，这些才决定它能不能规模化进入生产流程。

## 延伸阅读

- Paper-replication release bundle: https://github.com/PredictiveScienceLab/paper-replication-paper
- PaperBench: Evaluating AI's Ability to Replicate AI Research: https://arxiv.org/abs/2504.01848
- CORE-Bench: Fostering the Credibility of Published Research Through a Computational Reproducibility Agent Benchmark: https://arxiv.org/abs/2409.11363
- From Registry to Repository: How AI Agent Skills Are Written, Adapted, and Maintained: https://arxiv.org/abs/2607.00911
- From Conversation to Contribution: Characterizing Coding Agent in Open-Source Software: https://arxiv.org/abs/2607.05677
