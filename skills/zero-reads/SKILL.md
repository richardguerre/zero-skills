---
name: zero-reads
description: Build safe and efficient Zero queries, list/detail contracts, preloads, relationship projections, audience registries, and client read consumers.
---

# Build Zero reads

Inspect the repository, exact installed Zero version, schema exposure, permission helpers, registries, neighboring queries, and relevant official docs before editing.

## Choose the read contract

- Use `findMany` for a collection with explicit filters, ordering, and limits.
- Use `findOne` for a singular detail resource and its intentionally bounded relationship graph.
- Use `preload` only to warm a separately scoped query; preloading never widens authorization.

Keep arguments to route keys and genuine feature filters. Validate them with the project's schema validator. Derive result types from query definitions when the consumer needs them.

## Build the query

1. Apply audience/policy scope in the query expression.
2. Apply tenant and entity filters through trusted relationships or keys.
3. Apply soft-deletion policy explicitly.
4. Add related records only through constrained relationship callbacks.
5. Add ordering, limits, and nested visibility at the relationship that owns them.
6. Register the query in the matching public or authenticated registry.

Client-side filtering is presentation logic, never authorization. Do not run a conditional query with unresolved route or auth input if that could produce a broader result.

## Consume and verify

Use reactive reads for UI state, imperative complete reads when server-complete data is required, and preload for intentional warming. Preserve loading, error, and incomplete-result distinctions. Trace every returned field and relation back to its exposure and policy. Analyze expensive query plans and add/index relationships in the source database as needed.

## Completion checklist

- [ ] Query contract and cardinality are explicit.
- [ ] Audience, tenant, entity, and deletion filters are in the expression.
- [ ] Every relationship has its own visibility/filter/order/limit policy.
- [ ] Correct registry and consumer are used.
- [ ] Conditional inputs cannot issue a broader query.
- [ ] Public/private fields and relations were reviewed.
- [ ] Positive, forbidden, missing-target, and related-row leakage cases are tested.
- [ ] Query plan and indexing were checked when needed.
