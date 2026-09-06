---
name: zero-migrations
description: Safely evolve a Zero-backed database, synced schema exposure, replicas, backfills, and clients without breaking compatibility or leaking data.
---

# Migrate a Zero application

Inspect the database migration system, Zero schema/exposure configuration, generated artifacts, cache/deployment model, active clients, and installed Zero version first.

## Rollout sequence

For additive changes, expand in this order: database, server/Zero exposure, then clients. Backfill before exposing dependent behavior. Verify replica and query compatibility before rollout.

For removals or contract changes, contract in reverse: clients, server/Zero exposure, then database. Keep old and new forms compatible during the migration window.

## Migration workflow

1. Define the old and new contracts, affected audiences, fields, relations, queries, and mutators.
2. Add the database shape without breaking existing callers.
3. Backfill with bounded, observable, resumable work when needed.
4. Expose the new Zero shape only after the database is ready.
5. Migrate clients and verify optimistic/server behavior.
6. Remove the old contract only when no caller, replica, or in-flight operation requires it.

Treat generated files according to the target project's conventions. Never use a broad destructive reset without explicit scope, backup/recovery information, and replica cleanup guidance.

## Completion checklist

- [ ] Old/new contracts and affected boundaries are recorded.
- [ ] Rollout order is compatible with existing clients and replicas.
- [ ] Backfill is safe, observable, and verified.
- [ ] Synced exposure and nested relationships were reviewed.
- [ ] Permissions and optimistic/server behavior were tested.
- [ ] Removal has a caller/replica compatibility check and recovery plan.
