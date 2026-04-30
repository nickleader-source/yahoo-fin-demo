# Yahoo Finance — Fin AI Agent Demo

A working example of going from a PRD to a live Fin deployment in a single Claude Code session. No manual setup, no platform back-and-forth.

## The starting point

`PRD.md` is a real Yahoo Finance CX PRD written in Claude — covering the top 5 inbound support categories (800K monthly contacts). That's the only input.

## What this repo contains

```
PRD.md          ← The PRD written in Claude. This is the only starting point.
CLAUDE.md       ← Claude Code reads this and runs the deployment autonomously.
docs/           ← 5 help articles generated from the PRD, ready to publish.
  account-login-issues.md
  alerts-and-notifications.md
  data-and-quotes.md
  portfolio-tracking.md
  yahoo-finance-plus.md
```

## Run it yourself (2 minutes)

**Step 1 — Authenticate**
```bash
export INTERCOM_TOKEN=your_token_here
```
Get your token: Intercom → Settings → Developers → Access Token

**Step 2 — Preview (no changes made)**
```bash
npx @intercom/cli setup --plan --company-name "Yahoo Finance" --articles-from ./docs
```

**Step 3 — Deploy**
```bash
npx @intercom/cli setup --company-name "Yahoo Finance" --articles-from ./docs
```

Fin is live.

---

## What the CLI does (actual output)

Running `--plan` against this repo produces the following 4-step deployment plan:

```
Steps to complete Intercom setup:

1. intercom messenger snippet --format html

2. intercom help-center create -f name="Yahoo Finance Help"

3. intercom articles create -f title="Account Login Issues" -F body=@docs/account-login-issues.md
   intercom articles create -f title="Alerts And Notifications" -F body=@docs/alerts-and-notifications.md
   intercom articles create -f title="Data And Quotes" -F body=@docs/data-and-quotes.md
   intercom articles create -f title="Portfolio Tracking" -F body=@docs/portfolio-tracking.md
   intercom articles create -f title="Yahoo Finance Plus" -F body=@docs/yahoo-finance-plus.md

4. intercom fin manifest
```

Every command is real and executable. Add your token and drop `--plan` to deploy.

---

## The agentic version (Claude Code)

Clone this repo and open it in [Claude Code](https://claude.ai/code). It reads `CLAUDE.md` automatically and will:

- Verify that the docs match the PRD scope
- Fill any gaps or update articles if the PRD changes
- Run the full deployment
- Output the messenger install snippet

The full flow — PRD to live Fin — in one Claude Code session, with no coding required.

---

## Why this matters

Yahoo Finance's team already uses Claude to write PRDs. This demo shows that the same Claude session that produces the PRD can also deploy it — no recreation, no back-and-forth, no vendor dependency.

> "I already have a PRD using another AI. Why do I have to come and do it on your platform again?" — Yahoo Finance PM

This is the answer.
