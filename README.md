# Mallow Documentation System

A reusable documentation workflow you can drop into any codebase so every feature has a clear paper trail—from the first idea through delivery and long-term maintenance. It is tuned for AI-assisted coding, vibe coding sessions, and other agent-led workflows where you want an assistant to narrate and preserve the context as the work evolves.

## Why teams use it

- Keeps AI coding partners, product, engineering, and delivery notes aligned via a lifecycle-focused folder tree.
- Ships with templates for designs, specs, implementation journals, feature cards, ADRs, technical references, and more.
- Enforces progress tracking through lightweight rituals like session logs and working roadmaps.
- Makes it easy for AI coding agents or human contributors to stay in sync because every step has a dedicated home.
- Archives old decisions without losing context by mirroring the active tree.

See `docs/README.md` for the full system tour and file-by-file responsibilities.

## How the workflow operates

1. Capture ideas inside `docs/design/`, mature them into approved specs in `docs/specs/`, and log build work in `docs/implementation/`.
2. Graduate completed work into polished reference cards in `docs/features/`.
3. Track planning rituals (roadmaps, TBDs, ADRs) inside `docs/project/` so stakeholders share a single source of truth.
4. Use `docs/tech/` for system-wide architecture and stack notes, and `docs/meta/` for contributor guidance or comms plans.
5. Retire anything stale into the mirrored folders inside `docs/archive/` with a short note explaining why it moved.

The templates under `docs/templates/` seed each stage so formatting stays consistent.

## Get started

- **New project**

  1. Copy the `docs/` directory into the root of your repository (commit it right away so agents can see it).
  2. Ask your AI coding partner to bootstrap the system. Example prompt:
     > “Initialize the documentation workflow in `docs/`: seed the progress log, roadmap, and tech stack templates, then summarize today’s plan in `docs/project/progress.md`.”
  3. Let the agent create the initial files from `docs/templates/` and confirm the entries before you start coding together.

- **Existing codebase**
  1. Copy the `docs/` directory into the repo.
  2. Prompt your assistant to backfill history. Example prompt:
     > “Migrate the important documentation into `docs/`: capture the architecture, active features, recent decisions, and outstanding TODOs. Use the templates and record anything missing in `docs/project/working-roadmap.md` and `docs/project/progress.md`.”
  3. Review the generated docs, add nuance the agent missed, and archive any superseded material by mirroring the structure under `docs/archive/` with an “Archived on <date> because…” note at the top.

## Configure your agent prompts

Add a short policy snippet wherever you configure assistants (e.g. `agents.md`, `copilot-instructions.md`, prompt presets, onboarding docs):

> “Obey the documentation workflow described in `docs/README.md`. Before coding, review the lifecycle and follow it ruthlessly: capture new work in design/spec/implementation journals, promote docs forward as progress happens, and keep `docs/project/progress.md` up to date with every session (even if no code changes). Maintain the roadmaps, TBD tracker, and ADRs, and archive superseded files into the mirrored folders under `docs/archive/` with a note explaining why. If a required doc is missing, create it from the matching template in `docs/templates/` before proceeding.”

Reinforce the same expectation in contributor guides, session kickoffs, or PR templates so humans and AI helpers keep the docs trustworthy.

## Maintenance checklist

- Update `docs/project/progress.md` during every working session (even “no doc change needed” should be noted).
- Promote files forward in the lifecycle—design → spec → implementation → feature—rather than duplicating content.
- Treat `docs/features/` as the front door for future readers: link back to designs, specs, ADRs, and implementation notes.
- Regularly prune or archive stale material to keep the active tree easy to scan.

## Folder naming tip

Stick with `docs/` (no leading dot). Hidden folders such as `.docs/` are easy to miss in editors, confuse static-site tooling, and can surprise collaborators. The plain `docs/` directory stays visible everywhere while still being easy to copy into any project root.

---

Have ideas to improve the workflow? Open an ADR under `docs/project/decisions/` to document the change before rolling it out.
