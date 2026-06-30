# Aidan Schuster — Project Portfolio

Built end-to-end with Claude and Claude Code as my primary development partner. Each project below was self-directed, outside of any job or class, across a range of domains: trading infrastructure, personal data systems, and mobile apps.

Contact: schuster.aidan@gmail.com

---

## Aidan OS (Personal OS)

An AI-native personal dashboard that turns free-form input — text, voice notes, food photos — into structured tracking across tasks, habits, nutrition, goals, and net worth.

**How it works:** Capture happens through a Telegram bot and a web endpoint. Every input is classified by the Claude SDK (used as the primary vision and reasoning engine, with OpenAI Whisper/embeddings as a fallback), then routed into the right table and surfaced on a live dashboard.

**Stack:** Next.js 16 (App Router, Turbopack), TypeScript, Tailwind CSS v4, Supabase/Postgres with pgvector, deployed on Vercel with scheduled cron jobs.

**Highlights:**
- Unified multi-modal capture pipeline (text/voice/photo) with a regex-based fallback so classification degrades gracefully instead of failing
- Real external integrations: SimpleFIN for bank/net-worth sync, Google Health API (migrated off the deprecated Fitbit API)
- Custom Edge-compatible HMAC session auth
- A resilient `Loaded<T>` data layer so a missing integration never breaks the dashboard UI
- `CLAUDE.md` in the repo is a first-person build log written by Claude itself across our sessions — a literal record of an iterative, agentic build process

*Repo: [github.com/schusteraidan-droid/personal-os](https://github.com/schusteraidan-droid/personal-os) (private — contains personal financial and health data; access on request). Already audited: `.env.local` has never been committed and `.gitignore` correctly excludes all secret files.*

---

## Kalshi Trading Bot

A Python bot that trades on Kalshi, the CFTC-regulated event contract exchange, built by directing Claude Code to research Kalshi's API from scratch and scaffold the system.

**How it works:** Signs every request using Kalshi's RSA-PSS authentication scheme, polls live market state in the background, and manages long-running processes to act on that state.

**Stack:** Python, `cryptography` for request signing, `requests` for the API client.

*Repo is private (contains exchange API credentials); available on request.*

---

## bar-scene

A social/nightlife discovery mobile app built with React Native and Expo.

**Stack:** React Native, Expo, Supabase backend, native location and image-picker modules, with a companion Next.js web page for password reset.

*Repo in progress.*

---

## Background

Outside of these projects, I underwrite a ~$1M book of multinational accounts in a fast-paced, client-facing role with significant cross-border litigation exposure, and I was a founding member of the Helping Hands chapter at Michigan State University, where I mentored kids at underprivileged schools for a year and helped build the scheduling tool our chapter used to organize volunteers.
