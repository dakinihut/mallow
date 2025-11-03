# Specification Template

> Repeatable file template — copy into `docs/specs/` once a design is approved and you are ready to detail implementation.

> Convert an approved design into an actionable engineering plan. This document should make implementation straightforward and reduce ambiguity.

- **Feature / System Name:**
- **Design Source:** ../design/<file>.md
- **Author / Date:**
- **Status:** Draft / In Review / Approved

## Summary

- Short description of the functionality being delivered.
- Link to related roadmaps, TBD items, and ADRs.

## Requirements

- Functional requirements (behaviour, data mutations, user-visible states).
- Non-functional requirements (performance budgets, determinism constraints, networking expectations).

## Architecture & Modules

- Which crates/modules/plugins are touched.
- New modules or plugins to introduce.
- Diagrams or bullet flow if helpful.

## Data Model & Resources

- Components, resources, assets, or config structures to add or modify.
- Serialization/persistence considerations.

## Systems & Algorithms

- Steps, pseudo-code, or state machines describing the logic.
- Scheduling implications (Update, FixedUpdate, diagnostics, etc.).

## Input / Output

- Events/messages/commands consumed and emitted.
- UI or UX entry points (HUD changes, hotkeys).

## Testing Strategy

- Unit tests, integration tests, or headless app tests to write.
- Manual test plan notes (scenarios, debug commands).

## Tooling & Migration

- Data migrations or cleanup tasks.
- Editor or tooling support needed (if any).

## Telemetry & Observability

- Metrics to emit, logging level, tracing hooks.

## Risks & Mitigations

- Known tricky areas, fallback plans, and staged rollout thoughts.

## Task Breakdown

- [ ] Task 1 (granular, ideally <1 day)
- [ ] Task 2
- [ ] ...

## Open Questions

- Items needing answers before implementation starts. Link to TBD tracker entries.

## Approval Checklist

- [ ] Reviewed with engineering lead.
- [ ] Test strategy agreed.
- [ ] Risks acknowledged with owners.
