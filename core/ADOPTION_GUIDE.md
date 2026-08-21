# Adopting The Core Process

## Purpose

This guide turns the playbook into local, reviewed documentation. It is not a
license to copy claims from another project.

## Prerequisites

Before adoption, identify a stable target baseline:

- the latest release tag, or
- a reviewed `main` commit with green CI.

The adopter must be able to inspect the target repository, its build commands,
CI configuration, test suites and deployment/release path.

## Bootstrap Workflow

1. Create a branch such as `docs/adopt-engineering-playbook` from the chosen
   baseline.
2. Copy the core templates into the target project and select one adapter.
3. Replace all bracketed placeholders with facts established from the target
   code and CI. Delete sections that do not apply; never leave generic claims
   pretending to describe the project.
4. Create initial Knowledge Base maps for the architectural boundaries that
   future changes need to understand.
5. Create project-specific Skills only for recurring procedures. Do not turn a
   single feature's design into a reusable Skill. A starter Skill supplied by
   an adapter may be copied when its documented cross-project procedure applies;
   record it as inherited from the selected playbook version.
6. Record the adoption in `PROCESS_BASELINE.md`.
7. Open a documentation-only bootstrap Pull Request and obtain independent
   review before relying on the new process.

## Required Bootstrap Review Questions

- Does every claimed command actually run in this repository?
- Are the documents based on the selected baseline commit?
- Does the documentation route point to real local files?
- Are the stated test layers and CI gates real?
- Are architecture and technical-debt statements code-backed rather than
  copied from the playbook?
- Does the adapter match the project's runtime and package manager?
- Have all bracketed placeholders such as `[path]`, `[facts]` and `[commit]`
  been replaced or deliberately removed from adopted documents?

## After Adoption

For every Pull Request, apply the Documentation Impact Gate in
`CONTRIBUTING.md`. At each phase, feature milestone or release, perform the
closeout described there. Small changes may legitimately leave documentation
unchanged, but the author must evaluate and state that conclusion.
