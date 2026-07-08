# Visual Card 01 — Skill Supply Chain：从 Registry 到 Repository

## Purpose

Explain the paper's core framing: AI agent skills are reusable context dependencies that flow from public registries into local repositories, where they may be copied, adapted, and maintained.

## Layout

Use a left-to-right pipeline with four large blocks:

1. Public Registry
   - label: `skills.sh`
   - metric: `18,463 centralized skills`
   - note: `通用能力 / 可复制 / 上游源`
2. GitHub Repositories
   - metric: `23,199 personal-use skills`
   - metric: `5,876 repositories`
   - note: `项目上下文 / CI / 测试 / 配置`
3. Linkage Recovery
   - metric: `3,709 reuse links`
   - note: `name 字段 + 内容相似度`
4. Engineering Artifact
   - label: `SKILL.md + scripts + references + assets`
   - note: `agent 会读取并执行，不只是人类文档`

Add a bottom caption:

> 结论：Skill 已经像依赖一样被复制和复用，需要 owner、版本、验证和 drift 控制。

## Visual style

- Light background.
- Use simple dependency-chain / package icons, not robot icons.
- Use arrows between blocks.
- Highlight `SKILL.md` as the central object.
- Keep all numbers large and easy to read.

## Data fidelity

Use exact numbers from the paper: 18,463, 23,199, 5,876, 3,709. Do not add unsupported extrapolations.