# Source Notes — 2026-06-30

## Daily scan summary

Today's workflow intentionally avoids repeating the already-published 2026-06-29 OpenAI / Codex agentic work package. The scan focused on primary or near-primary sources from frontier AI and engineering organizations, recent research papers, and high-signal engineering/security writeups from the previous 14 days.

## Selected primary source

- Title: Detecting AI Coding Agents in Open Source: A Validated Multi-Method Census of 180 Million Repositories
- Authors: Arsham Khosravani, Audris Mockus
- Source: arXiv
- URL: https://arxiv.org/abs/2606.24429
- PDF: https://arxiv.org/pdf/2606.24429
- Published: 2026-06-23
- Selection status: selected as main article
- Why selected: it provides a validated, multi-method measurement framework for AI coding agent adoption in open source, with 180M+ repository scope and concrete implications for AI Native Engineering governance.

## Tier-0 / flagship scan notes

- OpenAI / arXiv: The Shift to Agentic AI: Evidence from Codex, published 2026-06-25. High-value Tier-0 source, but already published in the 2026-06-29 Feishu article, so excluded from today's main selection.
- OpenAI: Codex-maxxing for long-running work, published 2026-06-22. High-value supporting white paper, already used in the prior OpenAI/Codex article, so excluded.
- GitHub / Microsoft / Anthropic / Google official sources: no fresher, stronger official flagship report was selected during this run for the specific AI Native Engineering daily article.
- Selected source is treated as Tier 0 Special Attention because it is a major methodology/census paper directly affecting how AI coding adoption, productivity, and supply-chain risk should be measured.

## Other recent candidates considered

1. Mozilla 0din / Tom's Hardware coverage: AI coding agents can be tricked into installing malware via clean-looking GitHub repositories. High operational relevance for agent security, but the accessible source found was secondary coverage rather than the original primary report.
2. Business Insider: AI writes a lot of software; human code review is starting to disappear. Interesting trend signal from Cursor, but less primary and less methodologically deep than the selected arXiv paper.
3. arXiv: AIDev: Studying AI Coding Agents on GitHub. Strong dataset paper and used as an extension/reference, but not within the latest 14-day window and already serves as a baseline comparison in the selected paper.
4. arXiv: Agentic Much? Adoption of Coding Agents on GitHub. Important prior work, but older and PR-centric; used as context rather than today's main article.

## Source-aligned key facts to preserve

- The paper analyzes three World of Code snapshots from December 2024 to April 2026 across 180M+ Git repositories.
- Detection combines four trace types: centralized bot accounts, commit-message signatures, distributed human attribution, and configuration-file-only/silent adoption.
- Claude Code bot-account lookup alone finds 28,154 commits in V2510, while multi-method union finds 850,157 commits, implying roughly a 30x relative-recall gap.
- By V2604, commit-attributed agents collectively generate 320K+ commits/month.
- Claude Code leads with 886,122 commits across 17,295 projects, and Claude also appears as a dominant silent/config-file agent in 21,078 projects.
- AIDev comparison shows PR-based and commit-based channels capture nearly disjoint agent populations and different work profiles.
- Adoption timing is bimodal: born-with-AI projects versus legacy integration years after project start.
- Velocity and quality results are descriptive, not causal; the paper explicitly warns against treating before-after changes as effect sizes.
- Future work points toward standardized AI attribution metadata for Git commits.
