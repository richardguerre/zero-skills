---
name: zero-verify
description: Verify Zero setup and features through permissions, sync exposure, optimistic/server reconciliation, relationship behavior, query performance, and runtime troubleshooting.
---

<!-- If this document is updated, please also update the public repo: https://github.com/richardguerre/zero-skills -->

# Verify Zero behavior

Verify external behavior and data boundaries, not implementation wording. Inspect the repository's test tools, fixtures, schema exposure, auth context, query/mutator registries, and installed Zero version.

## Verification matrix

Exercise:

- allowed actor and intended tenant;
- forbidden actor and another tenant;
- missing target and invalid arguments;
- public versus authenticated projection;
- nested one-to-one and one-to-many visibility;
- soft-deleted parent and child;
- optimistic client execution;
- authoritative server completion;
- server rejection and reconciliation;
- hidden-field exclusion;
- query plan/index behavior for expensive reads;
- reconnect and replica behavior when relevant.

Use the highest available seam: integration tests with the real database/cache fixture before isolated helpers. A passing typecheck is not proof of authorization or sync safety.

## Troubleshooting order

Check repository configuration and package version, active query availability, query/mutate endpoint reachability, auth context, cache/replication state, generated schema, query plans, and connection status. Read current official debugging pages before inventing workarounds.

## Skill evaluation

Evaluate Agent Skills with realistic prompts in throwaway projects or fixtures. Grade changed artifacts and observable behavior, including negative cases; do not grade by checking for headings or skill names. Record prompt, fixture, version, selected capability, commands, result, and confusion to feed back into the owning skill.

## Completion checklist

- [ ] Positive and negative authorization behavior is proven.
- [ ] Public/private fields and relations are proven safe.
- [ ] Optimistic, authoritative, rejection, and reconciliation paths are proven.
- [ ] Missing targets and invalid inputs are covered.
- [ ] Query performance and relevant indexes are checked.
- [ ] Runtime/cache/replica behavior is verified or consciously out of scope.
- [ ] Evaluation records observable outcomes rather than prose matching.
