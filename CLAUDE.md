# Fin Deployment — Yahoo Finance

You are deploying Fin AI Agent for Yahoo Finance using the Intercom CLI.

## Your job

1. Read `PRD.md` to understand the use case, scope, and guardrails
2. For each topic in the PRD's "In scope" section, check whether a corresponding markdown file exists in `docs/`. If a file is missing or incomplete, create or update it using the PRD as the source of truth
3. Run `intercom setup` to deploy everything in one shot
4. Output the messenger install snippet at the end so the team can drop it into the site

## Commands

```bash
# Deploy from the current directory (run from repo root)
npx @intercom/cli setup \
  --company-name "Yahoo Finance" \
  --articles-from ./docs

# Get the messenger snippet after setup
npx @intercom/cli messenger snippet --format html

# Verify what was created
npx @intercom/cli articles list
npx @intercom/cli fin manifest
```

## Guardrails to enforce (from PRD)

- Fin must never provide personalized investment advice — if any article or guidance implies it does, rewrite it
- Messenger should be shown to authenticated users only
- Billing dispute articles must always offer a human escalation path

## Authentication

Set your Intercom API token before running:

```bash
export INTERCOM_TOKEN=your_token_here
# or: npx @intercom/cli auth login --token your_token_here
```

Get your token from: Intercom Settings > Developers > Access Token

## Done when

- [ ] All 5 in-scope help categories have a published article
- [ ] Fin is enabled on the workspace
- [ ] Messenger snippet has been output
- [ ] `intercom fin manifest` shows Fin as active
