# PostgreSQL Skill

A merged PostgreSQL skill repository for building and operating PostgreSQL 18+ systems.

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

## Sources

### Base Repository

Primary source:

- `https://github.com/artemiuss/postgresql-best-practices`

Taken from the base repository:

- `SKILL.md`
- `references/` directory
- `scripts/` directory
- `tests/` directory
- `CLAUDE.md`

### Imported Operations References

Imported from:

- `https://github.com/planetscale/database-skills/tree/main/skills/postgres`

Imported files:

- `references/process-architecture.md`
- `references/memory-management-ops.md`
- `references/mvcc-transactions.md`
- `references/wal-operations.md`
- `references/storage-layout.md`

Only generic Postgres operations and internals material was imported. Provider-specific hosting, CLI, and product documents were left out.

## What Changed Relative to the Base

- Renamed the skill to `postgresql-skill`
- Expanded the `SKILL.md` trigger/usage text to include runtime troubleshooting and incident analysis
- Added a dedicated `Operations Internals` section in `SKILL.md`
- Kept the base scripts and test suite intact
- Added source provenance and third-party attribution for the imported documents

## Repository Layout

```text
postgresql-skill/
├── SKILL.md
├── CLAUDE.md
├── README.md
├── THIRD_PARTY_NOTICES.md
├── references/                  # 39 reference docs
├── scripts/                     # 4 SQL helper scripts
├── tests/                       # inherited PL/pgSQL test suite
└── licenses/
    └── third-party-MIT.txt
```

## Attribution and Licensing

- The imported third-party references are covered by the MIT license from the source repository
- A copy of that license is included at `licenses/third-party-MIT.txt`
- A short attribution summary is included in `THIRD_PARTY_NOTICES.md`

## Notes

- The test suite is inherited from the base repository and primarily validates the original `artemiuss` patterns
- The imported ops/internals references are documentation-only additions; they do not currently add new automated tests
