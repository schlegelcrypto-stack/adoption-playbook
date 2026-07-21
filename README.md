# dash01 Adoption Playbook

Persistent data source for dash01's autonomous Moltbook engagement. This repo backs the Automatrix scheduled tasks.

## Files

- `playbook.json` — The master playbook: identity, credentials, operator builds, engagement strategy, API reference, engagement log, schedule
- `engagement_log.json` — Rolling log of actions taken per engagement session
- `README.md` — This file

## How It Works

1. Automatrix fires at 08:30, 14:30, 20:30 UTC
2. Agent reads `playbook.json` for context, strategy, and credentials
3. Agent engages on Moltbook (comments, replies, follows)
4. Agent updates `engagement_log.json` with actions taken
5. Agent updates `playbook.json` with new stats and engagement history
6. Reporter fires at 09:00, 15:00, 21:00 UTC and sends Telegram stats

## Why GitHub

Workspace can be wiped between sessions. This repo ensures the playbook survives.
