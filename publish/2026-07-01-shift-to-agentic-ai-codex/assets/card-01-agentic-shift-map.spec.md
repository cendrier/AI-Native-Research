# Card 01 Spec — 从聊天到派工

## Purpose

Explain the central conceptual shift in the paper: conversational AI is organized around asking and answering; agentic AI is organized around delegated production.

## Style

Follow `docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md` exactly. Use AI Native Research V1. Clean analytical research card, light background, modular panels, no cyberpunk, no decorative AI robot imagery.

## Canvas

1600 × 900 px, horizontal 16:9.

## Layout

Header zone:
- Series label: AI Native Engineering · Tier 0
- Main title: 从聊天到派工
- Subtitle: Agentic AI 的单位不是“对话”，而是“被委托的工作流”

Main content zone: two-column comparison with a center arrow.

Left column title: Conversational AI
- 交互单位：一次 chat / turn
- 用户动作：提问、补充、追问
- 模型产出：回答、建议、内容草稿
- 典型指标：活跃用户、消息数、使用时长
- 风险：看起来很热闹，但不一定进入生产流程

Center arrow label:
- Shift: asking → delegation
- 从“帮我想”到“帮我做完并可验证”

Right column title: Agentic AI
- 交互单位：delegated workflow
- 用户动作：派工、设定边界、等待执行、审查结果
- 系统产出：代码变更、文档、数据分析、配置、验证结果
- 典型指标：任务复杂度、runtime、并行度、workflow reuse、production output
- 风险：权限、验证、回滚、责任边界

Evidence chips:
- Codex WAU >5× in H1 2026
- OpenAI 内部 Codex output token share: 99.8%
- 26.6% active users used skills by 2026-06-11

Takeaway zone:
- 真正的 adoption，不是更多聊天，而是更多可审查、可复用、可交付的工作被委托出去。

## Visual notes

Use two large rounded rectangles. Use a subtle arrow or flow line between them. Keep Chinese text crisp and readable. Use minimal icons only if they clarify meaning: chat bubble for left, workflow nodes for right.
