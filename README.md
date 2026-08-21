# AI Engineering Playbook

A versioned, technology-neutral delivery process for teams using AI coding
agents. It helps a project move from a requirement through architecture,
implementation, review, acceptance and release without leaving stale technical
context for the next developer.

This repository is a process kit, not an application template. It does not
provide a domain model, product requirements, implementation architecture or
technology-specific commands for a target project.

## Adopt The Playbook

Use this repository when a project has a stable baseline (normally its first
release or current `main`) and needs a consistent AI-assisted workflow.

1. Choose a tagged playbook version and one stack adapter.
2. Create a documentation-only bootstrap branch in the target project.
3. Copy the files from [`core`](core) and the selected adapter, then tailor all
   placeholders to the target project's actual code, tests and CI.
4. Add `PROCESS_BASELINE.md` using the supplied template. Record the adopted
   playbook version, adapter and local deviations.
5. Ask an AI agent to inspect the target project and produce its initial
   Knowledge Base maps, Skills and contribution workflow. It must not invent
   facts from this repository.
6. Open a bootstrap Pull Request. Review it against the real project, then
   merge it before beginning the next feature.

Start with [`core/ADOPTION_GUIDE.md`](core/ADOPTION_GUIDE.md). For a
TypeScript/Node.js project, then follow
[`adapters/typescript-node/README.md`](adapters/typescript-node/README.md)
and use its
[`BOOTSTRAP_PROMPT.md`](adapters/typescript-node/BOOTSTRAP_PROMPT.md).

For a project that already adopted an earlier version, follow
[`core/UPGRADE_GUIDE.md`](core/UPGRADE_GUIDE.md) instead of repeating
bootstrap.

## What To Copy

Copy the core process files and exactly one stack adapter. The target project
should own the resulting files so that its process remains visible,
reviewable and independently versioned.

Do not use a submodule or a live runtime dependency on this repository.
Adopt improvements through deliberate documentation Pull Requests.

## Repository Layout

```text
core/                         Technology-neutral workflow and templates
  AGENTS.md.template          Instructions for AI contributors
  CONTRIBUTING.md.template    Branch, PR, review, release and documentation rules
  PROCESS_BASELINE.md.template
  PRODUCTION_READINESS_BACKLOG.md.template
  docs/README.md.template     Documentation entry point
  docs/knowledge/README.md.template
  docs/skills/README.md.template
  .github/pull_request_template.md
  ADOPTION_GUIDE.md
  UPGRADE_GUIDE.md

adapters/
  typescript-node/            TypeScript/Node.js conventions and templates
```

## Versioning

The playbook uses semantic versioning.

- A patch release corrects wording or a template defect.
- A minor release adds an optional or backward-compatible practice/adapter.
- A major release changes a required workflow gate or migration expectation.

Each target project records its adopted version in `PROCESS_BASELINE.md`.
It decides when an update is useful; no playbook update is applied implicitly.

## Design Principles

- Current code and tests prove behavior; documentation is maintained context.
- Architecture is reviewed before implementation when the change is complex.
- Pull Requests are independent review artifacts, not a formality after work.
- Documentation changes according to factual impact, not mechanically.
- Manual acceptance records only actions actually executed by a human tester.
- A release is distinct from implementation, CI success and manual acceptance.

## Adding An Adapter

An adapter describes how the core process is applied to a technology family.
It may contain test and build gates, common failure modes, starter Knowledge
Base maps and reusable Skills. It must not encode a particular product's
business rules or architecture.

Use `adapters/typescript-node` as the reference shape for a new adapter.

## Status

Initial bootstrap baseline. The first review should validate that the core is
general enough for more than one project and that the TypeScript adapter does
not make assumptions about a particular framework.
