# Source Notes — 2026-07-01

## Daily scan window

- Fresh article/report window: previous 14 days, approximately 2026-06-17 through 2026-07-01.
- Priority: primary sources, flagship reports, methodology papers, engineering case studies, and evidence-based writing related to AI-native organizations, AI coding, developer productivity, engineering effectiveness, and agentic engineering.

## Tier-0 scan result

Selected Tier-0 source:

- The Shift to Agentic AI: Evidence from Codex
- Source: arXiv
- Publication date: 2026-06-25
- Abstract URL: https://arxiv.org/abs/2606.26959
- PDF URL: https://arxiv.org/pdf/2606.26959
- Reason for selection: major empirical/methodology paper with OpenAI Codex usage data across individual users, organizational users, and OpenAI workers. The paper directly addresses the transition from conversational AI to agentic work delegation and gives concrete measurement dimensions useful for AI Native Engineering.

## Key source facts extracted

- Codex weekly active users increased more than fivefold in the first half of 2026.
- Codex share of output tokens across Codex + ChatGPT reached 99.8% among OpenAI workers, 63.3% among organizational users, and 16.5% among individual users.
- Recent 28-day active-user usage of Codex reached 97.9% among OpenAI workers, 17.3% among organizational users, and 0.7% among individual users.
- Codex usage is framed as delegated production rather than consultation: debugging, refactoring, validation, app configuration, document generation, data analysis, and broader workflow execution.
- Individual-user task complexity increased substantially: users submitting at least one task estimated at one or more human hours rose from 35.4% in Dec 2025 to 70.2% in May 2026; tasks estimated at eight or more human hours rose from 2.1% to 25.6%.
- In the week before 2026-06-11, 28.6% of OpenAI users managed five or more concurrent agents at some point.
- On 2026-06-11, median OpenAI employee Codex task runtime was 2.5 hours; the 99th percentile had about 71 agent-hours/day.
- Skill use rose from 5.4% on 2026-03-01 to 26.6% on 2026-06-11; within OpenAI, 96.2% of active Codex users invoked at least one skill.

## Figures worth using or redrawing

- Figure 1: Codex usage relative to ChatGPT by user population.
- Figure 2: Growth in active Codex users by account type and persona.
- Figure 6: Model-estimated complexity of Codex turns among Individual account users.
- Figure 9: Codex turn concurrency.
- Figure 11: Skill use over time and by account category.
- Figure 12: Change in median output tokens per person by OpenAI job function.

For Feishu, prefer generated visual cards that explain these concepts in Chinese rather than directly embedding all original figures. Use selected source figures only when they materially support the argument.

## Other candidates considered

1. AWS commits $1 billion toward new unit for embedded AI engineers
   - Source: Reuters
   - Date: 2026-06-30
   - URL: https://www.reuters.com/business/retail-consumer/amazons-aws-commits-1-billion-toward-new-unit-embedded-ai-engineers-2026-06-30/
   - Reason not selected as main article: important industry signal, but secondary news coverage and less methodologically rich than the Codex paper.

2. OpenAI Codex usage-limit incident coverage
   - Source: Business Insider
   - Date: 2026-06-30
   - Reason not selected: useful operational lesson about background agent cost/accounting, but more incident coverage than durable engineering-methodology material.

3. Human review decline / Cursor coverage
   - Source: Business Insider
   - Date: 2026-06-29
   - Reason not selected: relevant to AI code review, but not as primary-source-rich in this scan.

## Editorial decision

Publish one deep Tier-0专题 article today. Do not create a second standalone Feishu article because the selected Tier-0 paper is dense enough and overlaps with the daily AI coding theme. Include AWS forward-deployed AI engineers as an extension-reading signal instead of a separate article.
