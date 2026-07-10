```markdown
# CopilotKit Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the CopilotKit TypeScript codebase. You'll learn about file organization, code style, commit message conventions, and how to write and structure tests. This guide is ideal for contributors looking to maintain consistency and quality in their contributions.

## Coding Conventions

### File Naming
- Use **camelCase** for all file names.
  - Example: `myComponent.ts`, `userService.ts`

### Import Style
- Use **relative imports** for referencing modules within the project.
  - Example:
    ```typescript
    import { fetchData } from './apiClient';
    ```

### Export Style
- Use **named exports** rather than default exports.
  - Example:
    ```typescript
    // Good
    export function doSomething() { ... }
    export const CONSTANT = 42;

    // Bad
    export default function doSomething() { ... }
    ```

### Commit Messages
- Follow **conventional commit** format.
- Use prefixes such as `chore`.
- Keep commit messages concise (average ~68 characters).
  - Example:
    ```
    chore: update dependencies to latest versions
    ```

## Workflows

### Making a Code Change
**Trigger:** When you need to add a feature, fix a bug, or refactor code.
**Command:** `/make-change`

1. Create a new branch for your change.
2. Make your code changes following the coding conventions.
3. Write or update tests as needed.
4. Commit your changes using the conventional commit format.
5. Push your branch and open a pull request.

### Writing a Test
**Trigger:** When adding new functionality or fixing bugs.
**Command:** `/write-test`

1. Create a test file named with the pattern `*.test.*` (e.g., `userService.test.ts`).
2. Write tests for your code (testing framework is unspecified; use typical TypeScript testing patterns).
3. Ensure tests cover edge cases and expected behavior.
4. Run tests to verify correctness.

### Code Review Preparation
**Trigger:** Before submitting your pull request.
**Command:** `/prepare-review`

1. Ensure all code follows file naming, import, and export conventions.
2. Double-check commit messages for conventional format.
3. Confirm all tests pass.
4. Review your changes for clarity and maintainability.

## Testing Patterns

- Test files use the pattern `*.test.*` (e.g., `utils.test.ts`).
- The specific testing framework is not detected, but standard TypeScript testing practices apply.
- Place tests alongside or near the code they test.
- Example test file:
  ```typescript
  // mathUtils.test.ts
  import { add } from './mathUtils';

  describe('add', () => {
    it('adds two numbers', () => {
      expect(add(2, 3)).toBe(5);
    });
  });
  ```

## Commands
| Command         | Purpose                                         |
|-----------------|-------------------------------------------------|
| /make-change    | Start a new code change workflow                |
| /write-test     | Begin writing tests for new or changed code     |
| /prepare-review | Prepare your branch for code review and PR      |
```
