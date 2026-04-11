# Contributing to Lobster Agent (OpenClaw Fork)

## Quick Start
1. Clone: `git clone https://github.com/icanforyouthebest-bot/openclaw.git`
2. Ensure you're on main: `git checkout main`
3. Create your feature branch from main: `git checkout -b feat/<domain>/<name>`
4. Work only in your assigned directories
5. Commit with convention: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`
6. Push and open PR to `main`
7. Wait for Tech Lead review and merge

## Rules
- NEVER push directly to `main`
- NEVER mix multiple domains in one PR
- NEVER use branch names: test, new, max, final, aaa, temp
- NEVER share a feature branch with another person
- Each PR = ONE purpose

## Sync with Upstream
```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

## Team Directory Ownership
| Team | Directories | Branch Prefix |
|------|------------|---------------|
| A | ui/, apps/ | feat/ui/*, feat/apps/* |
| B | packages/, src/, gateway | feat/gateway/*, feat/core/* |
| C | skills/, docs/ | feat/skills/*, docs/* |
| D | extensions/, automation/, scripts/ | feat/integrations/*, chore/deploy/* |
| E | TEAM.md, architecture | PR merge only |

See [TEAM.md](./TEAM.md) for full details.
