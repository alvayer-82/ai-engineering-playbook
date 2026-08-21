# Versioning Policy

This repository versions its process, not its users' applications.

## Playbook Versions

Use semantic versioning for release tags:

- `MAJOR`: a required gate, adoption contract or template migration changes in
  a way that target projects must consciously adapt.
- `MINOR`: a new adapter, optional template or backward-compatible improvement.
- `PATCH`: a correction that does not change the required process.

Before releasing a version, update `CHANGELOG.md` and state whether existing
projects need action.

## Target Project Baselines

Each adopting project stores its own `PROCESS_BASELINE.md` with:

- adopted playbook tag;
- selected adapter (the adapter uses the same tag as the playbook);
- target baseline commit;
- local commands and deviations;
- date and reviewer of the bootstrap documentation PR.

The target project does not automatically inherit subsequent playbook changes.
It upgrades through a reviewed documentation Pull Request.

## Adapter Versions

Adapters are released together with the core and have no independent semantic
version. For example, a project using `typescript-node` from playbook `v1.2.0`
records `Adapter: typescript-node (playbook v1.2.0)`. This keeps one auditable
baseline for the templates and adapter conventions adopted by a project.
