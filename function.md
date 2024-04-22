# Functions

[📑 Table of Contents](../README.md)

### `functions-prefer-arrow`

- PREFER arrow functions
  - UNLESS `public` or `protected` class methods

```tsx
// ❌ Not allowed
function myFunction(): void {
  // do stuff
}

// ✅ Preferred
const myFunction = (): void => {
  // do stuff
}
```
