# Card 04 Spec — AI Native Engineering 落地手册

## Purpose

Translate the paper into a practical organizational playbook for AI Native Engineering teams.

## Style

Follow `docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md`. Use AI Native Research V1. Clean, analytical, internal strategy-card style.

## Canvas

1600 × 900 px, horizontal 16:9.

## Layout

Header zone:
- Series label: AI Native Engineering · Playbook
- Main title: 从工具上线到 workflow redesign
- Subtitle: Agentic AI 的组织收益来自流程、验证和复用

Main content zone: 2×3 grid of operating principles.

Principle 1: 任务拆分
- 把大目标拆成可委托、可验证、可回滚的小任务

Principle 2: 上下文资产
- 代码库说明、目录结构、数据源、团队规则、历史决策要可被 agent 读取

Principle 3: 自动验证
- 测试、lint、typecheck、安全扫描、基准结果作为 agent output 的 gate

Principle 4: Review 队列
- 人类重点审查意图、风险、边界、异常和最终可交付性

Principle 5: Skills / Plugins
- 把高频流程写成 SKILL.md / plugin / runbook，而不是每次重新 prompt

Principle 6: 新指标体系
- agent-hours、delegated task size、review latency、pass rate、rollback rate、skill reuse

Evidence chips:
- Skills use: 5.4% → 26.6% active Codex users
- OpenAI skill use: 96.2%
- Complex tasks: 8h+ prompts 2.1% → 25.6%

Takeaway zone:
- AI Native Engineering 的核心，不是“让每个人都用 AI”，而是让组织能安全地委托、验证和复用 AI work。

## Visual notes

Use six modular cards with short labels and one-line explanation. Keep text large and readable. Add a subtle bottom bar: “Measure work delegated, not chats generated.”
