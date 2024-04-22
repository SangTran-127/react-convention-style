# React/JSX

[📑 Table of Contents](../README.md)

### `jsx-space-inside-close`

- Space before `>` on single-line element MUST be omitted

```tsx
// ❌ Not allowed
const a = <div >foo</div>;
const b = <div id="foo" >foo</div>;

// ✅ Allowed
const a = <div>foo</div>;
const b = <div id="foo">foo</div>;
```

### `jsx-empty-element`

- Empty elements SHOULD be represented like `<div />`

### `jsx-wrap-single-element`

- Sometimes single elements MAY be wrapped to aid in chopping and clarity
- Multi-line single JSX root elements SHOULD always be wrapped
- When wrapped, single elements MUST be wrapped in parentheses `(...)`

```tsx
// ❌ Not allowed
const a = (<div>foo</div>);
// or
const a = <>
  <div>foo</div>
</>;

// ❌ Avoid
const b = <div>
  <span>foo</foo>
</div>;

// ✅ Allowed
const a = <div>foo</div>;
// or
const a = (
  <div>foo</div>
);

const b = (
  <div>
    <span>foo</foo>
  </div>
);
```

### `jsx-root-level-conditionals`

- In JSX, root-level ternaries SHOULD be avoided

```tsx
// ❌ Avoid
return <>
  {loading
    ? <Spinner />
    : <Main
      prop={value}
    />
  }
<>;

// ✅ Prefer
if (loading) return <Spinner />;

return (
  <Main
    prop={value}
  />
);
```
