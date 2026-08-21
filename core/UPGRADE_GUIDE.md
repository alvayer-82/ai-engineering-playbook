# Upgrading An Adopted Project

## Purpose

Use this guide when a project already records an earlier playbook version in
`PROCESS_BASELINE.md`. An upgrade is a reviewed local documentation change; it
does not overwrite the project's architecture, commands or local adaptations.

## Upgrade Workflow

1. Read the target project's `PROCESS_BASELINE.md` and identify its current
   playbook tag, selected adapter and recorded local deviations.
2. Choose the target playbook tag. Read its `CHANGELOG.md` and
   `VERSIONING.md`, including any migration notes for a major release.
3. Compare the two playbook versions. Review only the changed files in `core/`
   and the selected adapter, for example with `git diff --name-status
   <old-tag>..<new-tag>`.
4. Classify each changed template as one of: adopt unchanged, merge with a
   local adaptation, intentionally reject, or not applicable. Do not replace a
   local file wholesale merely because its template changed.
5. For a major version, explicitly review every newly required gate and record
   its local implementation or reason it is inapplicable.
6. Create a documentation-only upgrade branch and apply the approved local
   delta. Keep project behavior, dependencies and deployment untouched unless
   a separate, explicitly approved change is required.
7. Update `PROCESS_BASELINE.md` with the new playbook tag, current local
   adaptations and one `Upgrade History` row linking the upgrade Pull Request.
8. Validate that adopted documents contain no unresolved bracketed placeholders
   and that every changed command, CI claim and architecture statement remains
   true in the target project.
9. Open an upgrade Pull Request. Its description lists old/new tags, examined
   core/adapter files, applied local changes, deliberately rejected changes,
   verification evidence and remaining migration work.

## Upgrade Review Questions

- Does the baseline record match the actual previously adopted version?
- Were local adaptations preserved or consciously changed?
- For a major release, was every new required gate evaluated?
- Do final documents still point only to files and commands that exist?
- Does the upgrade introduce any unsupported technical claim?

## When To Defer

An upgrade may be deferred when it requires a product decision or a separate
implementation change. Record the reason and a follow-up item in the target
project rather than falsely claiming the new version was adopted.
