```markdown
# OpenCut Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the OpenCut Rust codebase. You'll learn how to structure files, write imports and exports, follow commit message standards, and organize and run tests. These practices ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myModule.rs`, `dataParser.rs`

### Import Style
- Use **relative imports** within the codebase.
  - Example:
    ```rust
    mod utils;
    use crate::utils::parseData;
    ```

### Export Style
- Use **named exports** for modules and functions.
  - Example:
    ```rust
    pub fn processData() { /* ... */ }
    ```

### Commit Messages
- Follow **conventional commit** format.
- Use the `feat` prefix for new features.
  - Example:  
    ```
    feat: add support for custom file formats
    ```
- Keep commit messages concise (average ~47 characters).

## Workflows

### Add a New Feature
**Trigger:** When implementing a new feature or module  
**Command:** `/add-feature`

1. Create a new file using camelCase (e.g., `newFeature.rs`).
2. Implement the feature using relative imports for dependencies.
3. Export public functions or structs using named exports.
4. Write corresponding tests in a file named `newFeature.test.rs`.
5. Commit your changes using the `feat` prefix:
    ```
    feat: brief description of the new feature
    ```

### Update or Refactor Code
**Trigger:** When improving or restructuring existing code  
**Command:** `/refactor-code`

1. Identify the module or function to update.
2. Apply changes, maintaining camelCase file naming and relative imports.
3. Update or add tests as needed in `*.test.rs` files.
4. Commit changes using the `feat` prefix (if adding features) or another appropriate prefix.

### Run Tests
**Trigger:** Before pushing changes or verifying code correctness  
**Command:** `/run-tests`

1. Locate test files matching the `*.test.*` pattern.
2. Run tests using your preferred Rust test runner (e.g., `cargo test`).
3. Review test results and fix any failures.

## Testing Patterns

- Test files are named using the `*.test.*` pattern (e.g., `parser.test.rs`).
- Each test file should cover the corresponding module's public API.
- Example test file structure:
    ```rust
    #[cfg(test)]
    mod tests {
        use super::*;

        #[test]
        fn test_process_data() {
            // Arrange
            let input = /* ... */;
            // Act
            let result = processData(input);
            // Assert
            assert_eq!(result, expected);
        }
    }
    ```

## Commands
| Command        | Purpose                                      |
|----------------|----------------------------------------------|
| /add-feature   | Scaffold and commit a new feature/module     |
| /refactor-code | Refactor or update existing code             |
| /run-tests     | Run all tests in files matching *.test.*     |
```
