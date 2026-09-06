---
name: zero-setup
description: Set up Zero in a new or existing application and prove a complete scoped read and authorized write vertical slice. Use when adding Zero, configuring zero-cache or Zero Cloud, wiring auth, or establishing a first working integration.
---

<!-- If this document is updated, please also update the public repo: https://github.com/richardguerre/zero-skills -->

# Set up Zero

Integrate Zero into the target repository and leave a working, verifiable vertical slice. Adapt to the existing stack; do not impose a framework-specific layout.

## 1. Reconnaissance

Inspect the runtime, frontend, package manager, database and schema source, authentication, deployment model, migrations, environment conventions, existing providers, server endpoints, and installed Zero version. Read the current official [agent support](https://zero.rocicorp.dev/docs/agents) guidance and [`llms.txt`](https://zero.rocicorp.dev/llms.txt), then open the relevant install, schema, auth, query, mutator, configuration, and debugging pages.

Complete reconnaissance when you can name the integration points, source schema, auth context, cache/deployment boundary, and first suitable entity.

## 2. Resolve only material decisions

Ask one question at a time and skip anything the repository answers confidently. Ask about:

- frontend/runtime stack;
- schema source;
- Zero Cloud versus self-hosted `zero-cache`;
- authentication context passed to Zero;
- audiences and tenant/ownership boundaries;
- the entity for the first vertical slice.

Present the detected architecture, proposed files/configuration, environment variables, commands, and unresolved choices. Get confirmation immediately before installing packages, changing configuration, creating files, or changing schema exposure.

## 3. Establish the seams

Configure the client/provider, query and mutate endpoints, cache/deployment connection, authentication context, schema exposure, development scripts, and generated-file boundaries. Establish feature-local query and mutator modules, registries, and a permission boundary using the target project's conventions.

Do not edit generated schema output by hand. Treat synced schema as a client exposure allowlist, not the whole database schema.

## 4. Prove one vertical slice

Choose one entity and implement a complete path:

- a scoped `findMany` or `findOne` query;
- an independently authorized mutator;
- a client consumer;
- one allowed-actor test;
- one forbidden-actor or cross-tenant test;
- optimistic execution and authoritative server completion.

Generate IDs outside mutators when the client can create them. Keep secrets and server-only effects outside synced state.

## 5. Verify and hand off

Verify application startup, Zero connectivity, cache/replication behavior, query scope, mutator authorization, generated types, query performance, and the local reset/development loop. Record adapter choices and unresolved version differences. Hand future work to `zero-design`, `zero-reads`, `zero-writes`, `zero-authz`, `zero-migrations`, or `zero-verify`.

## Completion checklist

- [ ] Repository and installed Zero version inspected.
- [ ] Material setup decisions resolved and mutation confirmation obtained.
- [ ] Client, server, auth, schema exposure, and cache boundaries configured.
- [ ] Complete scoped read/write slice works.
- [ ] Allowed and forbidden behavior is tested.
- [ ] Optimistic and authoritative behavior is verified.
- [ ] Local development and troubleshooting handoff is recorded.
