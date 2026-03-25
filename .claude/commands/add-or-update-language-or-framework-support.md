---
name: add-or-update-language-or-framework-support
description: Workflow command scaffold for add-or-update-language-or-framework-support in Understand-Anything.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-language-or-framework-support

Use this workflow when working on **add-or-update-language-or-framework-support** in `Understand-Anything`.

## Goal

Adds or updates support for a programming language or framework in the analysis pipeline, including config, registry, prompt snippets, and tests.

## Common Files

- `understand-anything-plugin/packages/core/src/languages/configs/*.ts`
- `understand-anything-plugin/packages/core/src/languages/frameworks/*.ts`
- `understand-anything-plugin/packages/core/src/languages/language-registry.ts`
- `understand-anything-plugin/packages/core/src/languages/framework-registry.ts`
- `understand-anything-plugin/packages/core/src/languages/index.ts`
- `understand-anything-plugin/packages/core/src/__tests__/*.test.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update language/framework config in packages/core/src/languages/configs/*.ts and/or frameworks/*.ts
- Update language and framework registry files (language-registry.ts, framework-registry.ts, index.ts)
- Add or update prompt snippets in skills/understand/languages/*.md and/or frameworks/*.md
- Update or add tests in packages/core/src/__tests__/
- Update SKILL.md and related prompt files to inject new snippets or handle new frameworks

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.