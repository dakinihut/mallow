# BUG-XXXX – <Title>

> Repeatable file template — copy into `docs/bugs/BUG-XXXX.md` when documenting an issue. Update the identifier to match your tracker or repository naming scheme.

- **Reported By:**
- **Date Reported:**
- **Current Status:** Triaged / In Progress / Blocked / Ready for Review / Verified / Archived
- **Severity & Impact:** Blocker / High / Medium / Low – describe affected users or systems
- **Affected Releases / Environments:**
- **Related Tickets / Links:** Issue tracker IDs, support cases, slack threads, etc.

## Summary

- One-paragraph overview of the defect and the symptoms users observe.
- Note any known workarounds.

## Environment Details

- Application version / commit SHA.
- Platform (OS, browser, device) and configuration (feature flags, locale, permissions).
- Data setup or accounts used during reproduction.

## Reproduction Steps

1. Step-by-step actions to trigger the bug.
2. Include data inputs or prerequisites required.

## Expected Behaviour

- Describe what should happen when the steps above are followed.

## Observed Behaviour

- Detail what actually occurs, including error messages, screenshots, or log excerpts.

## Impacted Areas

- Modules, components, services, or files suspected to be involved.
- Downstream systems or teams potentially affected.

## Tests & Diagnostics

- Existing automated tests covering this flow (and whether they pass or fail).
- Manual checks completed or planned.
- Additional diagnostics to run (profiling, logging, tracing, telemetry queries).

## Debugging Notes

- Hypotheses being investigated.
- Instrumentation added or code paths inspected.
- Links to experiment branches or throwaway scripts.

## Progress Log

| Date       | Owner | Notes / Commands / Findings |
| ---------- | ----- | --------------------------- |
| YYYY-MM-DD | Name  | Initial triage summary      |

## Fix Plan

- Outline the approach to remediate the bug (code changes, rollbacks, configuration adjustments).
- Checklist of tasks required, including pull requests, reviews, and documentation updates.

## Verification & Release

- Test cases executed after the fix (automated and manual) with results.
- Deployment or release plan, including feature flag rollouts if applicable.

## Follow-up Actions

- ADRs to draft, metrics to monitor, or regression tests to add.
- Backlog items or roadmap adjustments triggered by this bug.

## Resolution Summary

- Final outcome, including root cause and prevention notes.
- Date closed and link to verifying commit/PR.
