# OpenClaw x Lobster Agent - Team Structure

## Total Principle
- Official repo = upstream only
- Our fork = main battlefield
- Build lobster skeleton first, then connect external systems
- Everyone only modifies their own area, no crossing boundaries

---

## A Team: Frontend / Console / WebChat
**Directories:** `ui/`, `apps/`

**Tasks:**
- Lobster brand UI
- WebChat custom entry
- Admin dashboard
- Customer sandbox status page
- Payment completion redirect
- Skill marketplace UI

**Branches:** `feat/ui/*`, `feat/apps/*`, `fix/ui/*`

**Do NOT touch:** skill logic, gateway routing, webhook integrations

---

## B Team: Gateway / Session / Routing / Sandbox
**Directories:** `packages/`, `src/`, gateway modules

**Tasks:**
- Multi-tenant routing
- Per-customer session/memory/sandbox
- Skill allowlist/denylist
- Security scanning hooks
- Model routing: local Qwen / cloud fallback
- MCP server registration & isolation
- Webhook event bridge

**Branches:** `feat/gateway/*`, `feat/core/*`, `feat/session/*`, `feat/routing/*`

**Do NOT touch:** frontend styles, business docs, HighLevel CRM

---

## C Team: Skills / Docs / Lobster Flows
**Directories:** `skills/`, `docs/`

**Tasks:**
- ecpay-payment
- line-notify
- telegram-admin
- sensor-bridge
- mission-report
- customer-onboarding
- Whitelist review skills
- Install manual / SOP / internal docs

**Branches:** `feat/skills/*`, `docs/skills/*`, `docs/sop/*`

**Do NOT touch:** gateway core, UI framework, production infra

---

## D Team: External Integrations / Automation / Webhook
**Directories:** `extensions/`, `automation/`, `scripts/`, webhook adapter

**Tasks:**
- HighLevel integration
- n8n workflow
- LINE / Telegram / Email
- ECPay webhook callback
- Supabase trigger
- Cloudflare / Railway deploy scripts
- PM2 / Docker startup

**Branches:** `feat/integrations/*`, `feat/automation/*`, `chore/deploy/*`

**Do NOT touch:** UI details, skill prompt wording, gateway internals

---

## E Team: Tech Lead / Merge Authority
**Role:** Architecture lock, PR merge, spec decisions, blocker removal, daily standup

**Rule:** Does NOT directly modify files. Only reviews and merges.

---

## Branch Naming Convention
```
main          -> always deployable
develop       -> team integration branch
upstream-sync -> sync official repo, no dev

feat/<domain>/<short-name>
fix/<domain>/<short-name>
chore/<domain>/<short-name>
docs/<domain>/<short-name>
refactor/<domain>/<short-name>
hotfix/<domain>/<short-name>
```

## Commit Convention
```
feat: add tenant-aware gateway routing
fix: resolve sandbox memory leak
docs: add ecpay skill setup guide
chore: add docker compose for local dev
refactor: split webhook adapter into modules
```

## PR Rules
- Each PR = ONE purpose only
- No mixing UI + gateway + skill in same PR
- No direct push to main
- No shared feature branches

## Prohibited Branch Names
`test`, `new`, `max`, `final`, `aaa`, `temp`
