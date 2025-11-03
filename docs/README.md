# Documentation System Overview

This repository follows a reusable documentation pipeline you can copy to any project. Each folder represents a stage in the feature lifecycle, from early concept through shipped reference material and eventual archiving.

## Directory Layout

```
docs/
├── README.md               # You are here – how to navigate and maintain this system
├── incoming.md             # Ad-hoc task inbox; triage items with an agent before filing them
├── design/                 # Product & intent
├── specs/                  # Engineering blueprints once a design is approved
├── implementation/         # In-flight implementation journals and hand-off notes
├── features/               # Final reference cards for shipped functionality
├── bugs/                   # Active bug investigations, diagnostics, and fix journals
├── project/                # Planning rituals (roadmaps, progress log, ADRs, TBD tracker)
│   ├── decisions/          # ADR files capturing why a choice was made (seed from `templates/adr-template.md`)
│   ├── progress.md         # Session-by-session changelog (seed from `templates/progress-template.md`)
│   ├── roadmap.md          # Long horizon goals (seed from `templates/roadmap-template.md`)
│   ├── working-roadmap.md  # Current WIP focus (limited, actionable list; seed from `templates/working-roadmap-template.md`)
│   ├── future-ideas.md     # Free-form wishlist of early concepts (seed from `templates/future-ideas.md`)
│   └── tbd-tracker.md      # Open design or technical questions (seed from `templates/tbd-tracker-template.md`)
├── meta/                   # Meta project information (marketing ideas, contributor guides, release comms, vendor notes)
├── tech/                   # Cross-cutting engineering notes (architecture, stack)
│   ├── architecture.md     # System architecture overview and external integrations
│   └── techstack.md        # Runtime environment, frameworks, and dependency versions
└── archive/                # Mirror of the tree above; create matching subfolders to store retired material
```

Everything in `archive/` retains the same relative structure as its active counterpart so historical trails are easy to follow.

## Feature Lifecycle

1. **Ideation (`design/`)**

   - Describe the user-facing problem, desired outcomes, constraints, and the systems it touches.

- Keep the language approachable; focus on user experience, workflows, and sequencing rather than code.
- Seed design docs from `templates/design-template.md` into `design/<topic>.md`.

2. **Specification (`specs/`)**

   - Promote a vetted design into a spec file.
   - Capture data models, component/resource changes, algorithm notes, migration considerations, testing strategy, and success criteria.

- Link back to the design doc; list assumptions and known risks.
- Seed specs from `templates/spec-template.md` into `specs/<topic>.md` once a design is approved.

3. **Implementation (`implementation/`)**

   - Create an implementation journal when coding begins.

- Break the work into granular checklist items (one action per bullet) so progress can be tracked transparently.
- Log date-stamped progress, commands run, test results, decisions made, and deviations from the spec.
- Reference commits/PRs where possible so another developer (or future you) can resume work midstream.
- Seed implementation journals from `templates/implementation-template.md` into `implementation/<feature>.md` before writing code.

4. **Feature Reference (`features/`)**

   - After successful delivery, summarise the final behaviour, configuration knobs, failure modes, and extension hooks.

- Include links back to the spec, design, ADRs, and implementation journal for deeper context.
- Treat this as the “front door” when someone wants to understand the feature later.
- Seed feature cards from `templates/feature-template.md` in `features/`.

5. **Archival (`archive/`)**
   - When a design/spec/implementation/feature becomes obsolete, move the relevant files into the mirrored folder inside `archive/`.
   - Append a short note at the top explaining when and why it was archived.

## Project Management Rituals

- **`project/roadmap.md`** – High-level destination and phased objectives. Review quarterly or whenever strategy changes.
  - Seed the first version from `templates/roadmap-template.md`.
- **`project/working-roadmap.md`** – Enforce Kanban-style WIP: keep **2 active items max**, document acceptance criteria, and list a small “Next Up” queue plus a backlog section.
  - Seed the structure from `templates/working-roadmap-template.md` and maintain it as a single living doc.
- **`project/backlog.md`** (optional) – Capture design-heavy or future-phase items with acceptance criteria before promoting them into the active queue, noting whether each entry introduces a new feature or updates an existing one.
- **`project/future-ideas.md`** (optional) – Use as a low-friction parking lot for rough ideas that are not yet ready for the backlog; revisit it periodically and promote promising entries when they mature.
  - Seed the file from `templates/future-ideas.md` and reuse its sections per idea.
- **`project/progress.md`** – Append concise session summaries; include the docs touched, tests run, and next steps.
  - Seed each entry from the block in `templates/progress-template.md` and append it to the file.
- **`project/tbd-tracker.md`** – Register unresolved questions from design, specs, or implementation. Replace inline `[TBD]` markers with tracker IDs.
  - Seed the tracker from `templates/tbd-tracker-template.md`.
- **`project/decisions/ADR-XXX.md`** – Record significant technical or design choices with context, decision, and consequences.
  - Seed each ADR from `templates/adr-template.md` before filling in the specifics.

## Incoming Work Queue

- **`incoming.md`** – Drop quick tasks, refactors, or questions that do not yet have a home.
  - Separate each entry with a standalone `---` line so agents can parse them reliably (copy the snippet from `templates/incoming-template.md` if you like).
  - When you or your assistant triage the file, clarify the context, then promote the item into the right doc (design/spec/implementation/feature/bug/meta/etc.).
  - After filing the work, log the decision in `project/progress.md`, update relevant planning docs, and delete the processed block from `incoming.md` to keep the inbox lean.

## Bug Investigation Workflow

- **`bugs/BUG-ID.md`** – Seed bug journals from `templates/bug-template.md` when you open an issue. Capture reproducible steps, environment details, and expected vs. observed behaviour upfront.
  - Log diagnostics as you go (logs, traces, profiling results) and note which modules, files, or services are implicated.
  - Keep a progress diary of hypotheses, commands run, and experiments so others can resume the investigation quickly.
  - Record verification steps once the fix lands; move resolved entries into `archive/bugs/` with a short resolution note.

## Meta Documentation

- **`meta/`** – Collect broader project context (marketing calendars, contributor guides, release comms scripts, partner/vendor notes, community engagement plans, operational playbooks).
  - Group related material in subfolders (`marketing/`, `ops/`, etc.) to keep navigation tidy.
  - Retire outdated artefacts by moving them into `archive/meta/` and annotating when/why they were archived.

## Tech References

- Use `tech/architecture.md` to capture major components, how they interact, and key integration points with external services.
- Use `tech/techstack.md` to record runtime environments, frameworks, language versions, and other critical dependencies.
- When architecture or tooling shifts, update these docs **and** link to the relevant ADR or spec.

## Templates

- Each file in `docs/templates/` is marked as either a **repeatable file template** (copy it whenever you need a fresh document of that type) or a **singleton document template** (seed a specific shared doc—such as `project/future-ideas.md`—by copying this file once, then maintain the live doc in place).
- Whenever you spin up a new document, use the relevant template in `docs/templates/`, rename it in place, and start filling in the placeholders.
- Reuse the markdown skeletons under `docs/templates/` when drafting new design docs, specs, implementation journals, feature cards, bug investigations, roadmaps, progress entries, future idea dumps, ADRs, and other planning artifacts.
- Tailor the placeholders, but keep the section headings intact so future automation can parse them consistently.

## Contributor Expectations

- Start every session by skimming this README to locate the correct stage.
- Do not begin implementation work without a vetted design and spec. If they do not exist, collaborate to create them before writing code.
- Whenever you create or revise a **design**, **spec**, or **implementation** doc, run through the relevant template and surface clarification questions (requirements, dependencies, risks) before proceeding. Confirm the answers inside the document so gaps are closed early.
- Whenever you modify a doc, check for links that need updating (README, AGENTS, specs, features, etc.).
- Keep filenames lower-case with hyphens, and use relative links (`../design/foo.md`) to ease future moves.
- Prefer editing rather than replacing history; archive old context so we keep a durable knowledge base.
- LLM or human, narrate progress in `project/progress.md` and note any docs you touched during the work.
- When in doubt about where something belongs, ask in the implementation journal or progress log so the decision gets recorded.

### Mandatory doc-update checklist (apply before closing any task)

1. Append a dated entry to `project/progress.md` covering code changes, docs touched, and verification steps (tests/checks).
2. Reconcile `project/working-roadmap.md`: mark completed items, capture “Next” bullets, and move backlog entries into or out of the active list as scope shifts.
3. Confirm design/spec/implementation/feature docs reflect the latest intent; author or revise them if the work departs from existing plans.
4. Move superseded material into the mirrored folder under `archive/`, annotate with when/why it was retired, and repair any links.
5. Update cross-cutting references (`tech/architecture.md`, `tech/techstack.md`, ADRs, templates) whenever architecture or workflow has changed.
6. If the work truly requires no documentation change, note the reason explicitly in `project/progress.md` (“No doc change needed: …”).

This structure is intentionally lightweight but enforceable. Copy it to new projects, adjust folder names if necessary, and keep the lifecycle moving in one direction: **Design → Spec → Implementation → Feature → Archive**.
