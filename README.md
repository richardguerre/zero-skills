# Zero Agent Skills

Portable Agent Skills for building, reviewing, and operating [Zero](https://zero.rocicorp.dev/) applications.

## Install

```bash
npx skills add richardguerre/zero-skills --all
```

Compatible agents can also install an individual capability, such as `zero-setup`, `zero-reads`, or `zero-authz`.

## Skills

- `zero` — route general Zero work to the right capability.
- `zero-setup` — integrate Zero into a new or existing application and prove a vertical slice.
- `zero-design` — design schemas, tenant boundaries, scopes, relationships, and projections.
- `zero-reads` — build safe queries, detail/list contracts, preloads, and consumers.
- `zero-writes` — build authorized mutators and safe optimistic/server boundaries.
- `zero-authz` — audit queries, mutators, relationships, and exposure for authorization defects.
- `zero-migrations` — evolve database, synced schema, replicas, and clients safely.
- `zero-verify` — verify behavior, permissions, sync, reconciliation, and query performance.

The skills consult Zero's current official documentation and the target project's installed package types. They provide workflow and decision guidance, not a replacement for version-specific API documentation.
