# Visual Card Spec — card-04-measurement-playbook

## Title

从 PR throughput 到质量控制

## Purpose

Turn the Microsoft study into a practical internal measurement playbook for AI coding agent rollout.

## Layout

Use a 2-column checklist or layered stack.

Column 1: Rollout funnel

- Eligible population
- First use
- Retained use
- Weekly active days
- Agent-assisted PR
- Merged PR

Column 2: Quality / governance guardrails

- Review cycle time
- Review comments / rework
- Test coverage delta
- Revert / rollback
- Incident / defect rate
- Security finding
- Complexity / maintainability
- Reviewer load
- Unit task cost

Bottom principle: “不要把 activation 当 adoption；不要把 PR 数当价值。”

## Visual style

Dense but readable, Feishu-friendly. Use checkmarks sparingly. Emphasize this as an internal operating dashboard rather than a poster.

## Footer attribution

Inspired by Microsoft / arXiv 2026-07-01 field study and AI Native Engineering rollout practice.
