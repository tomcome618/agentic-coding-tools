# Agentic Coding Tools — ShipSolo Pipeline

## Project State

- Status: LIVE (11/13 stages complete)
- Site: https://ai-coding-tool.com
- GitHub: https://github.com/tomcome618/agentic-coding-tools

## Pipeline Automation Rule

When the user says "继续" or "推进流水线" or "next":

1. Read this file to find current stage
2. Find the next stage in status list below
3. Read the previous stage's output file for handoff context
4. Load the corresponding Skill from /root/.claude/skills/<skill-name>/SKILL.md
5. Execute the Skill following its Preflight → Stage Flow → Deliverables
6. Save output to <stage-number>-<stage-name>-output.md
7. Update the status in this file

## Stage Status

| # | Stage | Skill | Output | Status |
|---|-------|-------|--------|--------|
| 01 | research | keyword-research-agent | 01-research-output.md | NEEDS_REVIEW |
| 02 | product | product-definition-prd | 02-product-prd.md | NEEDS_REVIEW |
| 03 | pricing | site-pricing-calibration | 03-pricing-calibration.md | NEEDS_REVIEW |
| 04 | compliance | student-site-compliance-pipeline | 04-compliance-output.md | DONE |
| 05 | copy | site-copywriting-student | 05-copywriting-output.md | DONE |
| 06 | design | site-design-student | 06-design-output.md | NEEDS_REVIEW |
| 07 | frontend | frontend-site-automation | 07-frontend-output.md | DONE |
| 08 | backend | backend-auto-site-cloudflare-workers | — | SKIPPED (static site) |
| 09 | qa | student-site-qa-acceptance | 09-qa-output.md | DONE |
| 10 | seo | seo-launch-workflow | 10-seo-output.md | NEEDS_REVIEW |
| 11 | ops | site-ops-growth-launch | 11-ops-output.md | NEEDS_REVIEW |
| 12 | review | site-data-review-iteration | — | WAITING (needs 1 week data) |
| 13 | orchestrator | site-orchestrator-playbook | — | LIVE |

## User Open Items

- [ ] Buy domain ai-coding-tool.com
- [ ] Bind domain in Cloudflare Pages
- [ ] Set up support@ai-coding-tool.com
- [ ] Submit GSC + sitemap
- [ ] Post launch materials from 11-ops

## Gate Status

- QA_GO ✅
- SEO_GO ✅
- Compliance_GO ✅
- PM Gate: NEEDS_REVIEW
- Launch Gate: NEEDS_DECISION (user confirms public posts)
