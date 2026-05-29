# Stitch 页面生成 Prompt — 复制粘贴即用

## 使用方法

1. 打开 https://stitch.withgoogle.com → Google 登录
2. 点 "+ New Project" → 选 Desktop
3. 粘贴下面的 Prompt（一次一个页面）
4. 生成后点 "Get Code" 导出 HTML

---

## 首页 `/`

```
Design a light-theme landing page for Agentic Coding Tools —
"The most comprehensive, developer-focused comparison platform for
agentic AI coding tools. Pick the right tool in 5 minutes — no signup,
no fluff, updated weekly."

Target users: Software developers evaluating AI coding tools.

Typography: System font stack (-apple-system, BlinkMacSystemFont, "Segoe UI")
for body text. DO NOT use Inter, Roboto, or Google Fonts.
Use a monospace font for tool names and code.

Color scheme: Off-white background (#fafbfc), blue accent (#2563eb),
dark text (#1a1a2e), secondary text (#64748b).
NO purple, NO gradients, NO pastel colors.

Page structure (top to bottom):

1. NAVIGATION: Logo text "Agentic Coding Tools" left (bold, "Agentic" in blue accent),
   nav links "Tools | Compare | Free Tools | Blog" center-right.
   Sticky, white background, bottom border 1px solid #e2e8f0.

2. HERO SECTION (LEFT-ALIGNED, NOT CENTERED):
   H1 "Find the Right Agentic AI Coding Tool for How You Work" in 2.5rem bold.
   Subheadline "Stop reading 10 different blog posts and signing up for 5 trials.
   We compare the top agentic AI coding tools side-by-side — free tiers, pricing,
   features, and real trade-offs. No signup. No bias. Updated weekly." in 1.125rem #64748b.
   Two buttons side by side: "Find My Tool →" (blue bg, white text) and
   "Browse All Tools →" (white bg, blue border).

3. TOP TOOLS THIS WEEK section:
   Section title "Top Tools This Week".
   Horizontal COMPACT list (NOT equal-height cards, NOT 3-column grid):
   "→ Claude Code — 54% market share, best for code quality"
   "→ Cursor — $2B ARR, best for IDE-native workflow"
   "→ Gemini CLI — 1/10 the cost of Opus, best for budget"
   "→ Codex CLI — OpenAI's contender, free for 2 months"
   "→ GitHub Copilot — The incumbent, now with agent mode"
   Link "See All 10+ Tools →" at bottom.

4. WHY TRUST section:
   Section title "Why Developers Trust Our Comparisons".
   Horizontal row of 5 COMPACT items (NOT large icon cards):
   "Updated weekly" / "Objective criteria" / "Free tier facts" /
   "Independent" / "No signup"

5. HOW IT WORKS section:
   Section title "How It Works".
   Numbered list 1-4:
   "1. Browse — Scroll the directory or jump to a tool"
   "2. Filter — Narrow by free tier, pricing, language"
   "3. Compare — Pick 2-4 tools and see them side-by-side"
   "4. Try — Click through, many have free tiers"

6. FAQ section:
   Section title "Frequently Asked Questions".
   Accordion with expandable items:
   "What is an agentic AI coding tool?"
   "Which AI coding tool is best?"
   "Are there free AI coding tools?"
   "Do I need to sign up to use this site?"
   "How often do you update tool information?"

7. FOOTER:
   Links "Privacy Policy · Terms of Use · Affiliate Disclosure"
   Copyright "© 2026 Agentic Coding Tools. All rights reserved."

Design constraints:
- Developer-tool aesthetic, NOT SaaS marketing template
- High information density, developers can scan quickly
- Asymmetric layout where appropriate
- NO emoji as icons — use simple text labels or minimal SVG
- NO purple gradients anywhere
- NO generic rounded-corner shadow cards
- NO hero illustrations or stock photos
- Clean, functional, documentation-like but friendlier
```

---

## 工具详情页 `/tools/claude-code/`

```
Design a light-theme tool detail page for an AI coding tool comparison site.

Typography: System font stack for body, monospace for tool names and code.
Color scheme: Background #fafbfc, surface white, accent #2563eb, text #1a1a2e.

Page structure:

1. NAVIGATION: Same as homepage header

2. PAGE HEADER:
   H1 "Claude Code: What It Is, What It Costs, and Who It's For"
   One-liner "Anthropic's agentic coding tool. Terminal-native.
   54% market share among AI coding tools."

3. AT A GLANCE — Definition list in 2-column grid:
   Maker: Anthropic | Type: Terminal-native CLI
   Free tier: Yes | Starting price: $20/mo
   SWE-bench: ~82% | Self-hosted: No
   IDE integration: Terminal, VS Code | Languages: All major
   Agent mode: Yes — full autonomous multi-step editing

4. FREE TIER section:
   H2 "Free Tier"
   Paragraph about Claude Code free tier access and limits.

5. PRICING table:
   H2 "Pricing"
   Clean table: Plan | Price | What You Get
   Claude Free ($0) | Claude Pro ($20/mo) | Claude Max ($100/mo) | API (pay-per-token)

6. FEATURES section:
   H2 "Features & Integrations"
   Bullet list with checkmarks.

7. ALTERNATIVES table:
   H2 "Claude Code Alternatives"
   Compact table: If you want... | Try this instead

8. FAQ accordion: 3 questions.

9. CTA button: "Compare Claude Code with other tools →"

Design constraints: Editorial layout, tabular data, NO stock photos.
```

---

## 目录页 `/tools/`

```
Design a light-theme tool directory page.

H1: "Every Agentic AI Coding Tool We Track"

FILTER BAR: Horizontal chip group [Free tier ✓] [Self-hosted] [VS Code] [JetBrains] [Terminal]
Active state: blue bg white text.

TOOL LIST: Dense TABLE format, NOT cards.
Columns: Tool | Free Tier | Starting Price | SWE-bench |
Free tier badges: green "Yes" | amber "Limited" | gray "No".
```

---

## 移动端适配

生成完桌面版后，新建 Screen → Mobile：

```
Create a mobile version of the desktop landing page above.
Same content, same design system, same colors and fonts.
- Single column layout
- Hero headline max 2 lines, font-size 1.75rem
- Navigation becomes hamburger menu
- Tables horizontally scrollable
- Touch targets minimum 44px
```

---

## 导出 HTML

每个 screen 生成满意后 → 点右上角 "Get Code" → 复制 HTML
→ 保存到 `/root/projects/agentic-coding-tools/design/pages/`
