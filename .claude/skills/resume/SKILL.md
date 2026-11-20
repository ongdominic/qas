---
name: resume
description: Load one project's context so work can continue where it stopped. Reads the project's CLAUDE.md, _brief.md and recent _log.md entries, then states where things stand and the next actions. Use when the user says "let's work on <project>", "where was I with <project>", "resume <project>", or names a project at the start of a session.
argument-hint: "<project name, partial match ok>"
allowed-tools: Read Glob Grep Bash(git pull *) Bash(git log *)
---

# Resume a project

Project requested: $ARGUMENTS

## Steps

1. Run `git pull --rebase --autostash` so this device has the latest notes. On conflict, stop and tell the user.
2. Find the folder: match `$ARGUMENTS` against `10 Projects/*/` (case-insensitive, partial). If nothing matches, try `20 Areas/*/`. If several match, list them and ask. If none, list the active projects from `90 System/core/projects-index.md`.
3. Read, in this order and nothing else unless needed:
   - `<folder>/CLAUDE.md` (project rules, tools, contacts, locations)
   - `<folder>/_brief.md` (current state)
   - The last 5 dated entries of `<folder>/_log.md`
   - Notes in `00 Inbox/` that mention the project name (list them only)
4. Check `git log -5 --format="%ad %s" --date=short -- "<folder>"` to see when it last changed.

## Reply format

**<Project>**: last touched <date>

- **Status:** two sentences max
- **Open items / next actions:** up to 5 bullets, from the brief and log
- **Waiting on:** people or events, with dates if known
- **Unfiled inbox notes about this:** list, or "none"

Then ask what to work on. Do not load `docs/` files until the task needs them; open only the specific file required.

## Notes

- If the brief and the log disagree, trust the newer log entry and say so.
- If `_brief.md` is missing or empty, offer to write it from the log and docs.
- This skill is read-only. It never writes or pushes.
