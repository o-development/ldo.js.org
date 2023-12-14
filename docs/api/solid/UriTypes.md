# URI Types

@ldo/solid has two kinds of `string` URI types that indicate if a URI is for a Leaf resource or a Container resource.

## LeafUri

A leaf URI is any URI that doesn't have a path that ends in a `/`.

### Usage

```typescript
import { LeafUri } from "@ldo/solid";

const a: LeafUri = "https://example.com/a"; // okay
const b: LeafUri = "https://example.com/b#hash"; // okay
const c: LeafUri = "https://example.com/c?query=true"; // okay
const d: LeafUri = "https://example.com/d?somecontainer=example.com/"; // okay
const e: LeafUri = "https://example.com/e/"; // not okay
```

## ContainerUri

A container URI is any URI that does have a path that ends in a `/`.

### Usage

```typescript
import { ContainerUri } from "@ldo/solid";

const a: ContainerUri = "https://example.com/a/"; // okay
const b: ContainerUri = "https://example.com/b/#hash"; // okay
const c: ContainerUri = "https://example.com/c/?query=true"; // okay
const d: ContainerUri = "https://example.com/d/?somecontainer=example.com/"; // okay
const e: ContainerUri = "https://example.com/e"; // not okay
```
