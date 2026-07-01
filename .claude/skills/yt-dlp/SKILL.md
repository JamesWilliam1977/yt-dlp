```markdown
# yt-dlp Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `yt-dlp` Python codebase. You'll learn the preferred file naming, import/export styles, commit message patterns, and how to write and run tests. This guide is ideal for contributors aiming to maintain consistency and quality in the project.

## Coding Conventions

### File Naming
- Use **snake_case** for all Python files.
  - Example: `download_manager.py`, `extractor_utils.py`

### Import Style
- Use **relative imports** within the package.
  - Example:
    ```python
    from .utils import download_file
    from .extractor import BaseExtractor
    ```

### Export Style
- Use **named exports** (explicitly listing exported classes, functions, or variables).
  - Example:
    ```python
    __all__ = ['Downloader', 'Extractor']
    ```

### Commit Messages
- Commit messages are **freeform** (no strict prefix), with an average length of about 47 characters.
  - Example:
    ```
    Fix bug in YouTube extractor for age-restricted videos
    Add support for new video format
    ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new capability or extractor  
**Command:** `/add-feature`

1. Create a new Python file using snake_case if needed.
2. Use relative imports to include shared utilities.
3. Implement the feature with clear, modular code.
4. Add named exports as needed.
5. Write or update tests in a corresponding `*.test.*` file.
6. Commit with a descriptive message.

### Fixing a Bug
**Trigger:** When resolving a reported or discovered issue  
**Command:** `/fix-bug`

1. Locate the relevant module or function.
2. Apply the fix, following code style conventions.
3. Add or update tests to cover the bug scenario.
4. Commit with a message describing the fix.

### Writing and Running Tests
**Trigger:** When adding new code or refactoring existing code  
**Command:** `/run-tests`

1. Create or update test files matching the `*.test.*` pattern.
2. Write tests for new or changed functionality.
3. Run tests using the project's preferred method (framework unknown; check project docs or use standard Python test runners).
4. Ensure all tests pass before committing.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `extractor.test.py`).
- The specific test framework is **unknown**; check for usage of `unittest`, `pytest`, or custom runners.
- Place tests close to the code they exercise or in a dedicated `tests` directory.
- Example test file name: `downloader.test.py`

## Commands
| Command       | Purpose                                     |
|---------------|---------------------------------------------|
| /add-feature  | Steps for adding a new feature or extractor |
| /fix-bug      | Steps for fixing a bug                      |
| /run-tests    | Steps for writing and running tests         |
```