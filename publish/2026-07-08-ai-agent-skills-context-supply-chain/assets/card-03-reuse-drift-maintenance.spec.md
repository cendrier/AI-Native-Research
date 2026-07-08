# Visual Card 03 — 一次性复制带来的 Drift 风险

## Purpose

Visualize the main operational risk from the paper: many reused skills are copied nearly verbatim, then local and upstream versions drift apart without a dependency-management loop.

## Layout

Use a split diagram with two paths:

### Top path: Ideal dependency loop

`Registry skill` → `版本化引入` → `本地配置` → `验证` → `上游更新提醒` → `同步 / 再验证`

### Bottom path: Observed common pattern

`Registry skill` → `Copy once` → `本地静默漂移` → `上游变了但本地没跟` → `agent 执行过期规则`

Place four metric tiles on the right:

- `70.3%` — reuse pair 相似度 ≥ 0.99，近乎原样复制
- `53%` — reused skills 采用后没有本地更新
- `40.2%` — 未本地更新的 reused skills 中，上游后来更新过
- `62.3%` — 本地和上游都变时，多数独立分叉而非同步

Bottom warning banner:

> 过期 README 只是被读；过期 SKILL.md 可能被 agent 执行。

## Visual style

- Use clean flow arrows and small alert icons.
- The ideal path should look controlled; the observed path should show drift gaps.
- Keep the warning banner prominent but not alarmist.

## Data fidelity

Use the exact metrics above. Do not imply causality beyond the paper's observed public skill reuse patterns.