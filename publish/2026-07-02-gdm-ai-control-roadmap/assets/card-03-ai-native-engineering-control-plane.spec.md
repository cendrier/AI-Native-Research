# Visual Card Spec: AI Native Engineering Control Plane

## Card id

card-03-ai-native-engineering-control-plane

## Insert location

After heading: `给我们的启示`

## Purpose

Translate Google DeepMind's AI Control Roadmap into a practical AI Native Engineering control plane for teams using coding agents in real development workflows.

## Core message

The control plane for AI coding agents should cover the full lifecycle: task intake, execution, code change, review, deployment, monitoring, response, and learning.

## Layout

Use a 16:9 architecture-style research card. Title: `AI Native Engineering Control Plane`.

Main diagram: a left-to-right flow with seven nodes:

1. `Task Intake` — intent, scope, risk level
2. `Agent Identity` — separate actor, attribution
3. `Sandboxed Runtime` — workspace, tools, network, secrets
4. `Action Telemetry` — files, commands, API calls, diffs
5. `Policy & Monitor` — trusted reviewer, anomaly detection, PR monitor
6. `Response` — block, resample, escalate, rollback
7. `Learning Loop` — incident review, policy update, evals

Above the flow, add a small label: `Beyond human code review`.

Below the flow, add metric chips: `coverage`, `recall`, `TTR`, `unsafe-action block rate`, `rollback rate`.

## Visual style

Follow `docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md`. Use clean modular architecture blocks, generous spacing, and analytical tone. No cloud vendor logos.

## Text constraints

Short labels only. Avoid dense paragraphs. Make the flow easy to scan in 5 seconds.