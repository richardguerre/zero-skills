---
name: zero-authz
description: Audit an existing Zero application for tenant leaks, missing ownership checks, identity impersonation, unsafe public exposure, relationship leaks, and unauthorized mutator effects.
---

<!-- If this document is updated, please also update the public repo: https://github.com/richardguerre/zero-skills -->

# Audit Zero authorization

This is an evidence-backed review workflow. Inspect repository instructions, installed Zero version, schema exposure, query/mutator registries, auth context, policy helpers, and relationship definitions before reporting findings.

## Audit each boundary

For every public or authenticated query:

- identify the audience and trusted viewer context;
- trace tenant and ownership policy into the query expression;
- inspect soft-deletion and entity filters;
- inspect every related row and projection independently;
- check fields and relations against synced exposure.

For every mutator:

- verify entry authorization independent of query access;
- verify client-supplied workspace, row, and identity references;
- inspect optimistic and authoritative paths;
- check hidden persistence and server-only effects;
- check rejection and reconciliation behavior.

## Report findings

Report severity, evidence, affected boundary, exploit scenario, data/effect at risk, and a concrete remediation. Distinguish confirmed defects from design questions. Add negative tests for forbidden actors, cross-tenant rows, public/private projection boundaries, and identity supplied by arguments.

## Completion checklist

- [ ] All public and authenticated registries were inspected.
- [ ] Every query has a traced policy and tenant boundary.
- [ ] Every nested relation and exposed field was reviewed.
- [ ] Every mutator has independent authorization and safe server effects.
- [ ] Sensitive and oversized fields are excluded where required.
- [ ] Findings include evidence and remediation.
- [ ] Negative tests cover confirmed security boundaries.
