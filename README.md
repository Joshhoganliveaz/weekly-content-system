# Weekly Content System

Automated weekly content brief generator for the Live AZ Co real estate team. A remote scheduled Claude agent runs every Monday at 7:00 AM Phoenix time, researches trending real estate content, generates weekly briefs for each team member, creates Trello cards with full shot lists and captions, and sends email notifications.

## Team Members Served

- **Robyn Gabrielson** (robyn@liveazco.com): 3 Scottsdale luxury reels per week
- **Jacqui** (Jacqui@liveazco.com): 1 Gilbert reel + 1 carousel or second reel per week
- **Josh Hogan** (josh@liveazco.com): Consolidated weekly summary

## Schedule

Every Monday at 7:00 AM Phoenix (2:00 PM UTC). Cron: `0 14 * * 1`

## How It Works

1. **Research** trending real estate content via Apify (YouTube Shorts, Instagram Reels)
2. **Generate** weekly content briefs using playbook templates and seasonal context
3. **Create Trello cards** with hooks, shot lists, and captions on the "Live AZ Co Social Media" board
4. **Send Gmail notifications** to each team member with their card summary and link

## Repo Structure

```
weekly-content-system/
├── CLAUDE.md                              — Agent system prompt (read on every run)
├── README.md                              — This file
├── playbook/
│   ├── robyn-reels-templates.md           — 6 reel templates with hooks, shots, scripts, captions
│   └── jacqui-gilbert-angles.md           — Gilbert-specific adaptations and hook bank
├── reference/
│   ├── seasonal-calendar.md               — Monthly content angles by season
│   ├── hashtag-sets.md                    — Curated hashtag groups by market and topic
│   └── hook-patterns.md                   — Hook formula patterns for generating fresh content
└── logs/
    └── YYYY-MM-DD.md                      — Weekly run logs (created by agent)
```

## Trello Board

Board: "Live AZ Co Social Media" (ID: `688446529cebc3cf35f0571e`)

Lists:
- **This Week**: Agent places new cards here each Monday
- **In Progress**: Team moves cards here when filming
- **Done**: Completed content (preserves hook history for deduplication)

## Design Spec

Full design spec: `~/Documents/Obsidian Vault/docs/superpowers/specs/2026-04-24-weekly-content-agent-design.md`
