# General

[📑 Table of Contents](../README.md)

### `general-block-single-line-control-flow`

- AVOID block statement in case of a single line control flow statement
- **Exceptions** allowed when
  - `if` conditions are particularly long or multi-line
    - also consider extracting conditions as variable(s) to increase clarity.
  - `return` statement is particularly long or multi-line

```typescript
// ❌ Not recommended
function someMethod(n: number): void {
  if (n !== 3) {
    return;
  }

  this.doThis();
}

// ✅ Preferred
const someMethod = (n: number): void => {
  if (n !== 3) return;

  this.doThis();
}
```

### `general-avoid-nesting`

- AVOID nesting where reasonable
  - Replace nested conditionals with Guard Clause

```typescript
// ❌ Not recommended
function someMethod(n: number): void {
  if (n === 3) {
    this.doThis();
    this.doThat();
    other.doOther(n);
  }
}

// ✅ Preferred
const someMethod = (n: number): void => {
  if (n !== 3) return;

  this.doThis();
  this.doThat();
  other.doOther(n);
}
```

### `general-constant-naming`

- ONLY **module level** `const`s or **static readonly class members** may be in `SHOUTING_SNAKE` case

```typescript
// ✅ Allowed
import fs from 'fs';

const MODULE_LEVEL: string = 'module level';

class A {
  public static readonly CLASS_LEVEL: string = 'class level';

  private func(): void {
    const myConst: string = 'myConst';
  }
}

const myFunc = (): void => {}
```
