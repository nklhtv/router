---
id: catchNotFoundComponent
title: CatchNotFound Component
---

The `CatchNotFound` component is a component that catches not-found errors thrown by its children, renders an fallback component and optionally calls the `onCatch` callback. It resets when the pathname changes.

### Props

#### `props.children`

- Type: `JSX.Element`
- Required
- The component's children to render when there is no error

#### `props.fallback`

- Type: `(error: NotFoundError) => React.ReactElement`
- Optional
- The component to render when there is an error

#### `props.onCatch`

- Type: `(error: any) => void`
- Optional
- A callback that will be called with the error that was thrown by the component's children

### Returns

- Returns the component's children if there is no error
- Returns the `fallback` if there is an error

### Examples

```tsx
import { CatchNotFound } from '@tanstack/react-router'

function Component() {
  return (
    <CatchNotFound
      fallback={(error) => <p>Not found error! {JSON.stringify(error)}</p>}
    >
      <ComponentThatMightThrowANotFoundError />
    </CatchNotFound>
  )
}
```
