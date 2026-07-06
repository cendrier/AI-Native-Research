# Card 03 — 不要让 Builder 审自己

## Purpose

Show the recommended AI Native Engineering architecture: generation and verification should be separated.

## Visual layout

Use a system architecture diagram with three lanes:

### Lane 1 — Builder Layer

- IDE / CLI coding agent
- Test generation agent
- Refactor / migration agent
- Documentation agent

### Lane 2 — Independent Verification Layer

- CI tests
- static analysis
- security / dependency scan
- architecture rules
- policy-as-code
- risk classifier
- owner routing

### Lane 3 — Accountability Layer

- PR provenance metadata
- evidence links
- human owner
- audit trail
- incident traceability

Add a red-line rule between lane 1 and lane 2:

**同一个系统可以生成建议，但不能单独给自己放行。**

## Required Chinese title

**AI Coding 的下一层基础设施：独立验证层**

## Required subtitle

生成可以多工具，验证必须统一、可审计、可路由。

## Design notes

- Use arrows from Builder → Verification → Accountability → Merge/Deploy.
- Make it feel like an engineering platform map, not a generic AI illustration.
- Avoid personified robots.
