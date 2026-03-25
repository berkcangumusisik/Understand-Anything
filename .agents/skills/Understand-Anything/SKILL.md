```markdown
# Understand-Anything Development Patterns

> Auto-generated skill from repository analysis

## Overview

The **Understand-Anything** repository is a TypeScript codebase focused on code analysis, language/framework support, and multi-platform plugin integration. It is organized for maintainability and extensibility, with clear workflows for adding language/framework support, updating dashboards, synchronizing installation instructions, evolving prompt pipelines, and managing localization. The repository follows conventional commit patterns and emphasizes modular, testable code.

---

## Coding Conventions

- **Language:** TypeScript (no framework detected)
- **File Naming:** camelCase for files (e.g., `languageRegistry.ts`, `fileAnalyzerPrompt.md`)
- **Import Style:** Relative imports  
  ```ts
  import { analyzeFile } from './fileAnalyzer'
  ```
- **Export Style:** Named exports  
  ```ts
  export function analyzeFile(...) { ... }
  export const LANGUAGE_REGISTRY = { ... }
  ```
- **Commit Messages:** Conventional commits with prefixes: `feat`, `fix`, `docs`, `chore`, `refactor`  
  Example:  
  ```
  feat: add support for Rust language detection
  ```
- **Test Files:** Located alongside source, named `*.test.ts`

---

## Workflows

### Add or Update Language or Framework Support

**Trigger:** When you want to add or improve support for a programming language or framework in the analysis pipeline.  
**Command:** `/add-language-support`

1. **Add or update config:**  
   - Edit or create files in  
     ```
     packages/core/src/languages/configs/*.ts
     packages/core/src/languages/frameworks/*.ts
     ```
2. **Update registries:**  
   - Edit  
     ```
     packages/core/src/languages/language-registry.ts
     packages/core/src/languages/framework-registry.ts
     packages/core/src/languages/index.ts
     ```
3. **Add prompt snippets:**  
   - Edit or add  
     ```
     skills/understand/languages/*.md
     skills/understand/frameworks/*.md
     ```
4. **Update or add tests:**  
   - Add/modify tests in  
     ```
     packages/core/src/__tests__/*.test.ts
     ```
5. **Update documentation:**  
   - Edit  
     ```
     skills/understand/SKILL.md
     ```
     and related prompt files as needed.
6. **(Optional) Update dashboard/docs:**  
   - Reflect new support in UI or documentation.

**Example:**  
```ts
// packages/core/src/languages/configs/rust.ts
export const rustConfig = {
  name: 'Rust',
  extensions: ['.rs'],
  // ...
}
```

---

### Dashboard Feature or Performance Improvement

**Trigger:** When you want to add a dashboard feature or optimize dashboard performance.  
**Command:** `/dashboard-feature`

1. **Edit/add React components:**  
   - Modify or create  
     ```
     packages/dashboard/src/components/*.tsx
     ```
2. **Update utilities for performance:**  
   - Edit  
     ```
     packages/dashboard/src/utils/*.ts
     packages/dashboard/src/utils/*.worker.ts
     ```
3. **Update hooks/state:**  
   - Edit  
     ```
     packages/dashboard/src/hooks/*.ts
     ```
4. **Update styles:**  
   - Edit  
     ```
     packages/dashboard/src/index.css
     ```
5. **(Optional) Update docs:**  
   - If user-facing changes, update `SKILL.md` or documentation.

**Example:**  
```tsx
// packages/dashboard/src/components/GraphView.tsx
export function GraphView(props) {
  // ...
}
```

---

### Multi-Platform Installation Instructions Sync

**Trigger:** When you add a new platform, update install instructions, or bump versions.  
**Command:** `/sync-install-docs`

1. **Edit/add INSTALL.md for each platform:**  
   - Update  
     ```
     .antigravity/INSTALL.md
     .codex/INSTALL.md
     .openclaw/INSTALL.md
     .opencode/INSTALL.md
     .gemini/INSTALL.md
     .pi/INSTALL.md
     ```
2. **Update plugin manifests:**  
   - Edit  
     ```
     .claude-plugin/plugin.json
     .claude-plugin/marketplace.json
     .cursor-plugin/plugin.json
     ```
3. **Update README and translations:**  
   - Edit  
     ```
     README.md
     README.zh-CN.md
     README.ja-JP.md
     README.tr-TR.md
     ```
4. **(Optional) Update developer docs:**  
   - Edit `CLAUDE.md`, `CONTRIBUTING.md` as needed.

---

### Skill Prompt Pipeline Update

**Trigger:** When you need to change the LLM prompt pipeline or fix normalization/validation logic.  
**Command:** `/update-prompt-pipeline`

1. **Edit SKILL.md:**  
   - Update phases, normalization, or prompt logic in  
     ```
     skills/understand/SKILL.md
     ```
2. **Edit related prompt files:**  
   - Update  
     ```
     skills/understand/architecture-analyzer-prompt.md
     skills/understand/file-analyzer-prompt.md
     skills/understand/tour-builder-prompt.md
     skills/understand/project-scanner-prompt.md
     skills/understand/graph-reviewer-prompt.md
     ```
3. **Update addendum files:**  
   - Edit  
     ```
     skills/understand/frameworks/*.md
     skills/understand/languages/*.md
     ```
4. **(Optional) Update schema/tests:**  
   - If validation logic changes, update `schema.ts` and relevant tests.

---

### Add or Update Localization

**Trigger:** When you want to add a new language or update documentation translations.  
**Command:** `/add-localization`

1. **Add/update translated README:**  
   - Add or edit  
     ```
     README.<lang>.md
     ```
2. **Update language selector links:**  
   - Edit  
     ```
     README.md
     ```
     to include new translation links.
3. **(Optional) Update other localized files:**  
   - For new instructions or content.

---

## Testing Patterns

- **Framework:** [vitest](https://vitest.dev/)
- **Test File Pattern:** `*.test.ts` in `packages/core/src/__tests__/`
- **Test Example:**
  ```ts
  // packages/core/src/__tests__/languageRegistry.test.ts
  import { describe, it, expect } from 'vitest'
  import { LANGUAGE_REGISTRY } from '../languages/language-registry'

  describe('LANGUAGE_REGISTRY', () => {
    it('should include TypeScript', () => {
      expect(LANGUAGE_REGISTRY).toHaveProperty('typescript')
    })
  })
  ```

---

## Commands

| Command                 | Purpose                                                         |
|-------------------------|-----------------------------------------------------------------|
| /add-language-support   | Add or update language/framework support in the analysis pipeline|
| /dashboard-feature      | Add or optimize dashboard features or performance               |
| /sync-install-docs      | Sync installation instructions and manifests for all platforms  |
| /update-prompt-pipeline | Update LLM prompt pipeline or normalization logic              |
| /add-localization       | Add or update documentation translations                       |
```
