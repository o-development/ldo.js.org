# `toNTriples`

Converts a Linked Data Object to a NTriples string

## Usage

```typescript
import { toNTriples } from "@ldo/ldo"
// ...
const rawNTriples: string = await toNTriples(profile);
```

## Definition

```typescript
toNTriples(ldo: LdoBase): Promise<string>
```

### Parameters
 - `ldo`: Any linked data object
