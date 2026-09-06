---
name: zero
description: Route Zero work to the focused setup, design, reads, writes, authorization-audit, migration, or verification workflow. Use for any Zero integration, schema or policy design, query or mutator work, security review, synced-schema migration, or Zero testing and troubleshooting.
---

<!-- If this document is updated, please also update the public repo: https://github.com/richardguerre/zero-skills -->

# Zero

Use this as the entry point for Zero work. Inspect the target first, then choose one primary capability. The router routes; it does not duplicate capability instructions.

## Inspect before routing

1. Read the target repository's agent instructions and architecture decisions.
2. Inspect its package manifest, lockfile, database/schema source, Zero configuration, providers, query and mutator registries, auth integration, and server endpoints as applicable.
3. Determine the installed Zero version and confirm unfamiliar APIs against installed exports and types.
4. Read Zero's current [`llms.txt`](https://zero.rocicorp.dev/llms.txt), then open only relevant official Markdown pages.

Complete inspection when the repository shape, installed version, local standards, and relevant official sources are known.

## Route the primary outcome

| Outcome | Skill |
| --- | --- |
| Install or integrate Zero and prove the first end-to-end slice | `zero-setup` |
| Design synced schema, tenant/policy scopes, relationships, or projections | `zero-design` |
| Build queries, list/detail contracts, preloads, or read consumers | `zero-reads` |
| Build mutators, write authorization, optimistic/server behavior, or effects | `zero-writes` |
| Audit an existing boundary for leaks, impersonation, or unsafe exposure | `zero-authz` |
| Evolve database and synced schema, backfill data, or plan rollout | `zero-migrations` |
| Prove permissions, sync, reconciliation, performance, or runtime behavior | `zero-verify` |

For a cross-cutting request, choose the skill that owns the requested deliverable and consult a secondary skill only for decisions it owns. A new app needing its first query and mutator remains `zero-setup`; a query feature is `zero-reads`; a security audit is `zero-authz`.

If a focused skill is unavailable, say which one is missing and continue with repository-native guidance plus current official documentation. Do not silently substitute another capability.

## Router checklist

- The target repository and exact installed Zero version were inspected.
- One primary capability owns the deliverable.
- Version-sensitive behavior was checked against installed types and current official docs.
- Repository-specific conventions were kept separate from portable Zero guidance.
