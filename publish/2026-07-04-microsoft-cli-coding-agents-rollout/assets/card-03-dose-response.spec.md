# Visual Card Spec — card-03-dose-response

## Title

使用强度决定产出曲线

## Purpose

Visualize the outcome study: merged PR lift scales with weekly use intensity, and the headline 24% lift should be treated as throughput evidence, not quality proof.

## Layout

Use a simple ascending curve or stepped bar chart.

Main data points:

- Overall adopter lift: ≈ +24% merged PRs over the four-month window.
- Dose-response:
  - 0 days/week: reference
  - 3 days/week: +15.0% merged PR lift
  - 5+ days/week: +50.1% merged PR lift

Small side panel: Tool comparison in single-tool subset.

- Claude Code any-use week: +11.4% merged PR lift
- Copilot CLI any-use week: +24.9% merged PR lift
- Caution: likely affected by task mix and Microsoft/GitHub workflow fit; do not read as universal tool ranking.

Bottom caution strip: “Merged PR = throughput proxy；还需要质量、复杂度、review load、rollback 等指标。”

## Visual style

Use chart-like visual language with concise labels. Do not overload with confidence intervals unless space allows. Keep the caution visible.

## Footer attribution

Source: Microsoft / arXiv, 2026-07-01. Outcome is merged PRs within a 28-day merge window.
