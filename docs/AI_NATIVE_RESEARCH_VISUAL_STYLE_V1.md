# AI Native Research Visual Style V1

This is the canonical visual design guideline for all AI Native Research visual cards and research decks. Treat this document as the single source of truth for visual style. Codex and any other generation agent must follow this file before generating images for Feishu or GitHub.

## 1. Design Goal

AI Native Research visual cards are not decorative images. They are structured research artifacts that help readers quickly understand the core framework, evidence, and implications of each article or report.

The desired feeling is: **clean, analytical, premium research card, visually consistent, easy to scan, and suitable for internal knowledge sharing**.

The card should look like it belongs to a continuous research series, not like a one-off AI-generated poster.

## 2. Canonical Style Name

Use this style name in manifests and prompts:

```text
AI Native Research V1
```

When a package says `Follow AI Native Research V1`, it means this document.

## 3. Canvas and Layout

### Default canvas

Use a wide presentation-friendly layout:

```text
16:9 or 16:10 horizontal card
Recommended: 1600 × 900 px or 1600 × 1000 px
```

### Layout structure

A standard card should have four zones:

1. **Header zone**
   - Series label, card number or card role
   - Main title
   - Optional subtitle
   - Source / date metadata if useful

2. **Main content zone**
   - Core framework, flow, table, matrix, or insight blocks
   - This should be the visual center of the card

3. **Evidence / metric zone**
   - Small chips for key metrics, source facts, or signals
   - Use sparingly; avoid clutter

4. **Takeaway zone**
   - One short conclusion sentence
   - Usually placed at bottom or bottom-right

## 4. Visual Style

### Overall tone

- Clean and structured
- High information density, but not crowded
- More like a strategy/research slide than a marketing poster
- Avoid cyberpunk, neon, 3D renders, cartoons, photorealistic scenes, or decorative backgrounds
- Avoid random icons that do not add meaning

### Background

Use a calm, light background:

```text
warm off-white / very light gray / pale cream
```

Avoid pure black or dark full-background cards unless specifically requested.

### Cards and containers

Use rounded rectangles and modular panels:

- Soft shadows or subtle borders
- Clear spacing between modules
- Consistent corner radius
- Avoid heavy gradients
- Use thin dividers for structure

### Visual rhythm

Prefer one of these structures:

- 3-column or 4-column comparison
- horizontal maturity flow
- circular/loop flow
- 2×2 or 2×3 insight grid
- layered stack: foundation → workflow → outcome

## 5. Color System

Use a restrained, consistent palette.

### Primary colors

- Deep navy / slate blue for titles and structural headers
- Soft blue for workflow / platform / system modules
- Soft purple for AI / agent / augmentation modules
- Soft green for verification / outcome / productivity modules
- Warm amber or orange only for transition, warning, or key shift

### Avoid

- Excessive rainbow palettes
- High-saturation neon colors
- Random red/green contrast unless used as a deliberate warning/success signal
- Overly dark backgrounds

## 6. Typography

### Chinese readability is critical

Chinese text must be clear, legible, and not hallucinated. If the image generation system is weak at Chinese typography, use one of these approaches:

1. Generate the card layout with simplified, minimal Chinese text.
2. Prefer short labels rather than long paragraphs.
3. Keep text blocks large enough to read.
4. If possible, render final text with deterministic tooling such as HTML/SVG/Canvas/Python/PPT rather than relying entirely on image generation text rendering.

### Font style

- Sans-serif
- Modern, neutral, clean
- No handwritten fonts
- No decorative display fonts

### Text hierarchy

Use consistent hierarchy:

```text
Series label: small uppercase or small Chinese label
Title: largest text
Subtitle: medium text
Section labels: medium-bold
Body labels: short and readable
Metric chips: compact but legible
```

## 7. Content Density Rules

Each card should be understandable in 10–20 seconds.

### Good

- 1 main idea per card
- 3–6 modules
- 3–6 metric chips
- Short phrases
- One explicit takeaway

### Avoid

- Full paragraphs inside images
- Too many arrows
- Dense tables with tiny text
- Mixing multiple unrelated frameworks in one card
- More than 8 major blocks unless it is a research deck overview

## 8. Standard Card Types

### 8.1 Executive Summary Card

Purpose: one-minute overview.

Recommended layout:

```text
Header: title + source
Center: transformation flow or 3–5 insight blocks
Bottom: key metrics + one takeaway
```

### 8.2 Workflow / Loop Card

Purpose: show an operating model.

Recommended layout:

```text
Goal → Context → Tools → Execution → Review → Memory → Automation → Reuse
```

Use arrows or a loop. Keep each node short.

### 8.3 Engineering Implications Card

Purpose: convert source content into practical implications.

Recommended layout:

```text
2×3 grid of implications
Each block: short title + one-line meaning
Bottom: one actionable takeaway
```

### 8.4 Tier 0 Research Deck Cards

For official reports, white papers, and flagship sources, create a multi-card deck instead of forcing everything into one framework card.

Typical deck:

1. Executive Summary
2. Key Findings / Evidence
3. Operating Model / Workflow
4. Engineering Implications
5. Optional: Risk / Governance / Metrics

Do not number Tier 0 deck cards as global Framework-00x. They belong to the report package.

## 9. Required Metadata on Each Card

Include a small metadata strip when possible:

```text
AI Native Research
Source: <publisher or report>
Date: <YYYY-MM-DD>
Card: <role or number>
```

This creates series continuity.

## 10. Prompting Pattern for Image Generation

When using an image generation tool, use this prompt structure:

```text
Create a clean horizontal research infographic card in the AI Native Research V1 style.
Use a warm off-white background, deep navy headings, soft blue/purple/green accent panels, rounded modular cards, subtle borders, and a clear premium strategy-research layout.
Chinese text must be minimal, crisp, and readable.
Do not use decorative 3D objects, neon colors, cyberpunk style, cartoons, or photo-realistic scenes.

Title: <title>
Subtitle: <subtitle>
Source metadata: <source/date/card role>
Main structure: <flow/table/grid>
Key data chips: <metrics>
Takeaway: <one sentence>
```

## 11. Deterministic Generation Recommendation

If Codex has access to deterministic rendering tools, prefer generating cards with HTML/SVG/Canvas/PPT/Python over purely prompt-based image generation. This reduces Chinese text errors and makes visual consistency easier.

Recommended deterministic approach:

1. Build an HTML or SVG template for AI Native Research V1.
2. Fill in card title, subtitle, modules, metric chips, and takeaway from the `*.spec.md` file.
3. Render to PNG at 1600×900 or 1600×1000.
4. Use the generated PNG in Feishu.
5. Optionally commit the PNG back to the same package directory.

## 12. Quality Checklist

Before publishing, check:

- Title is readable at preview size.
- Chinese text has no broken characters or hallucinated words.
- The card follows the same color and layout language as previous AI Native Research cards.
- The card has one clear main idea.
- Metrics are traceable to the article/package.
- The card is useful as a supplement to the article, not a replacement for the article.
- The card does not overload readers with too much text.

## 13. Current Approved Style Summary

The approved style is:

```text
Clean horizontal infographic / research card
Warm light background
Deep navy headings
Soft blue, purple, green, and amber accents
Rounded modular panels
Concise Chinese labels
Metric chips
One central flow or framework
One short takeaway
Series metadata strip
Readable, premium, structured, non-decorative
```

This document supersedes any earlier informal style descriptions in chat history.
