# Card 02 — Provenance 盲区会变成 Incident 盲区

## Purpose

Explain why AI-generated code visibility is a production risk, not just a documentation issue.

## Visual layout

Create a two-layer diagram.

Top layer: **开发阶段的证据链**

- Prompt / task
- Tool / model
- Files changed
- Tests / policy gates
- Human owner
- Reviewer / approver

Bottom layer: **Incident 之后要回答的问题**

- 这段代码是不是 AI-assisted？
- agent 为什么这样改？
- 当时哪些检查通过了？
- 谁承担 merge responsibility？
- 哪个 guardrail 失效了？

Connect the two layers with a central warning badge:

**没有 provenance，就没有 accountability**

## Required Chinese title

**AI Code Provenance：不是标签，是证据链**

## Required metric callouts

- 43% 难以区分 AI-generated / human-written code
- 34% 在 incident 中无法判断 AI code 是否参与
- 73% 担心长期可维护性

## Design notes

- Use a ledger / trace line metaphor.
- Avoid dark cyber-security clichés; keep clean and executive-friendly.
- Show blind spot as a gap in the trace line between PR and incident.
