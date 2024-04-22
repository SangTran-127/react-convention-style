# Quotes & Strings

[📑 Table of Contents](../README.md)

## Files: .ts .tsx .js .jsx

### `quote-single-ts`

- String literals in TS/JS code MUST use single quote
  - UNLESS the content on the string includes a single quote, in which case double quotes may be used in place of escaping

```typescript
// ❌ Not allowed
const a = 'hello';

// ✅ Allowed
const a = 'hello';
const c = "it's ok";
```

### `quote-double-ts`

- String literals as direct JSX property values MUST be use double quotes
  - this does not include string literals inside `{}` as they are considered TS/JS

```tsx
// ✅ Allowed
const jsx = <Stuff foo="bar" ts={{ foo: 'bar' }} />;
```

### `quote-concatenation`

- Avoid concatenating string with the addition operator (+), prefer Template Literal Strings

```typescript
// ❌ Not allowed
const a = 'hello';
const b = a + ' world';

// ✅ Allowed
const a = 'hello';
const b = `${a} world`;
```
