# Potential Improvements

Ideas worth exploring to make the documentation system even more robust. Evaluate and promote into the docs or an ADR when you are ready to act.

## Automation & Tooling

- Provide a bootstrap script (e.g., `scripts/bootstrap-docs.sh`) that creates the directory tree, copies templates into place, and seeds initial files so agents can kick-start the workflow with a single command.
- Add lightweight checks (pre-commit or CI) that verify `docs/project/progress.md` was updated in branches that touch source code, and flag missing backlinks between designs, specs, implementation journals, and feature cards.

## Documentation Enhancements

- Create an `archive/README.md` with a short how-to and a reusable “Archived on YYYY-MM-DD because…” blurb so agents archive consistently.
- Expand the agent briefing with example session flows or prompt snippets tailored to specific assistants if you standardise on them.

## Process Ideas

- Consider a periodic review (monthly/quarterly) where an agent audits `docs/` for stale entries, ensuring roadmaps, TBDs, and feature cards stay current.
- Explore integrating the documentation workflow into PR templates or issue templates so contributors must link the relevant docs before merging work.
