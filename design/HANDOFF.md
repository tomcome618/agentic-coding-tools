# 设计 Handoff → 07-frontend

## 文件结构

```
design/
├── design-system.css      # 全局设计系统 (416行 CSS变量 + 组件样式)
├── stitch-prompts.md      # Stitch 页面生成 Prompt (复制到 stitch.withgoogle.com)
├── HANDOFF.md             # 本文件
└── pages/
    ├── index.html         # 首页 (完整可运行)
    └── tool-detail.html   # 工具详情页模板 (Claude Code 示例)
```

## 前端实现清单

### 设计系统变量 (从 design-system.css 提取)

| 类别 | 变量 | 值 |
|------|------|-----|
| 背景 | `--color-bg` | `#fafbfc` |
| 表面 | `--color-surface` | `#ffffff` |
| 文字 | `--color-text` | `#1a1a2e` |
| 次要文字 | `--color-text-secondary` | `#64748b` |
| 强调色 | `--color-accent` | `#2563eb` |
| 边框 | `--color-border` | `#e2e8f0` |
| 成功绿 | `--color-success` | `#16a34a` |
| 警告色 | `--color-warning` | `#d97706` |
| 字体 | `--font-body` | system font stack |
| 等宽字体 | `--font-mono` | monospace stack |

### 需要实现的页面 (按 PRD Route Contract)

| # | URL | 模板 | 状态 |
|---|-----|------|:--:|
| 1 | `/` | index.html | ✅ 已实现 |
| 2 | `/tools/` | 新建 (table layout) | ⬜ 待实现 |
| 3 | `/compare/` | 新建 (JS驱动) | ⬜ 待实现 |
| 4-8 | `/tools/[slug]/` | tool-detail.html 模板 | ✅ 模板已实现 |
| 9 | `/free-tools/` | 同 /tools/ + 过滤 | ⬜ 待实现 |
| 10 | `/blog/` | 新建 | ⬜ 待实现 |
| 11-12 | `/blog/[slug]/` | 新建 | ⬜ 待实现 |
| 13 | `/about/` | 简单 prose | ⬜ 待实现 |
| 14-15 | `/privacy/` `/terms/` | 法律页面 (合规已冻结) | ⬜ 待实现 |

### 交互状态

| 组件 | 状态 | 实现方式 |
|------|------|----------|
| Accordion | open/closed | CSS class toggle |
| Filter chips | active/inactive | CSS class toggle |
| Mobile nav | open/closed | CSS class toggle |
| Compare table | empty/1 tool/2+ tools | JS 条件渲染 |
| Tool directory | with/without filters | JS 过滤表格行 |

### 数据契约 (tools.json)

```json
{
  "tools": [
    {
      "id": "claude-code",
      "name": "Claude Code",
      "maker": "Anthropic",
      "type": "Terminal-native CLI",
      "freeTier": true,
      "freeTierLabel": "Yes (limited credits)",
      "startingPrice": "$20/mo",
      "sweBench": "~82%",
      "selfHosted": false,
      "ideIntegrations": ["Terminal", "VS Code"],
      "languages": ["Python", "JavaScript", "TypeScript", "Go", "Rust"],
      "agentMode": true,
      "description": "Anthropic's agentic coding tool. Terminal-native.",
      "pricingTiers": [
        {"plan": "Free", "price": "$0", "details": "Limited API credits"},
        {"plan": "Pro", "price": "$20/mo", "details": "Higher limits"},
        {"plan": "Max", "price": "$100/mo", "details": "Maximum limits"},
        {"plan": "API", "price": "Pay-per-token", "details": "Usage-based"}
      ],
      "features": [
        "Autonomous multi-file editing",
        "Git-aware",
        "Terminal-native",
        "Custom instructions (CLAUDE.md)",
        "VS Code extension",
        "Enterprise features"
      ],
      "alternatives": [
        {"want": "IDE-native experience", "toolId": "cursor"},
        {"want": "Lowest cost per token", "toolId": "gemini-cli"}
      ],
      "sponsored": false
    }
  ]
}
```

### 部署

```bash
# 所有页面为静态 HTML + 一个 tools.json 数据文件
# 部署到 Cloudflare Pages:
npx wrangler pages deploy design/pages/ --project-name agentic-coding-tools
```
