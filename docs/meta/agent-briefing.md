# Agent Briefing: Mallow Documentation Workflow

> Share this file with any AI assistant, agent, or copilot before it touches the codebase. It summarises the promises you must keep while working in this repo.

## Core Principles

- Follow the lifecycle in `docs/README.md`: **Design → Spec → Implementation → Feature → Archive**.
- Never leave undocumented work. If no doc change is needed, record the reason in `docs/project/progress.md`.
- Prefer updating existing artefacts over creating duplicates; promote files forward when work advances.

## Daily Rituals

1. **Before coding**
   - Review the latest entries in `docs/project/progress.md`, `docs/project/working-roadmap.md`, and any active implementation journals.
   - If work lacks a design/spec, create one from the matching template in `docs/templates/`.

2. **During a session**
   - Narrate commands, tests, and decisions in `docs/implementation/<topic>.md` and append a session log to `docs/project/progress.md`.
   - Update roadmaps, TBD tracker, or ADRs if scope, open questions, or decisions change.
   - Note any documentation debt you incur (e.g., missing diagrams) so it is not lost.

3. **After delivering**
   - Promote implementation notes into `docs/features/<name>.md` and link back to the design/spec/ADR.
   - Archive superseded docs by moving them into the mirrored folder in `docs/archive/` with an “Archived on YYYY-MM-DD because…” explanation.

## File Responsibilities

- `docs/design/` – User-facing problem statements, constraints, and desired outcomes (Seed: `templates/design-template.md`).
- `docs/specs/` – Technical blueprint for approved designs (Seed: `templates/spec-template.md`).
- `docs/implementation/` – In-flight build logs with checklists and status updates (Seed: `templates/implementation-template.md`).
- `docs/features/` – Shipped feature cards; the front door for readers (Seed: `templates/feature-template.md`).
- `docs/bugs/` – Active bug investigations and diagnostics (Seed: `templates/bug-template.md`).
- `docs/project/` – Planning rituals: progress log, roadmaps, backlog, future ideas, TBD tracker, ADRs.
- `docs/tech/` – Architecture overview (`templates/architecture-template.md`) and tech stack (`templates/techstack-template.md`).
- `docs/meta/` – Meta info such as this briefing or onboarding guides.
- `docs/templates/` – Source templates; do not edit directly without documenting the change via ADR.
- `docs/archive/` – History. Mirror the active structure and add a short note describing why an item was archived.

## When in Doubt

- Ask the question in the relevant doc (implementation journal, TBD tracker, or progress log) so the conversation is captured.
- If a file you expect is missing, create it from the proper template before continuing.
- Link everything: designs ↔ specs ↔ implementation ↔ features ↔ ADRs ↔ progress entries.
- Default to clarity over brevity; future readers (and agents) inherit these notes.
