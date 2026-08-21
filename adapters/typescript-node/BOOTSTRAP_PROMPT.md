# TypeScript/Node.js Bootstrap Prompt

Give the following prompt to an AI agent working in the target project. Replace
the bracketed values before use.

```text
Adopt AI Engineering Playbook [version] using the TypeScript/Node.js adapter
for this repository. The project baseline is [tag or commit].

This is a documentation-only bootstrap task. Do not change production code,
dependencies, application configuration or deployment behavior.

Read the playbook adoption guide and TypeScript/Node.js adapter first. Then
inspect this repository's actual package manager, package.json scripts,
TypeScript configuration, lint/format setup, tests, CI workflows, runtime
entry points, external API boundaries, persistence/migrations and deployment
configuration.

Create a dedicated documentation branch and prepare a bootstrap PR containing:

- AGENTS.md and CONTRIBUTING.md tailored to verified local commands and rules;
- docs/README.md as the local documentation entry point;
- docs/knowledge/README.md plus only the architecture/test maps that this
  repository genuinely needs;
- docs/skills/README.md and only reusable stack-specific Skills;
- PROCESS_BASELINE.md recording the playbook version, adapter, project baseline
  and local deviations;
- PRODUCTION_READINESS_BACKLOG.md seeded only with real, evidenced gaps;
- .github/pull_request_template.md.

Do not copy technical claims, commands, architecture rules or debt from the
playbook. Every target-project claim must be backed by current code, tests or
CI. If a verification command cannot run, report why rather than claiming it
passed.

Open a draft PR and stop for independent review. Its description must include:
the chosen baseline, created files, code-backed facts, open assumptions,
commands actually run, documentation deliberately not created, and any
unresolved adoption questions.
```
