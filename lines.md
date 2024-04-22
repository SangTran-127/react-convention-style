# Empty Lines & End-of-Line

[📑 Table of Contents](../README.md)

Empty lines in code are used to visually separate/group code to decrease cognitive load when reading.

## All Text-based Files

### `line-end-of-line-trim`

- All lines must be trim of any trailing spaces
  - VS Code can be configured to do this

### `line-end-of-file`

- All files MUST end with a single `<LF>` character
  - VS Code can be configured to do this
  - **Exception:** `.vscode/cspell.json` has no `<LF>` at EoF

## Files: .ts .tsx .js .jsx

### `line-between-imports`

- Empty lines between `import` statement lines are NOT ALLOWED

### `line-after-imports`

- Empty line MUST be present between imports and the rest of the code

### `line-block-begin-end`

- Code blocks, either TS/JS `{...}` or JSX `<>...</>`, MUST NOT begin or end with an empty line

```typescript
// ❌ Now allowed
if (condition) {

  doSomething();

}

// ✅ Allowed
if (condition) {
  doSomething();
}
```
