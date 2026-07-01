# Card 03 Spec — 从工程师到 agent portfolio manager

## Purpose

Explain the new human role implied by parallel and long-running agents: dispatch, monitor, review, integrate.

## Style

Follow `docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md`. Use AI Native Research V1. Clean research-slide look. No sci-fi visuals.

## Canvas

1600 × 900 px, horizontal 16:9.

## Layout

Header zone:
- Series label: AI Native Engineering · Workflow Shift
- Main title: 从工程师到 agent portfolio manager
- Subtitle: 重度用户不只是“聊更多”，而是在管理多条 agent 工作流

Main content zone: central workflow diagram with five steps.

Step 1: Dispatch / 派工
- 把目标拆成 agent 可执行任务
- 明确上下文、边界、验收标准

Step 2: Parallelize / 并行
- 多个 agent 同时跑不同 thread
- 适合 investigation、测试补齐、迁移草稿、文档生成

Step 3: Monitor / 监控
- 看 runtime、阻塞点、需要澄清的问题
- 不要求每一步人工介入，但要保留观察面板

Step 4: Review / 审查
- 测试、静态检查、diff review、事实核查
- 重点看可交付性，而不是模型回答是否流畅

Step 5: Integrate / 整合
- 合并到代码库、文档、决策或工作流
- 形成可复用 skill / checklist / runbook

Evidence side panel:
- OpenAI users: 28.6% managed 5+ concurrent agents during observed week
- Median OpenAI worker: 2.5 Codex runtime hours on 2026-06-11
- 99th percentile OpenAI worker: ~71 agent-hours/day

Takeaway zone:
- 未来工程能力的上限，取决于人如何组织、验证和整合 agent work。

## Visual notes

Use a horizontal flow or loop. Include one small “human supervisor” node above multiple agent workstreams, but keep it abstract: boxes, lines, queues, checkmarks. Avoid anthropomorphic robot illustrations.
