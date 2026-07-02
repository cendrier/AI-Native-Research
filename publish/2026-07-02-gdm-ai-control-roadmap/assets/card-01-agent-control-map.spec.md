# Visual Card Spec: Agent Control Map

## Card id

card-01-agent-control-map

## Insert location

After heading: `⭐ Tier 0 Special Attention`

## Purpose

Show why AI coding agents need a control layer beyond model alignment. The card should make the conceptual shift immediately clear: from “assistant writes code” to “agent acts inside systems and therefore needs governance.”

## Core message

AI agents are valuable because they can act. The same ability requires a system-level control plane: identity, permissions, monitoring, interception, rollback, and shutdown.

## Layout

Use a clean 16:9 research card. Top left: title `From Coding Assistant to Controlled Agent`. Under it, one-sentence subtitle: `Agentic engineering needs a control layer outside the model.`

Center diagram: three horizontal layers.

Layer 1: `Model Alignment` with small labels `training`, `policy`, `helpful / safe behavior`.

Layer 2: `Agent Runtime` with labels `tools`, `codebase`, `terminal`, `cloud resources`, `internal docs`.

Layer 3: `AI Control Layer` with labels `identity`, `least privilege`, `sandbox`, `telemetry`, `monitoring`, `real-time block`, `rollback`, `shutdown`.

Right side: a small callout titled `Why now?` with three bullets: `agents execute actions`, `human review does not scale`, `control must be measurable`.

Bottom footer: `Source: Google DeepMind — GDM AI Control Roadmap, 2026`.

## Visual style

Follow `docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md`. Keep it clean, analytical, premium, and suitable for internal knowledge sharing. Avoid sci-fi robots, dark cyberpunk, alarms, skulls, or sensational security imagery.

## Text constraints

Use English labels on the card because the source terms are English, but keep the text short and readable. No paragraph blocks. Use clear hierarchy and enough whitespace.