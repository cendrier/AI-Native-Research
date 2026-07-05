# Card 03 — AI 写得更快，瓶颈下移到 Review

## Purpose

Make the paper’s main operational warning memorable: AI increases code/PR throughput faster than the human review system can scale.

## Suggested layout

A two-column before/after comparison or bottleneck diagram:

Left: Writing / PR production
- AI-authored PRs: ~90%
- Raw PR volume: ~3.1×

Right: Review system
- Reviewer pool: ~1.5×
- Per-reviewer load: ~2.0×
- Human review: ~89% → ~68%
- Automated AI review: ~19% → ~84%
- Substantive human reviews: ~39% → ~21%

Center or bottom message:

> AI 没有消除质量控制，只是把质量控制推到了 review、eval 和 governance 层。

## Visual style

Use clear visual hierarchy. Use arrows to show the imbalance between PR production growth and reviewer capacity growth. Keep all percentages legible.

## Footer attribution

Source: AI Writes Faster Than Humans Can Review, arXiv, 2026-07-02.
