# Visual Card Spec — card-01-rollout-funnel

## Title

Rollout 三段漏斗：adoption / retention / outcome

## Purpose

Explain why AI coding agent rollout cannot be measured by license activation alone. The Microsoft paper separates first use, retained use, and merged PR outcome.

## Layout

Use a horizontal three-stage funnel or pipeline.

1. Adoption / first use
   - 指标：第一次打开 Copilot CLI
   - 驱动：peer / manager 可见使用
   - 提醒：好奇心不等于采用

2. Retention / sustained use
   - 指标：首次使用后 14 天内至少 5 天活跃
   - 驱动：真实 PR 工作流、baseline coding activity
   - 提醒：有替代工具的人可能更快流失

3. Outcome / merged PR throughput
   - 指标：28 天内 merged PR
   - 发现：adopters ≈ +24% merged PR
   - 提醒：PR throughput 不等于质量或业务价值

## Visual style

Clean, dense, internal research-card style. Use minimal icons: doorway for first use, loop for retention, PR merge icon for outcome. Avoid vendor logos unless the existing visual style allows small text labels.

## Footer attribution

Source: Microsoft / arXiv, 2026-07-01, `Adoption and Impact of Command-Line AI Coding Agents`.
