# OpenClaw Workspace — Azera ⚡

My personal AI assistant, built on [OpenClaw](https://docs.openclaw.ai). This repo holds the workspace files that define who the agent is and how it behaves. My personal data is not included.

The agent runs on its own. It replies on Discord, keeps my journal and todos, checks email and calendar on a heartbeat, and keeps long-term memory in plain Markdown files inside an Obsidian vault.

## What's here

| File | Purpose |
|------|---------|
| [`AGENTS.md`](AGENTS.md) | Operating manual: memory model, safety red lines, Discord channel behaviors, the Notion todo flow, group-chat etiquette, heartbeat rules |
| [`SOUL.md`](SOUL.md) | Personality and values |
| [`IDENTITY.md`](IDENTITY.md) | Name, vibe, emoji |
| [`HEARTBEAT.md`](HEARTBEAT.md) | Periodic task checklist (left empty, so heartbeats make no API calls) |

## Highlights

- **File-based memory.** Daily logs (`memory/YYYY-MM-DD.md`) are periodically distilled into a curated `MEMORY.md`. The agent persists across sessions without a database.
- **Privacy by design.** `MEMORY.md` loads only in direct chats, never in group chats, so personal context can't leak to other people.
- **Integrations.** Discord (journal and reminders channels), Notion (`ntn` CLI as the single todo store), Google Calendar (`gog`), and an Obsidian vault as the workspace root.
- **Guardrails.** It asks before anything leaves the machine, uses `trash` instead of `rm`, inspects config before changing it, and checks for an existing open-source tool before building a custom one.
- **Proactive but quiet.** Heartbeat checks rotate through email, calendar, and weather. It stays silent at night and when nothing is new.

## What's excluded

`USER.md`, `MEMORY.md`, `TOOLS.md`, `memory/`, media, and all secrets are gitignored (see [`.gitignore`](.gitignore)). IDs and account emails in `AGENTS.md` are replaced with `<PLACEHOLDERS>`.

## Use it yourself

1. Install OpenClaw ([docs](https://docs.openclaw.ai)).
2. Copy these files into your workspace (`~/.openclaw/workspace`).
3. Replace the `<PLACEHOLDERS>` in `AGENTS.md` and edit `IDENTITY.md` and `SOUL.md` to fit your setup.

## License

[MIT](LICENSE)
