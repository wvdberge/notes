# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

Personal Zettelkasten knowledge base in Obsidian. One vault covering academic work, teaching, and personal ideas.

## Directory structure

- `inbox/` — fleeting notes captured from phone/iPad; processed weekly into permanent notes or discarded
- `notes/` — permanent atomic notes; evergreen insights that transcend any single project
- `references/` — literature notes, one per paper
- `templates/` — note templates
- `attachments/` — images/PDFs; **not tracked in git**

## Sync

- Git remote: GitHub (private)
- Mobile sync via the **obsidian-git** plugin (auto-commit on file change, auto-pull every 10 min)
- Commit message format: `vault backup: YYYY-MM-DD HH:mm:ss`
- `attachments/` and Obsidian workspace files (`.obsidian/workspace.json`) are gitignored

## Note-writing conventions

- **Inbox notes** are rough captures — titles can be anything, content can be incomplete
- **Permanent notes** (`notes/`) should be atomic (one idea per note) and written in your own words
- **Reference notes** (`references/`) are one-per-paper and link to related permanent notes
- Wikilinks (`[[note title]]`) are the primary connection mechanism — links are the value

## Inbox processing

When asked to process the inbox, read all notes in `inbox/` and triage each one:

1. **Evergreen → `notes/`** — the idea is general, reusable across projects, and worth keeping as a permanent atomic note. Rewrite it in a clear, standalone way if needed.
2. **Project-specific → project folder** — the idea is only relevant to a concrete project. Ask which project folder to move it to if unclear, or suggest one based on the content.
3. **Discard** — the note is a one-off reminder or already acted on. Flag it for deletion and confirm before removing.

For each inbox note, state your triage decision and reasoning before moving or rewriting anything. Move files with `git mv` so the rename is tracked.

Project folders live outside this vault on the same disk:

- `/Volumes/Samsung2TB/academia/research/` — research projects
- `/Volumes/Samsung2TB/academia/teaching/` — teaching projects
- `/Volumes/Samsung2TB/personal/` — personal projects

When moving a project-specific note, use a plain `mv` (not `git mv`) since the destination is outside this repo. Ask which project subfolder to use if the note could fit more than one.

## What belongs here vs. academia/

| This vault | academia/ |
|---|---|
| Evergreen insights and concepts | Project TODOs and working notes |
| Literature notes (one per paper) | Draft text and data decisions |
| Cross-project ideas | Meeting notes |
| Personal reflections | Code and output |
