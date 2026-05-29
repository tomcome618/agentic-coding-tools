# 视觉设计与页面生成 Prompt — 正式产出

## 基本信息

| 字段 | 值 |
|------|-----|
| 项目 | `agentic-coding-tools` |
| 当前阶段 | `06-design` |
| Agent | `moying` |
| 日期 | 2026-05-29 |
| 目标市场 | US / English |
| 状态 | `NEEDS_REVIEW` |
| 结论 | 产出完整设计系统 + HTML/CSS 真源 + Stitch 生成 Prompt。因 Stitch 需浏览器 Google 登录无法命令行调用，设计 Prompt 需手动粘贴到 stitch.withgoogle.com |

---

## 设计方向

**视觉概念:** "Developer Toolbelt" — 干净、快速、实用。不是 SaaS landing page。

**反 AI 味检查:** 系统字体(非 Inter)、蓝色 accent(非紫色)、左对齐 Hero(非居中)、表格布局(非三卡片)、无占位图(非 stock photo)

**设计系统 Token:** 见 `design/design-system.css` — 完整 CSS 变量 + 组件样式 (416 行)

---

## 产出文件

| 文件 | 内容 |
|------|------|
| `design/design-system.css` | 全局 CSS: 变量、reset、layout、header、footer、buttons、badges、table、chips、accordion、hero、tool list、trust pills、tool meta grid、sponsored banner、breadcrumb、empty state、responsive |
| `design/stitch-prompts.md` | 7 个 Stitch 页面生成 Prompt (首页/工具详情/目录/对比/免费工具/About/移动端) |
| `design/pages/index.html` | 首页完整 HTML (123 行，可直接浏览器打开) |
| `design/pages/tool-detail.html` | 工具详情页模板 (150 行，Claude Code 示例) |
| `design/pages/icon.svg` | Favicon SVG (`>_`) |
| `design/HANDOFF.md` | 前端 handoff: 设计变量表、页面清单、交互状态、数据契约、部署命令 |

---

## 质量门槛自检

| 检查项 | 状态 |
|--------|:--:|
| 设计是真源，不是单张概念图 | ✅ 提供 416 行 CSS + 2 个完整 HTML 页面 |
| 前端可提取字体/颜色/间距/图标 | ✅ `:root` CSS 变量完整 |
| 关键交互状态齐全 | ✅ 空态/accordion open-close/filter active/mobile nav |
| 视觉不撞脸 | ✅ 反 AI 味检查全部通过 |

---

## 给下游的交接 Prompt

```
请加载 ShipSolo Skill：frontend-site-automation，基于设计真源实现前端。

上游输入：
- 设计系统 CSS: design/design-system.css
- 首页 HTML: design/pages/index.html
- 工具详情模板: design/pages/tool-detail.html
- Handoff 文档: design/HANDOFF.md
- Stitch 生成 Prompt: design/stitch-prompts.md (可选)

关键约束：
- 技术栈: vanilla HTML/CSS/JS 或 Astro SSG，不引入 React/Vue
- 数据: 所有工具数据集中在 tools.json (见 HANDOFF.md 数据契约)
- 部署: Cloudflare Pages (npx wrangler pages deploy)
- 页面: 按 HANDOFF.md 清单实现全部 15 页
- 不可改动设计系统 CSS 变量名
- 不可把表格改成卡片布局
```

---

**[NEEDS_REVIEW]**

> 原因: Stitch 需浏览器 Google 登录态，无法从命令行自动生成。已提供完整 Stitch Prompt，打开 stitch.withgoogle.com 粘贴即可生成。HTML/CSS 真源已可独立作为设计交付。
