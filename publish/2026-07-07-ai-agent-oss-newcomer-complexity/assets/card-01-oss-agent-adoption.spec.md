# Card 01 — 如何识别 AI Agent Adoption

## Goal

Explain the paper's measurement design in one visual: visible adoption signal, identified sample, and causal comparison.

## Recommended layout

Use a 3-step horizontal flow:

1. **Signal**
   - `.cursorrules`
   - `CLAUDE.md`
   - first commit date = visible adoption date
   - note: adoption proxy, not usage intensity

2. **Sample filter**
   - 1,888 harvested adopters
   - 603 adopters with ≥6 months pre-history
   - 1,784 matched never-adopter controls
   - remove bot / agent accounts by numeric GitHub user id

3. **Estimation**
   - matched controls
   - difference-in-differences
   - check pre-trends
   - outcome families: newcomer inflow, first PR handling, retention, beginner-task supply, code complexity

## Main headline

**先把 adoption 量对，再谈 AI 的影响**

## Visual details

- Use a clean pipeline diagram, left to right.
- Show `.cursorrules` and `CLAUDE.md` as file chips.
- Use one small warning label: “visible adoption ≠ usage intensity”.
- Keep numbers large and readable.
- Avoid implying the study directly observes all AI usage.

## Insert location

After `重点内容` subsection 2.
