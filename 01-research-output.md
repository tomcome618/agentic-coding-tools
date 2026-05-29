# 关键词研究 Agent（discoverkeywords.co API）— 正式产出

## 基本信息

| 字段 | 值 |
|------|-----|
| 阶段 | `01-research` |
| Agent | `motan` |
| 日期 | 2026-05-28 |
| 目标市场 | US / English |
| 方向 | AI tools + lightweight web tools + calculator/generator/converter/checker/planner |
| 限制 | 低成本 MVP、SEO 小站优先、无重登录、无真实支付、无敏感数据 |
| 状态 | `NEEDS_REVIEW` |
| 结论 | API 今日新词缓存无匹配方向的 clean word；old-word pool + Web SERP 研究确定 "agentic ai coding tool" + niche web tools 策略为最可行路径 |

---

## 阶段流程产出

### 1. 候选池
- **新词侧**：API 扩展 200 词 → compare 50 词 → 4 个"值得继续"（全部不匹配方向）
- **老词侧**：API 个性化老词接口 3 个：`free ai writer`、`checker for ai`、`agentic ai coding tool`
- **Web 补充**：niche calculators（BMI、concrete、salary-to-hourly）、AI detection checker、AI tool directory/lister

### 2. 硬闸门判定

| 候选词 | Google Trends | 基准对比 | 12月 Freshness | 工具化意图 | SERP 可进入 | ROI | 判定 |
|--------|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| ai editor rsp | ✅ | 2.31x strong | ✅ 新词(90d) | ⚠️ | ❌ 品牌词 | ❌ | SKIP |
| ai editor rsp editing | ✅ | 2.16x strong | ✅ 新词(90d) | ⚠️ | ❌ 品牌词 | ❌ | SKIP |
| teamfight manager | ⚠️ 0.44x | watch | ✅ 新词(90d) | ❌ 游戏 | ❌ | ❌ | SKIP |
| teamfight manager 2 | ⚠️ 0.37x | watch | ✅ 新词(90d) | ❌ 游戏 | ❌ | ❌ | SKIP |
| **agentic ai coding tool** | ✅ | $16.54 CPC | ✅ <18月 | ✅ "tool" | ✅ KD 7, LOW | ✅ | **PASS** |
| checker for ai | ⚠️ | 40,500 vol | ⚠️ old | ⚠️ 意图模糊 | ⚠️ KD 32 | ⚠️ | WATCH |
| free ai writer | ⚠️ | 3,600 vol | ❌ stable | ✅ | ❌ 大牌饱和 | ❌ | SKIP |

### 3. 机会分级

| 等级 | 关键词/方向 | 依据 |
|------|-----------|------|
| A_NOW | [无] | API 今日缓存无匹配方向的 clean new word |
| **B_QUEUE** | `agentic ai coding tool` (KD 7) | 低竞争、高 CPC、SERP 空隙、新兴赛道 |
| **B_QUEUE** | niche calculators 策略 (200+ pages) | 验证过的 SEO 飞轮、低成本、匹配 MVP 约束 |
| C_WATCH | `checker for ai` (KD 32, vol 40,500) | 高流量但 KD 偏高，意图需验证 |
| D_SKIP | ai editor rsp / teamfight manager / free ai writer | 品牌词/游戏词/饱和市场 |

### 4. SERP 实扫结论

**agentic ai coding tool SERP：**
- Top 10 以研报/博客为主（Gartner、dev.to、虎嗅、kilo.ai），无专用工具站/比较站
- 绿色信号：KD 7 极低、无 AI Overview 占位[待确认]、有 niche 站点缝隙
- 结论：存在内容/工具型页面缺口

---

## 质量门槛自检

| 检查项 | 状态 | 说明 |
|--------|:--:|------|
| 主推荐有趋势、基准对比、freshness、SERP 证据 | ⚠️ | 趋势/基准/KD 来自 API；SERP 来自 WebSearch 非 incognito |
| 没有把稳定老词伪装成新词 | ✅ | agentic ai coding tool 明确标注 old-word pool 来源 |
| 没有用品牌词或定义词硬做工具站 | ✅ | RSP 品牌词、game 词已全部 SKIP |
| 结论可被 PRD 直接接住 | ✅ | B_QUEUE 方向有明确工具类型、用户意图、技术栈建议 |

---

## Top 3 推荐

| 排名 | 推荐 | 证据 |
|------|------|------|
| #1 | Agentic AI Coding Tool 比较/清单站 | KD 7, vol 12,100, CPC $16.54, SERP 空隙 |
| #2 | Niche Calculators 网络 | dev.to 200+ 案例验证、零竞争长尾、RPM $15-80 |
| #3 | AI Checker/Detector 工具 | vol 40,500, LOW 竞争, 现有产品单一 |

---

## 给下游的交接 Prompt

```text
请加载 ShipSolo Skill：product-definition-prd，基于关键词研究结果执行。

上游输入：
- 主方向："agentic ai coding tool" 比较/清单站
- 备选方向：niche web tools 网络（calculator/generator/checker）
- 目标市场：US / English
- 主关键词：agentic ai coding tool (KD 7, 12,100 vol/mo, $16.54 CPC, LOW competition)
- 观察关键词：checker for ai (KD 32, 40,500 vol/mo)
- SERP 现状：Top 10 以研报/博客为主，无专用比较工具站，存在页面形态缺口
- 竞品：agenthunt.io, ai123.help (轻量目录站，非专用比较工具)

限制条件：
- 低成本 MVP
- SEO 小站优先
- 无重登录
- 无真实支付
- 无敏感个人数据
- 可以接受 old-word fallback，但不把老词伪装成新词

请严格按 Skill 执行：
1. 先执行 Preflight 和输入契约检查
2. 按阶段流程逐步产出
3. 每个重要判断写依据
4. 输出交付物 + 验收清单自检 + 下游交接摘要
5. 涉及公开发布、生产部署、支付、真实用户数据时，先列确认项
6. 最后一行只能是：[DONE] / [BLOCKED] / [NEEDS_REVIEW]
```

---

**[NEEDS_REVIEW]**
