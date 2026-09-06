---
name: zero-design
description: Design a Zero-backed data and authorization model before implementation, including synced schema exposure, tenant boundaries, policy scopes, relationships, and public/private projections.
---

# Design Zero boundaries

Produce a concrete design that a reads or writes implementation can follow. Inspect the target repository, installed Zero version, schema source, auth model, and current official docs first.

## Design sequence

1. Name the audiences, viewer identity, tenant boundary, ownership rule, and operation permissions.
2. Separate database schema from synced exposure. Mark sensitive, oversized, derived, and server-only fields.
3. Define policy scopes independently from route/entity filters and soft-deletion policy.
4. Map one-to-one and one-to-many relationships. For each related collection define visibility, deletion, ordering, and limits.
5. Define public, authenticated, and privileged projections. A safe parent query does not make every related row safe.
6. Choose the highest reusable seam: policy predicate, tenant scope, entity scope, projection, query, or mutator authorization.
7. State the positive and negative behaviors that must be tested.

## Design rules

- Treat query expressions as the read-authorization boundary.
- Require every mutator to authorize independently; readable does not mean writable.
- Enforce tenant membership through trusted context and relationship traversal, not an unchecked client tenant ID.
- Make singular versus collection contracts explicit.
- Keep public projections intentionally narrower than Admin or privileged projections.
- Add a reusable helper only when its policy is stable and genuinely shared.

## Completion checklist

- [ ] Audience, viewer, tenant, ownership, and operation permissions are explicit.
- [ ] Synced versus hidden fields are identified.
- [ ] Policy, tenant/entity, and soft-deletion scopes are separate.
- [ ] Relationship cardinality and nested visibility are defined.
- [ ] Public/private projections are defined.
- [ ] Reads and writes have named implementation seams.
- [ ] Allowed, forbidden, missing-target, and cross-tenant cases are listed.
