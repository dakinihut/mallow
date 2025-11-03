# Architecture Overview Template

> Copy to `docs/tech/architecture.md` when you set up a new project, or whenever the system’s architecture is overhauled.

## System Context

- High-level description of the product or service.
- Core user journeys or system responsibilities.
- External integrations and upstream/downstream dependencies.

## Component Map

- List the major components/services/modules.
- For each component: role, owners, data it manages, critical interactions.
- Include diagrams (link to image files) if helpful.

## Data Flows & Contracts

- Key APIs, events, or queues between components.
- Data models or schemas that must stay in sync.
- Performance/SLA expectations.

## Operational Guarantees

- Deployment model, hosting regions, scaling strategy.
- Observability stack (metrics, logs, tracing).
- Disaster recovery and backup considerations.

## Change History

- YYYY-MM-DD – Summary of architectural shift (link to ADR/spec/PR).
