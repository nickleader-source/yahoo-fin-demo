# Yahoo Finance — Fin AI Agent PRD

## Overview

Yahoo Finance receives approximately 800,000 monthly inbound support contacts. The majority fall into five repeatable categories that are candidates for AI-first resolution:

- Account access and login issues
- Portfolio setup, import, and tracking questions
- Market data accuracy and quote delay questions
- Yahoo Finance Plus billing and subscription management
- Alerts and notification configuration

## Goal

Deploy Fin as the first point of contact for Yahoo Finance users. Fin should resolve the top 5 inbound categories autonomously without routing to a human agent.

## Scope

**In scope for v1:**
- Help center population covering the 5 categories above
- Fin enabled on the Yahoo Finance web messenger
- Messenger shown to authenticated users only (hide from anonymous visitors to reduce noise)
- Fin should never provide personalized investment advice — direct those questions to a financial advisor

**Out of scope for v1:**
- Phone / voice channel
- Integration with brokerage account data
- Personalized portfolio analysis

## Success Metrics

- Fin resolution rate > 60% within 30 days of launch
- Human escalation rate < 40% for scoped categories
- CSAT on Fin-handled conversations > 4.0 / 5.0

## Tone and Guardrails

- Friendly, concise, and factual
- Never speculate on stock prices or market direction
- Never provide investment advice or recommendations
- For billing disputes, always offer to escalate to a human agent
- Acknowledge when something is outside Fin's knowledge rather than guessing
