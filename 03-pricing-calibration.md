# 定价与商业模型校准 — 正式产出

## 基本信息

| 字段 | 值 |
|------|-----|
| 项目 | `agentic-coding-tools` |
| 当前阶段 | `03-pricing` |
| Agent | `mozhang` |
| 日期 | 2026-05-28 |
| 目标市场 | US / English |
| 状态 | `NEEDS_REVIEW` |
| 结论 | 本站是内容型 Comparison/Directory 站点，不对用户收费。变现为三阶段：V0 纯流量积累 → V1 Affiliate → V2 Sponsored Listings ($99-299/mo) |

---

## 1. 竞品锚点

### 直接竞品（AI 工具目录站）

| 竞品 | 类型 | 变现模型 | 数据来源 |
|------|------|----------|----------|
| agenthunt.io | AI Agent 目录 | 免费浏览 + premium insights | WebSearch |
| ai123.help | 通用 AI 工具目录 | 免费 + 对比 | WebSearch |
| futurebrainy | AI 工具 + Prompt 目录 | 付费提交 $29-99/mo | SideProjectors |
| thereisanaiforthat | 老牌 AI 工具目录 | 免费 + sponsored | 已知 |

### 竞品变现锚点提取

| 锚点 | 值 | 来源 |
|------|-----|------|
| Sponsored listing 月费 | $50-500/mo | 多源交叉验证 |
| Paid submission 月费 | $29-99/mo | blink.new, futurebrainy |
| Affiliate 佣金率 | 20-50% recurring | Notta, OutlierKit |
| Display Ad RPM (niche tech) | $15-80 | dev.to case study |
| 稳态月收入参考 | $500-5,000/mo | 多源数据 |
| 参考案例 | Directory.app — $8,200/mo, 1 人 2 周末 | 微信技术博客 |

---

## 2. 成本模型

### 基础设施成本

| 项目 | 月成本 | 年成本 | 说明 |
|------|:--:|:--:|------|
| Cloudflare Pages | $0 | $0 | 免费 tier |
| 域名 (.dev) | ~$1 | ~$12 | ~$12/yr |
| Analytics | $0 | $0 | Cloudflare Web Analytics 或 Plausible CE |
| **合计** | **~$1** | **~$12** | |

> 本站无 API 调用成本、无数据库成本、无存储成本、无计算成本。纯静态站。

### 边际成本

| 场景 | 增量成本 |
|------|:--:|
| +1 用户访问 | $0 |
| +1 工具录入 | 10-20min 人工 |
| 1,000 → 10,000 DAU | $0 |
| 异常流量/DDoS | $0（Cloudflare CDN） |

---

## 3. 三阶段变现路线图

```
V0 (0-3mo):   流量积累期 → ZERO monetization
              目标：10 个工具、12 个页面、开始获取 SEO 流量
              收入：$0
              
V1 (3-6mo):   Affiliate 接入
              条件：月访问 >1,000
              动作：为每个工具页添加 affiliate referral link
              预估：$50-200/mo

V2 (6-12mo):  Sponsored Listings 上线
              条件：月访问 >5,000，DA >20
              动作：开设 "Featured" 槽位，$99-299/mo per slot
              预估：$500-2,000/mo

V3 (12mo+):   Multi-channel
              条件：月访问 >20,000
              动作：Newsletter + Display Ads + 更多 sponsored slots
              预估：$2,000-8,000/mo
```

---

## 4. 变现层级矩阵

| 层级 | 对象 | 方式 | 价格锚点 | 开通路径 |
|------|------|------|:--:|------|
| **Free** | 所有用户 | 全部内容免费访问 | $0 | 无需注册 |
| **Affiliate** | 工具方 | 推荐链接佣金 | 20-50% 订阅费 | 注册 affiliate program → 替换链接 |
| **Featured Listing** | 工具方 | 首页+目录页顶部曝光 | $99-299/mo | Email outreach → Stripe invoice |
| **Sponsored Category** | 工具方 | 整类目独占 | $500-1,000/mo [待确认] | Email outreach → 人工开通 |

---

## 5. Featured Listing 额度（硬限制）

| 档位 | 价格 | 槽位数 | 包含 |
|------|:--:|:--:|------|
| Basic Listing | $0 | 无限 | 标准目录、工具详情页 |
| Featured | $99/mo | **最多 5** | 首页 Top 10 优先、目录页置顶、Featured 标签、增强 tool page |
| Premium | $299/mo | **最多 2** | Featured 全部 + 首页 Hero 区、Blog 推荐位、Newsletter 提及(V3) |

**硬规则：**
- Featured ≤5，售罄即止（不写"无限"）
- Premium ≤2
- 不接受竞品买断类目独占（保持 editorial 中立）
- 所有 sponsored listing 有 `Sponsored` 标签（FTC 合规）

---

## 6. 转化口径

### 对终端用户（免费）

> "Compare the top agentic AI coding tools side-by-side. Free, no signup, updated weekly."

CTA 路径：搜索 → 首页/目录 → 筛选/对比 → 点击工具方链接 (affiliate)

### 对工具方（B2B）

冷启动(工具上线) → 自然 listing(免费) → 观察到流量 →
Email: "Your listing received X views this month. Upgrade to Featured for $99/mo." →
Stripe invoice → 开通

---

## 7. 文案禁止词和必须词

| 类型 | 词/短语 |
|------|------|
| **禁止** | "unlimited", "lifetime access", "money-back guarantee", "subscribe now", "best price guaranteed" |
| **必须** | "free", "no signup", "no credit card", "sponsored" (标签) |

---

## 8. 给下游的交接规格

### 给文案（05-copy）
- 定价/变现区文案模板（§6）
- 用户侧 CTA："Try [Tool Name] Free" → affiliate link
- 工具方 CTA："Get Listed" → email

### 给后端（08-backend）
- `listingTier`: `free | featured | premium`
- `FEATURED_MAX_SLOTS = 5`
- `PREMIUM_MAX_SLOTS = 2`
- Affiliate 埋点：`ref=agentictools` query param

### 给 QA（09-qa）
- 全站无支付按钮（"Buy Now" / "Subscribe" / "Purchase"）
- 全站无注册入口（"Sign Up" / "Register" / "Login"）
- Sponsored listing 必须有 "Sponsored" 标签
- Affiliate 链接带 `ref=agentictools` 参数

---

## 9. 质量门槛自检

| 检查项 | 状态 | 说明 |
|--------|:--:|------|
| 价格有竞品锚点和成本依据 | ✅ | Sponsored $99-299/mo 锚定自多源数据 |
| 免费额度能体验价值但不亏穿 | ✅ | 全部内容免费，边际成本 $0 |
| 没有"无限"或承诺过度 | ✅ | Featured ≤5, Premium ≤2 |
| CTA 与真实开通路径一致 | ✅ | 无虚假"立即购买" |
| 不得出现 unlimited | ✅ | |
| 必须有竞品定价表 | ✅ | |
| 必须有单位成本 | ✅ | $1/mo |
| 必须有 Pro 额度上限 | ✅ | Featured ≤5, Premium ≤2 |

---

## 10. 风险

| 级别 | 风险 | 缓解 |
|:--:|------|------|
| P0 | 不收费模型下流量是唯一引擎，SEO 不起量则零收入 | V0 成本 $1/mo 可承受；6 个月无起色则 pivot |
| P1 | AI coding tools 可能无 affiliate programs（企业销售模式） | 备选：扩大品类至周边工具 |
| P1 | Sponsored listings 需流量才有买方 | V0-V1 不依赖此收入 |
| P2 | 工具方可能要求删除负面信息 | Editorial policy：客观、事实为依据、不删负面 |

---

## 给下游的交接 Prompt

```text
请加载 ShipSolo Skill：student-site-compliance-pipeline，基于 PRD 和定价校准执行。

上游输入：
- 项目：Agentic Coding Tools 比较站
- 站点类型：内容型 Comparison/Directory（非 SaaS 工具）
- 技术栈：Astro + Cloudflare Pages，纯静态
- 数据收集：无用户注册、无 Cookie（仅匿名 analytics）
- 变现：V0 零变现，V1 Affiliate，V2 Sponsored Listings
- 用户生成内容：无（V0 全人工 curation）
- AI 使用：本站不使用 AI 生成内容，全人工编辑
- 域名：[待确认]

合规需求：
- 需生成：Privacy Policy, Terms of Use
- 需生成：Affiliate Disclosure（为 V1 准备）
- 需生成：FTC Sponsored Content 标签规范
- 无需：Cookie Consent（不设 Cookie）
- 无需：Refund Policy（无支付）
- 无需：GDPR 数据导出/删除流程（无用户数据）

限制条件：
- 低成本 MVP
- 不接真实支付
- 不收集个人数据
- 不设用户账户

请严格按 Skill 执行，产出合规文档、风险矩阵、禁用表达清单。
最后一行只能是：[DONE] / [BLOCKED] / [NEEDS_REVIEW]
```

---

**[NEEDS_REVIEW]**
