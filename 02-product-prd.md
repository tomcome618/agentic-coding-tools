# 产品定义与 PRD — 正式产出

## 1. 基本信息

| 字段 | 值 |
|------|-----|
| 项目 | `agentic-coding-tools` |
| 候选域名 | `ai-coding-tool.com` / `aicoding.tools` [待确认] |
| 当前阶段 | `02-product` |
| Agent | `moce` |
| 日期 | 2026-05-28 |
| 目标市场 | US / English |
| 状态 | `NEEDS_REVIEW` |
| 结论 | 定义 15 页 MVP 的 Agentic AI Coding Tools 比较/发现平台，站点类型混合型（Comparison Tool + Directory + Content），V0 可 1 人 2-4 周交付 |

---

## 2. 上游输入

- 来源：01-research 交接摘要
- 主关键词：`agentic ai coding tool` (KD 7, 12,100 vol/mo, $16.54 CPC, LOW)
- SERP 缝隙：Top 10 以研报/博客为主，无专用工具比较站
- 竞品：agenthunt.io, ai123.help

---

## 3. ICP 定义

### 主 ICP：Developer evaluating AI coding tools

| 维度 | 描述 |
|------|------|
| Who | 全栈/后端/前端开发者，个人或小团队 |
| Pain | 20+ AI coding tools，不知道选哪个，浪费 2-3 天试错 |
| Goal | 5 分钟内找到适合自己的工具 |
| Trigger | 新项目启动 / 团队引入 AI / 当前工具不满意 |
| Reachable via | "agentic ai coding tool", "best AI coding assistant", "Claude Code vs Cursor" |

### 次 ICP 2：Engineering Manager / Tech Lead

| 维度 | 描述 |
|------|------|
| Who | 管理 3-20 人团队，需为团队选型 |
| Pain | 需要客观对比数据做选型报告 |
| Goal | 拿到 2-3 个候选方案的标准化对比 |

### 次 ICP 3：Indie Hacker / Solo Builder

| 维度 | 描述 |
|------|------|
| Who | 独立开发者，预算有限 |
| Pain | 不想在工具上花钱 |
| Goal | 找到最好的免费 AI coding 工具 |

---

## 4. 定位与边界

### 一句话定位

> The most comprehensive, developer-focused comparison platform for agentic AI coding tools. Pick the right tool in 5 minutes — no signup, no fluff, updated weekly.

### 差异化

1. Side-by-side comparison with standardized criteria
2. "Free Tier Checker" — 一眼看到免费额度
3. Weekly updates（不像过时的博客文章）
4. No signup required
5. Lightweight（<200KB, <200ms）

### NOT-DO（V0 硬边界）

| 不做 | 原因 |
|------|------|
| ❌ AI 代码生成（不运行模型） | 非工具站，是比较平台 |
| ❌ 用户注册/登录 | 限制条件 |
| ❌ 支付/付费订阅 | 限制条件 |
| ❌ API 服务 | MVP 不建 |
| ❌ 收集个人数据 | 限制条件 |
| ❌ 非 coding 类 AI 工具 | 聚焦避免品类扩散 |
| ❌ AI 生成比较内容 | 数据人工验证 |
| ❌ Newsletter 弹窗 | 零摩擦 |

---

## 5. 站点类型

**混合型 — Comparison Tool + Directory + Content**

| 维度 | 决策 |
|------|------|
| 主形态 | Interactive Comparison Tool |
| 次级形态 | Directory（可筛选/排序） |
| SEO 支撑 | Content / Blog |
| 不是 | SaaS landing page、纯 blog、纯 listicle |

---

## 6. 页面矩阵

### Core Pages (V0)

| # | URL | Index | 主词 | H1 | Schema |
|---|-----|:--:|------|----|--------|
| 1 | `/` | ✅ | agentic ai coding tool | Best Agentic AI Coding Tools Compared (2026) | WebSite + ItemList |
| 2 | `/tools/` | ✅ | agentic ai coding tools list | All Agentic AI Coding Tools — Complete Directory | ItemList |
| 3 | `/compare/` | ✅ | compare ai coding tools | Compare AI Coding Tools Side-by-Side | WebApplication |
| 4 | `/tools/claude-code/` | ✅ | claude code review | Claude Code: Features, Pricing, Free Tier & Alternatives | SoftwareApplication |
| 5 | `/tools/cursor/` | ✅ | cursor ai editor | Cursor: Features, Pricing, Free Tier & Alternatives | SoftwareApplication |
| 6 | `/tools/gemini-cli/` | ✅ | gemini cli coding | Gemini CLI: Features, Pricing, Free Tier & Alternatives | SoftwareApplication |
| 7 | `/tools/codex-cli/` | ✅ | openai codex cli | Codex CLI: Features, Pricing, Free Tier & Alternatives | SoftwareApplication |
| 8 | `/tools/github-copilot/` | ✅ | github copilot agent | GitHub Copilot: Features, Pricing, Free Tier & Alternatives | SoftwareApplication |
| 9 | `/free-tools/` | ✅ | free ai coding tools | Best Free AI Coding Tools (No Credit Card) | ItemList |
| 10 | `/blog/` | ✅ | ai coding blog | Blog — Agentic AI Coding Tools | Blog |
| 11 | `/blog/best-agentic-ai-coding-tools-2026/` | ✅ | best agentic ai coding tools 2026 | 10 Best Agentic AI Coding Tools in 2026 | Article |
| 12 | `/blog/claude-code-vs-cursor-vs-copilot/` | ✅ | claude code vs cursor vs copilot | Claude Code vs Cursor vs Copilot — Honest Comparison | Article |

### Utility Pages

| # | URL | Index | H1 |
|---|-----|:--:|----|
| 13 | `/about/` | ✅ | About Agentic Coding Tools |
| 14 | `/privacy/` | ❌ | Privacy Policy |
| 15 | `/terms/` | ❌ | Terms of Use |

---

## 7. Route Contract

```
/                           → indexable, static (SSG), revalidate weekly
/tools/                     → indexable, static (SSG), revalidate weekly
/tools/[slug]/              → indexable, static (SSG), revalidate weekly
/compare/                   → indexable, client-side interactive (CSR)
/blog/                      → indexable, static (SSG)
/blog/[slug]/               → indexable, static (SSG)
/free-tools/                → indexable, static or SSR, revalidate weekly
/about/                     → indexable, static
/privacy/                   → noindex, static
/terms/                     → noindex, static
/sitemap.xml                → auto-generated
/robots.txt                 → allow all, sitemap pointer
```

---

## 8. 技术栈

| 层 | 选择 | 原因 |
|----|------|------|
| Framework | Astro (SSG) 或 plain HTML | 轻量、<200KB、SEO 友好 |
| Styling | Tailwind CSS 或 vanilla CSS | 小体积 |
| JS | Alpine.js 或 vanilla JS | 比较工具交互无需 React |
| Hosting | Cloudflare Pages | 免费、快、自动部署 |
| Data | JSON/MDX files (no DB) | 工具数 <100，无需 DB |
| Analytics | Plausible 或 Cloudflare Web Analytics | 隐私友好 |
| Domain | `ai-coding-tool.com` [待确认] | .dev TLD 适合开发工具 |

---

## 9. 产品验收标准

| # | 任务 | 验收标准 | 优先级 |
|---|------|----------|:--:|
| T1 | Google 搜索进入首页 → 3 秒内看到 Top 5 | LCP <2s | P0 |
| T2 | `/tools/` 筛选 "Free tier = yes" → 即时过滤 | <100ms | P0 |
| T3 | 选 3 个工具 → `/compare/` 并排对比 | 数据正确、有来源 | P0 |
| T4 | 工具页点击 "Alternatives" → 替代工具列表 | ≥3 个替代项 | P1 |
| T5 | `/free-tools/` 列出免费工具 | 列表准确 | P1 |
| T6 | Blog 对比表 → 点击进入工具页 | 内链正确、数据一致 | P1 |

---

## 10. 质量门槛自检

| 检查项 | 状态 |
|--------|:--:|
| PRD 不只是关键词说明，而是可开发产品 | ✅ |
| 每个 indexable 页面有真实价值和用户任务 | ✅ |
| NOT-DO 明确（8 项硬边界） | ✅ |
| 设计/文案/前后端都知道交付边界 | ✅ |

---

## 给下游的交接 Prompt

```text
请加载 ShipSolo Skill：site-pricing-calibration，基于 PRD 执行。

上游输入：
- 项目：Agentic Coding Tools 比较站
- 站点类型：混合型 — Comparison Tool + Directory + Content
- 页面：15 页 MVP（12 indexable + 3 utility）
- 技术栈：Astro/plain HTML + Cloudflare Pages，无 DB
- 主 ICP：Developer evaluating AI coding tools
- NOT-DO：无用户注册、无支付、无 API、无 AI 生成内容、无数据收集

限制条件：
- 低成本 MVP（月成本目标 <$10）
- 不接真实支付
- 无用户账户系统
- SEO 小站优先

请严格按 Skill 执行，产出定价报告、成本假设表、套餐矩阵、转化口径、后端 entitlement 建议。
最后一行只能是：[DONE] / [BLOCKED] / [NEEDS_REVIEW]
```

---

**[NEEDS_REVIEW]**
