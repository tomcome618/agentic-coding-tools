# 合规与基础法律页面 — 正式产出

## 基本信息

| 字段 | 值 |
|------|-----|
| 项目 | `agentic-coding-tools` |
| 当前阶段 | `04-compliance` |
| Agent | `modun` |
| 日期 | 2026-05-29 |
| 目标市场 | US / English |
| 状态 | `DONE` |
| 结论 | 极低风险纯静态内容站（无用户系统、无支付、无 Cookie、无 AI API），产出 Privacy + Terms + Affiliate Disclosure + FTC Sponsored 规范 + 禁用词清单 |

---

## 1. 数据清单

| 类别 | 数据类型 | 本站状态 | 说明 |
|------|----------|:--:|------|
| 用户主动提交 | 注册信息（email/密码） | ❌ 无 | 无用户系统 |
| 用户主动提交 | 上传文件/图片 | ❌ 无 | 无上传功能 |
| 用户主动提交 | 评论/评价 | ❌ 无 | V0 无 UGC |
| 用户主动提交 | Newsletter 订阅 | ❌ 无 | V0 无邮件列表 |
| 自动采集 | Cookie（session/auth/tracking） | ❌ 无 | 无 Cookie |
| 自动采集 | 浏览器指纹 | ❌ 无 | 不使用 fingerprinting |
| 自动采集 | 服务器日志（IP, UA, referrer） | ⚠️ Cloudflare CDN 标准日志 | 所有网站基础设施日志 |
| 自动采集 | Analytics 事件 | ⚠️ 匿名页面浏览计数 | Cloudflare Web Analytics — 无 Cookie |
| 第三方 | 跳转外链（affiliate） | ⚠️ V1 阶段 | V0 无 affiliate，预先准备披露 |

---

## 2. 第三方映射

| 服务 | 用途 | 数据类型 | 共享对象 | 退出方式 |
|------|------|----------|----------|------|
| Cloudflare Pages | 托管 + CDN | 服务器日志 (IP, UA, referrer) | Cloudflare, Inc. | N/A（基础设施层） |
| Cloudflare Web Analytics | 匿名访问统计 | 页面浏览数、来源、国家 | Cloudflare, Inc. | 浏览器 Do Not Track / 站点可关闭 |
| Affiliate Links (V1) | 工具推荐佣金 | 点击来源 (`ref=agentictools`) | 目标工具方 | N/A（出站链接） |

---

## 3. 风险分级

| 级别 | 风险项 | 处理 |
|:--:|------|------|
| **P0** | [无] | 无阻断项 |
| **P1** | 联系邮箱用个人邮箱 | 上线前注册域名邮箱 `admin@[domain]` |
| **P1** | Privacy 中未披露 Cloudflare 日志 | 已在 Privacy 中明确列出 |
| **P1** | Affiliate Disclosure 缺失 (V1) | 预先准备完整草稿，V1 激活前上线 |
| **P2** | Sponsored Content 标签缺失 (V2) | 已产出规范文档 |
| **P2** | 工具数据更新频率声明 | Terms 中写 "regularly updated"，需与实际一致 |
| **P2** | 外部链接免责 | Terms 中已声明 |

---

## 4. 法律页面草稿

### 4.1 Privacy Policy (`/privacy/`)

```
# Privacy Policy

**Last updated: [DATE]**

## 1. Information We Collect

**We collect virtually nothing.**

Agentic Coding Tools (the "Site") is a static information website. We do not:

- Require user accounts or registration
- Use cookies or similar tracking technologies
- Collect email addresses, names, or any personal information
- Accept user uploads or submissions
- Run analytics scripts that track individual users

**Infrastructure Logs:** Our hosting provider (Cloudflare) may maintain standard
server logs (IP address, user agent, referrer URL) necessary for the operation
and security of the Site. These logs are not used by us to identify individual
visitors and are subject to Cloudflare's privacy practices.

**Anonymous Analytics:** We may use privacy-first analytics (Cloudflare Web
Analytics) that counts page views without cookies, fingerprinting, or tracking
individual users across sessions or sites.

## 2. How We Use Information

Since we collect no personal information, there is nothing to use, share, or
sell. Anonymous page view counts help us understand which content is useful.

## 3. Third-Party Services

| Service | Purpose | Privacy Policy |
|---------|---------|----------------|
| Cloudflare | Hosting, CDN, DDoS protection | cloudflare.com/privacypolicy |
| Cloudflare Web Analytics | Anonymous usage statistics | cloudflare.com/web-analytics |

## 4. External Links

Our Site contains links to third-party websites. We are not responsible for
their privacy practices.

## 5. Children's Privacy

Our Site is not directed at children under 13. We do not knowingly collect
information from anyone under 13.

## 6. Your Rights

Since we hold no personal data, there is no data to access, correct, or delete.
Questions: [CONTACT_EMAIL]

## 7. Changes

We will post any changes to this policy on this page.

## 8. Contact

For privacy questions: [CONTACT_EMAIL]
```

### 4.2 Terms of Use (`/terms/`)

```
# Terms of Use

**Last updated: [DATE]**

## 1. Acceptance

By accessing Agentic Coding Tools (the "Site"), you agree to these Terms.

## 2. Description of Service

The Site provides information about agentic AI coding tools, including curated
listings, feature comparisons, and editorial content. All content is for
informational purposes only.

## 3. No Accounts, No Payments

The Site does not offer user accounts, paid subscriptions, or any service
requiring payment. All content is freely accessible.

## 4. Intellectual Property

The Site's original content is our intellectual property. Tool names, logos,
and trademarks belong to their respective owners.

## 5. External Links & Affiliate Disclosure

The Site links to third-party websites. We are not responsible for their content.

**Affiliate Disclosure:** Some links may be affiliate links. We may earn a
commission at no additional cost to you. Affiliate relationships do not
influence our editorial assessments. See full [Affiliate Disclosure](/disclosure/).

## 6. Sponsored Content

Listings marked "Sponsored" are paid placements. Sponsored tools are clearly
labeled.

## 7. Accuracy & Updates

We strive to keep information accurate, but do not guarantee real-time accuracy.
Verify details on the tool's official website before making decisions.

## 8. Disclaimer of Warranties

THE SITE IS PROVIDED "AS IS" WITHOUT WARRANTIES OF ANY KIND.

## 9. Limitation of Liability

TO THE MAXIMUM EXTENT PERMITTED BY LAW, WE SHALL NOT BE LIABLE FOR ANY DAMAGES
ARISING FROM YOUR USE OF THE SITE.

## 10. Changes to Terms

We may update these Terms. Continued use after changes constitutes acceptance.

## 11. Contact

[CONTACT_EMAIL]
```

### 4.3 Affiliate Disclosure (`/disclosure/`)

```
# Affiliate Disclosure

**Last updated: [DATE]**

## Our Stance

Some links on Agentic Coding Tools are affiliate links. When you click and sign
up, we may receive a commission — at no additional cost to you.

## Why We Use Affiliate Links

Affiliate commissions help cover operating costs and allow us to keep the Site
free for all visitors — no paywalls, no subscriptions, no accounts.

## Does This Affect Our Recommendations?

**No.** Our editorial assessments are based on objective criteria. Affiliate
relationships do not influence rankings or comparisons.

## Identifying Affiliate Links

Affiliate links may be marked with a `ref=` parameter in the URL, a note near
the link, or context in the page's introductory text.

## Current Affiliate Relationships

| Tool | Affiliate Program | Status |
|------|:--:|:--:|
| [V1 — to be populated] | — | — |

## Questions?

[CONTACT_EMAIL]
```

---

## 5. FTC Sponsored Content 标签规范

### 标签要求

| 位置 | 标签文字 | 外观要求 |
|------|----------|----------|
| 首页 Featured 工具卡片 | `Sponsored` | 卡片左上角，与工具名称同字号，灰色或品牌色标签 |
| 目录页 listing 行 | `Sponsored` | listing 标题右侧，小标签样式 |
| 工具详情页 | `This is a sponsored listing. [Tool Name] paid for this placement.` | 页面顶部信息栏，浅色背景，可关闭 |
| Blog 内提及 sponsored 工具 | `[Tool Name] is a sponsor of this article.` | 段首或段尾 italic |

### 禁止行为

- ❌ 用 `Partner`、`Recommended`、`Featured` 模糊词语替代 `Sponsored`
- ❌ 标签颜色与背景相同导致不可见
- ❌ 付费 placement 写成 editorial ranking
- ❌ Sponsored 工具混入非付费对比表不加标签

### QA 验收标准

- 每个 sponsored listing 有明显可见 `Sponsored` 标签
- 标签与周围文字对比度 ≥4.5:1 (WCAG AA)
- 首页首屏可直接看到至少一个 Sponsored 标签（如首页有 sponsored 工具）

---

## 6. 禁用表达清单

### 全站禁用

| 禁用词/短语 | 原因 | 替代 |
|-------------|------|------|
| `official` | 非任何工具的官方渠道 | `curated` / `independent` |
| `100% accurate` | 无法保证实时准确 | `regularly updated` / `best-effort accuracy` |
| `guaranteed` | 无保证 | `we aim to` / `we strive to` |
| `the best` | 主观不可验证 | `top-rated` / `highly reviewed` |
| `all AI coding tools` | 不可能全覆盖 | `leading agentic AI coding tools` |
| `complete list` | 列表不完整 | `curated selection` |
| `endorsed by [Company]` | 未获授权 | 不写此类表述 |
| `partner` (未签约) | 只有签约才能叫 partner | `listed tool` / `affiliate` |
| `free forever` | 工具方可随时改定价 | `free tier available (subject to change)` |
| `open source` (未验证) | 需验证 license | 写具体: `MIT licensed` / `Apache 2.0` |
| `real-time`, `live` (未实现) | 本站不是实时数据 | `updated weekly` / `as of [date]` |

### 目录站特有禁词

| 禁止 | 原因 |
|------|------|
| 未经授权使用工具 logo 作为 favicon | 商标侵权 |
| 不披露情况下用 affiliate link 替代直链 | FTC 违规 |
| 声称 "we tested all tools" 但实际未全部测试 | 虚假陈述 |
| 引用 Gartner/Forrester 数据不注明出处 | 版权侵权 |

---

## 7. 法律页 Route Contract + Footer

```
/privacy/     → noindex, static HTML (canonical)
/terms/       → noindex, static HTML (canonical)
/disclosure/  → noindex, static HTML (V1 激活)
```

**Footer 结构：**
```
© 2026 Agentic Coding Tools. All rights reserved.
Privacy Policy · Terms of Use · Affiliate Disclosure
```

---

## 8. QA 合规验收点

| # | 检查项 | 方法 |
|---|--------|------|
| 1 | `/privacy/` 页面可访问，不 404 | 浏览器直接访问 |
| 2 | `/terms/` 页面可访问，不 404 | 浏览器直接访问 |
| 3 | Footer 三个法律链接全部可点击、跳转正确 | 目视检查 |
| 4 | 全站无 "Sign Up" / "Login" / "Register" 入口 | 目视扫描全站 |
| 5 | 全站无 "Buy Now" / "Subscribe" / "Purchase" 按钮 | 目视扫描全站 |
| 6 | 全站不含任何禁用词（见清单） | Ctrl+F 全站搜索 |
| 7 | Privacy 中 Cloudflare 已披露 | 阅读 /privacy/ |
| 8 | Terms 中 Affiliate Disclosure 段落存在 | 阅读 /terms/ |
| 9 | Sponsored 标签可见且合规（V2 时启用） | 目视 + 对比度检测工具 |
| 10 | 联系邮箱为域名邮箱（非 Gmail/Yahoo/个人邮箱） | 检查 [CONTACT_EMAIL] |

---

## 9. 质量门槛自检

| 检查项 | 状态 |
|--------|:--:|
| 法律页与实际数据收集一致 | ✅ |
| 第三方服务全部披露 | ✅ |
| 高风险素材/IP 有免责声明或替代方案 | ✅ |
| footer/legal route 不会 404 | ✅ |

---

## 给下游的交接 Prompt

```text
请加载 ShipSolo Skill：site-copywriting-student，基于 PRD + 定价 + 合规产出文案。

上游输入：
- 项目：Agentic Coding Tools 比较站
- 合规阶段已完成，产出见 04-compliance-output.md
- 法律页面草稿已冻结（Privacy / Terms / Affiliate Disclosure）
- 禁用词清单必须全程遵守（全站通用 + 目录站特有）
- FTC Sponsored 标签规范已定义，文案需配合设计落地标签外观
- Footer 法律链接结构已固定

关键约束：
- 禁用词清单不可突破
- 法律页面内容不可大改（只能替换 [CONTACT_EMAIL] [DATE] 占位符）
- Affiliate Disclosure 预先准备但 V0 暂不上线（V0 无 affiliate link）
- 所有声称必须与本站实际能力一致（不夸大）

限制条件：
- 低成本 MVP
- 无用户注册
- 无支付
- 无 AI 生成内容声明
```

---

**[DONE]**
