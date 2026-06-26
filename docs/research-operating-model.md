# AI Native Research｜Operating Model

## 项目定位

AI Native Research 是一个面向 AI Native 组织、研发效能和工程方法论的研究型知识库。目标不是收集文章，而是把高质量信息沉淀为可复用的研究资产：brief、case study、framework card 和 pattern。

## 核心原则

1. **Less but Better**：每天只归档真正值得长期保留的内容。
2. **Evidence First**：优先使用一手资料、企业工程博客、官方案例、研究报告和带指标的实践文章。
3. **Workflow over Tools**：关注组织、流程、验证、上下文和协作方式，而不是工具清单。
4. **Reusable Knowledge**：每篇文章都必须转化为可复用资产，而不是停留在摘要。
5. **Human + Codex Ready**：内容既要适合人阅读，也要适合 Codex/Agent 检索和复用。

## 每日产出标准

每次归档一篇精选文章，标准目录如下：

```text
YYYY-MM-DD-source-company-topic/
├── README.md
├── article.md
├── case-study-<company>.md
├── framework-<id>-<slug>.md
└── assets/
    └── framework-<id>-<slug>.png
```

如果当天文章不包含明确公司案例，可以省略 case-study 文件。如果没有新的框架，更新已有 framework，而不是强行新增。

## 文件职责

### README.md

给人和 Codex 快速理解：这篇为什么进入知识库、核心观点、关键指标、原文链接和归档决策。

### article.md

中文深度解读。不是全文翻译，也不是流水账摘要，而是提炼背景、核心观点、机制、方法论、局限和后续问题。

### case-study-*.md

公司案例库条目。记录某家公司如何实践 AI Native、经历了什么阶段、做了哪些流程和组织变化、产生了哪些指标和经验。

### framework-*.md / assets/*.png

框架库条目。用于沉淀通用模型和视觉卡片。Framework 应该少而精，持续迭代，不要每天重复造新框架。

## 文章筛选标准

优先：

- 过去 14 天内发表或更新
- 有实际落地案例
- 有指标、流程细节或组织变化
- 来自头部企业、工程博客、研究机构或一手访谈
- 能抽象出可复用 pattern

降低优先级：

- 纯观点文章
- 工具发布新闻
- 没有实践细节的营销文
- 无法验证日期或来源的内容

## 评分规则

| 分数 | 含义 | 是否归档 |
|---|---|---|
| ★★★★★ | 必须保留，长期引用 | 是 |
| ★★★★☆ | 高质量案例或方法论 | 是 |
| ★★★☆☆ | 有参考价值但不完整 | 视情况 |
| ★★☆☆☆ | 信息一般 | 否 |
| ★☆☆☆☆ | 噪声 | 否 |

## Pattern 抽象规则

Pattern 不是文章观点的复制，而是跨案例可复用的机制。一个合格 Pattern 至少包含：

- 定义
- 适用场景
- 前置条件
- 操作方式
- 风险与限制
- 支撑案例
- Confidence

## Confidence 规则

| Confidence | 含义 |
|---|---|
| ★★★★★ | 多家公司、多来源反复验证，接近行业共识 |
| ★★★★☆ | 多个案例支持，但仍需观察 |
| ★★★☆☆ | 单一强案例支持 |
| ★★☆☆☆ | 合理推断，但证据不足 |
| ★☆☆☆☆ | 假设或待验证观点 |
