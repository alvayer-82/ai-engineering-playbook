# TypeScript/Node.js Adapter

This adapter helps a TypeScript/Node.js project apply the core workflow. It is
framework-neutral: it does not assume React, Next.js, Express, NestJS, a
database, a package manager or a deployment platform.

## Adoption Steps

1. Copy `core` templates into the target repository.
2. Copy the starter maps in this adapter and populate them from actual code.
3. In `AGENTS.md`, record exact commands for install, typecheck, lint, unit,
   integration, end-to-end and build verification.
4. In `CONTRIBUTING.md`, name CI workflows, branch protection and release
   artifact/deployment rules.
5. Use the review checklist below in the bootstrap PR.

## Required Stack Discovery

The bootstrap agent must inspect:

- `package.json` and lockfile to identify the package manager and scripts;
- `tsconfig*.json`, lint/format configuration and generated-code rules;
- test configuration and test directories;
- CI workflows and environment-variable handling;
- application entry points, module boundaries and API contracts;
- schema/migration tooling, if a database exists;
- deployment/runtime configuration.

## Typical Verification Layers

Record only layers that actually exist:

| Layer | Common evidence | Questions |
| --- | --- | --- |
| Static checks | `tsc --noEmit`, lint, formatting | Does CI run the same commands? |
| Unit tests | Vitest, Jest or node:test | Which pure rules do they prove? |
| Integration tests | database, HTTP or module boundary tests | Which real infrastructure boundary is covered? |
| Contract tests | API/schema checks | What consumer or public contract is protected? |
| End-to-end tests | Playwright, Cypress or equivalent | Which user workflows remain manual? |
| Build/package | package build and artifact check | Can the artifact run with production config? |

## TypeScript-Specific Review Questions

- Is a type-safe interface hiding a runtime validation gap at an API boundary?
- Are environment variables validated and documented without exposing secrets?
- Does an async failure preserve exactly-once behavior where a side effect may
  have completed before a network failure?
- Are database migrations forward-compatible, reversible where required and
  represented in CI?
- Does a browser state update protect against stale requests, cancelled views
  and late responses where the product needs that behavior?
- Do package-lock changes correspond to a conscious dependency decision?

## Initial Knowledge Base Maps

Use the included starter files only after replacing placeholders with verified
facts. Add maps as the system requires; do not create documents with no reader
or purpose.

- [`docs/knowledge/architecture-map.md.template`](docs/knowledge/architecture-map.md.template)
- [`docs/knowledge/test-coverage-map.md.template`](docs/knowledge/test-coverage-map.md.template)
- [`docs/skills/typescript-change-review.md.template`](docs/skills/typescript-change-review.md.template)
