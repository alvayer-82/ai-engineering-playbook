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
configuration. Check environment-file hygiene without reading or printing
secret values, and identify the dependency-audit command actually available
through the project's package manager.

Create a dedicated documentation branch and prepare a bootstrap PR containing:

- AGENTS.md and CONTRIBUTING.md tailored to verified local commands and rules;
- docs/README.md as the local documentation entry point;
- docs/knowledge/README.md plus only the architecture/test maps that this
  repository genuinely needs;
- docs/skills/README.md and only reusable stack-specific Skills; an adapter
  starter Skill may be adopted only if it applies, with its playbook version
  recorded as its origin;
- PROCESS_BASELINE.md recording the playbook version, adapter, project baseline
  and local deviations;
- PRODUCTION_READINESS_BACKLOG.md seeded only with real, evidenced gaps;
- .github/pull_request_template.md.

Do not copy technical claims, commands, architecture rules or debt from the
playbook. Every target-project claim must be backed by current code, tests or
CI. If a verification command cannot run, report why rather than claiming it
passed.

Before opening the PR, verify that adopted documents contain no unresolved
bracketed placeholders such as `[path]`, `[facts]` or `[commit]`. Add a
production-readiness backlog item for secret/dependency hygiene only when
discovery finds a real, evidenced gap.

Open a draft PR and stop for independent review. Its description must include:
the chosen baseline, created files, code-backed facts, open assumptions,
commands actually run, documentation deliberately not created, and any
unresolved adoption questions.
```
