# Card 02 — AI-DLC：AI 执行，人类监督

## Goal

Visualize the AI-Driven Development Lifecycle as the workflow backbone behind AWS FDE.

## Layout

Use a circular or three-stage flow.

Stage 1: Inception
- Business intent
- AI generates requirements and stories
- Team validates questions and assumptions

Stage 2: Construction
- AI proposes architecture, domain model, code, tests
- Humans make technical and architectural decisions
- Team validates quality and business fit

Stage 3: Operations
- AI uses accumulated context for infra and deployment
- Humans supervise risk, release, rollback, and runbooks

Loop label around all stages:
AI plans → asks clarification → implements → humans verify → context compounds

## Design notes

- Make human oversight visible, not hidden.
- Show that AI stores persistent context and artifacts in the repository.
- Keep labels concise and readable in Feishu.

## Footer

Source: AWS DevOps & Developer Productivity Blog, 2025-07-31
