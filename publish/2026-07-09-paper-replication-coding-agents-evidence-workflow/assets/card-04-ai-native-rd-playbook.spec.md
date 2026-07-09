# Visual Card 04 — 内部 AI Native R&D Workflow Playbook

## Purpose
Translate the paper into practical internal engineering guidance.

## Layout
Use a vertical checklist / playbook card with five blocks.

Block 1: "1. Define targets"
- 每个任务拆成可验收 target
- 记录 source、owner、scope、acceptance rule

Block 2: "2. Create workspace contract"
- manifest
- task-ledger
- evidence/
- provenance/
- comparison/
- report.md

Block 3: "3. Record every run"
- command / environment / output hash
- code / config / seed
- failed and superseded executions

Block 4: "4. Gate completion outside the agent"
- tests / evals / benchmarks
- review coverage
- risk and caveat checklist

Block 5: "5. Review process, not only output"
- 看证据链
- 看修正路径
- 看不确定性
- 看是否可复跑

## Key message
"把 agent 当成执行者，把 workspace 当成系统记录，把 gate 当成验收者。"

## Visual style
Clean checklist, subtle icons, light background. Use concise wording and enough spacing for mobile readability.
