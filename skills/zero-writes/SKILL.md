---
name: zero-writes
description: Build authorized Zero mutators with safe optimistic execution, authoritative server reconciliation, hidden-column persistence, transaction boundaries, and server-only effects.
---

# Build Zero writes

Inspect the repository, installed Zero version, matching registry, permission helpers, schema exposure, and neighboring mutators before editing.

## Write sequence

1. Name the caller audience and required permission.
2. Define a minimal validated argument schema.
3. Authorize at mutator entry and verify every client-supplied tenant, row, and identity reference against trusted context.
4. Separate deterministic synced changes from server-only validation, hidden persistence, and external effects.
5. Make client execution safe and optimistic; make server execution authoritative and transactional.
6. Register the mutator in the matching authenticated or public registry.
7. Await authoritative completion whenever later behavior depends on authorization, persistence, credential validation, or an effect.

Keep raw secrets and private values out of synced fields, query responses, metadata, and results. Use the Zero-provided server transaction for hidden persistence so visible and hidden changes commit together. Do not generate IDs inside mutators when the mutator can run more than once.

## Verification

Test allowed and forbidden actors, missing targets, cross-tenant references, client execution, server execution, rejection, and reconciliation. Confirm that optimistic progress is not presented as authoritative success and that server-only effects run only after authorization.

## Completion checklist

- [ ] Caller, permission, arguments, target, and registry are explicit.
- [ ] Authorization is independent from read access.
- [ ] Client-safe synced behavior is separated from server-only behavior.
- [ ] Hidden values never enter synced state or results.
- [ ] Visible and hidden writes share the transaction boundary.
- [ ] Authoritative completion and rejection are handled by callers.
- [ ] Positive, forbidden, missing-target, rejection, and reconciliation cases are tested.
