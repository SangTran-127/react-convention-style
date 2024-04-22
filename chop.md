# Line/statement Chopping

[📑 Table of Contents](../README.md)

> NOTE: The examples on this page are shortened and in fact may quite well be expressed on single lines (without any chopping)

## Files: .ts .tsx .js .jsx

### `chop-chopping`

- Line/statement chopping is MAY be utilized to break long lines/statement onto multiple lines

### `chop-all-or-nothing`

- When chopping elements of a statement, chop all of them or none of them

```typescript
// ❌ Not allowed
const result = myFunction(
  'something', 234,
  false,
);

// ✅ Allowed
const result = myFunction('something', 234, false);
// or
const result = myFunction(
  'something',
  234,
  false,
);
```

- Exception: JSX logical operator chopping
  - May chop the JSX element onto a new line while not chopping the rest of the expression

```tsx
// ✅ Allowed
<div>
  {condition1 && condition2
    && <div>foo<div>
  }
</div>
```

## Specific Situations

### `chop-import`

- The elements in an import statement MAY be chopped onto multiple lines if required for clarity, see example below
  - **NOTE:** Due to conflicting behaviors in VS Code the dangling comma in multi-line import statements is optional
- As with non-chopped import statements, chopped imports MUST be sorted alphabetically

```typescript
// ❌ Not allowed
import {
  FormControl,
  FormGroup, InputLabel, MenuItem,
  Select
} from '@material-ui/core';

// ✅ Allowed
import { FormControl, FormGroup, InputLabel, MenuItem, Select } from '@material-ui/core';
// or
import {
  FormControl,
  FormGroup,
  InputLabel,
  MenuItem,
  Select
} from '@material-ui/core';
```

### `chop-interface`

- Each declaration in an interface MUST appear on it's own line
- Declarations in an interface SHOULD be sorted alphabetically

### `chop-type`

- Chopping MAY be used in type declarations

### `chop-function-declaration-arguments`

- Arguments MAY be chopped onto multiple lines if required for clarity

```typescript
// ✅ Allowed
const myFunction = (
  anArgument: string,
  anotherArgument: number,
  yetAnother: boolean,
): void => {
  // do stuff here
};
```

### `chop-function-call-arguments`

- Arguments MAY be chopped onto multiple lines if required for clarity

```typescript
// ✅ Allowed
const result = myFunction(
  'something',
  234,
  false,
);
```

### `chop-object-declaration`

- Properties MAY be chopped onto multiple lines if required for clarity, see example below
- Properties SHOULD be sorted alphabetically, unless good reason to the contrary

```typescript
// ✅ Allowed
const newObject = {
  hello: 'world',
  someNumber: 42,
};
```

### `chop-jsx-properties`

- JSX properties MAY be chopped onto multiple lines if required for clarity, see example below

```tsx
// ✅ Allowed
const myChip = (
  <Chip
    id="mine"
    label={formatValue()}
    onDelete={handleDelete}
    sx={{ margin: '0 0.5rem 0.7rem 0' }}
    variant='outlined'
  />
);
```

### `chop-ternary-operators`

- Ternary operators MAY be chopped onto multiple lines if required for clarity, see example below
- The operators `?` and `:` must appear at the start of lines when chopped

```tsx
// ❌ Not allowed
const out = width < maxWidth ? 'this is ok'
  : 'too wide';

const out = width < maxWidth ?
  'this is ok' :
  'too wide';

// ✅ Allowed
const out = width < maxWidth
  ? 'this is ok'
  : 'too wide';

const ternary = (
  <div>
    {width < maxWidth
      ? <span>foo</span>
      : <span>bar</span>
    }
  </div>
);
```

### `chop-logical-operators`

- Logical statements MAY be chopped onto multiple lines if required for clarity, see example below
- The operators (e.g. `&&` and `||`) must appear at the start of lines when chopped

```tsx
// ❌ Not allowed
const logical = (
  <div>
    {width < maxWidth &&
      <span>this is conditional</span>
    }
  </div>
);

// ✅ Allowed
const logical = (
  <div>
    {width < maxWidth
      && <span>this is conditional</span>
    }
  </div>
);

if (
  something < somethingElse
  && anotherCondition
) {
  // ...
}
```

### `chop-mathematical-operators`

- Chopping with mathematical operators SHOULD be avoided
- Consider breaking into multiple statements for clarity
