# Codex Feishu Publishing Runbook

This runbook defines how Codex should continue after ChatGPT pushes a daily publish package into the `AI-Native-Research` repository.

## 1. Role Split

### ChatGPT

ChatGPT is responsible for:

- Daily research and source selection
- Article drafting in Chinese
- Source metadata
- Codex handoff YAML
- Source image manifest
- Visual card manifest
- Visual card specs
- Pushing the text package to GitHub

### Codex

Codex is responsible for:

- Watching or reading the GitHub package
- Generating visual cards from specs
- Fetching original source images when listed
- Creating the Feishu document
- Uploading the document to the internal Feishu space
- Returning publication status
- Optionally writing generated PNG cards and status files back to GitHub

## 2. Trusted Inputs

For every package, Codex should treat these files as authoritative:

```text
publish/<date-slug>/README.md
publish/<date-slug>/metadata.yaml
publish/<date-slug>/source.md
publish/<date-slug>/codex-handoff.yaml
publish/<date-slug>/assets/source-images.yaml
publish/<date-slug>/assets/visual-card-manifest.yaml
publish/<date-slug>/assets/card-*.spec.md
```

For visual style, Codex must always read:

```text
docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md
```

This file is the only canonical source for card style. Do not rely on chat history.

## 3. Publishing Steps

1. Locate the newest package under `publish/` or use the package path explicitly provided by the user.
2. Read `codex-handoff.yaml`.
3. Read `README.md` as the article body.
4. Read `assets/source-images.yaml`.
   - If it contains original image URLs, fetch them and insert them into the specified sections.
   - If it is empty, skip this step.
5. Read `assets/visual-card-manifest.yaml`.
6. For each card in the manifest:
   - Read its `*.spec.md` file.
   - Read `docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md`.
   - Generate the PNG card using the approved visual style.
   - Save the PNG to the package `assets/` directory.
7. Create the Feishu document using `README.md` as the body.
8. Insert visual cards at the requested sections.
9. Preserve all original source links.
10. Generate a table of contents if Feishu supports it.
11. Publish to the configured Feishu space and folder.
12. Write a `publish-status.yaml` file back to the package directory.

## 4. Feishu Document Rules

- Use the title from `codex-handoff.yaml`.
- Preserve the article structure from `README.md`.
- Use normal paragraph spacing; do not create excessive line breaks.
- Keep original links clickable.
- Use images inline near the matching section, not all at the end.
- The visual cards supplement the text; they do not replace the article.

## 5. Visual Card Generation Rules

Before generating any card, read:

```text
docs/AI_NATIVE_RESEARCH_VISUAL_STYLE_V1.md
```

Then read the package-specific spec file, for example:

```text
publish/2026-06-29-openai-agentic-work/assets/card-01-executive-summary.spec.md
```

The package spec provides card content. The global style guide provides visual rules.

If using an image model, use the prompt pattern from the style guide. If possible, prefer deterministic rendering through HTML/SVG/Canvas/PPT/Python to keep Chinese text stable.

## 6. Required Output Files

After successful publishing, write:

```text
publish/<date-slug>/publish-status.yaml
```

Suggested successful status:

```yaml
status: published
published_at: "<timestamp>"
feishu_url: "<url>"
cards_generated:
  - assets/card-01-executive-summary.png
  - assets/card-02-long-running-agent-loop.png
  - assets/card-03-engineering-implications.png
notes: "Published by Codex from ChatGPT handoff."
```

Suggested failure status:

```yaml
status: failed
failed_at: "<timestamp>"
error_stage: "<github|card_generation|feishu_upload|permission|unknown>"
error_message: "<specific error>"
```

## 7. Current Package to Test

Use this package for the first end-to-end test:

```text
publish/2026-06-29-openai-agentic-work/
```

Expected Feishu title:

```text
2026-06-29｜OpenAI 最新研究：AI Coding 正在进入 Agentic Work 时代
```

Expected visual cards:

```text
assets/card-01-executive-summary.png
assets/card-02-long-running-agent-loop.png
assets/card-03-engineering-implications.png
```
