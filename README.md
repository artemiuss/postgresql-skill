# PostgreSQL Skill

A merged PostgreSQL skill repository for building and operating production PostgreSQL systems.

Default examples should stay compatible with broadly supported PostgreSQL releases. Newer features, including PostgreSQL 18 capabilities, are documented as version-specific options rather than repository-wide requirements.

This repository keeps `artemiuss/postgresql-best-practices` as the base and adds a small set of low-level Postgres operations references from a secondary source repository. The result is a broader skill: application-facing database engineering plus the internals needed to debug production behavior.

## Why This Name

- `postgresql-skill` is short, neutral, and easy to install as a skill directory name
- The repository still covers both database engineering and operational diagnosis
- The simplified name avoids carrying source-specific branding into the merged repository

## Scope

The repository now covers:

- Schema architecture and Table API design
- PL/pgSQL coding standards and naming conventions
- Migrations, CI/CD, testing, audit logging, and RLS
- Query tuning, indexing, JSONB, partitioning, vector search, PostGIS, and DWH patterns
- Process model, memory behavior, MVCC internals, WAL/checkpoints, and storage layout

## Installation

```bash
npx skills add artemiuss/postgresql-skill
```

## Sources

### Base Repository

Primary source:

https://github.com/wimolivier/postgresql-best-practices

Taken from the base repository:

- `SKILL.md`
- Markdown reference documents, now stored at the skill root

### Imported Operations References

Imported from:

https://github.com/planetscale/database-skills/tree/main/skills/postgres

Imported files:

- `process-architecture.md`
- `memory-management-ops.md`
- `mvcc-transactions.md`
- `wal-operations.md`
- `storage-layout.md`

Only generic Postgres operations and internals material was imported. Provider-specific hosting, CLI, and product documents were left out.

## What Changed Relative to the Base

- Renamed the skill to `postgresql-skill`
- Expanded the `SKILL.md` trigger/usage text to include runtime troubleshooting and incident analysis
- Added a dedicated `Operations Internals` section in `SKILL.md`
- Moved reference documents from `references/` to the skill root
- Removed the top-level SQL helper scripts from the packaged skill
- Added source provenance and third-party attribution for the imported documents

## Repository Layout

```text
postgresql-skill/
├── SKILL.md
├── README.md
└── *.md                         # root-level reference docs
```

## Attribution and Licensing

- The imported third-party references are covered by the MIT license from the source repository

## Notes

- The imported ops/internals references are documentation-only additions; they do not currently add new automated tests
