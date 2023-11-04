# `toTurtle`

Converts a Linked Data Object to a Turtle string

## Usage

```typescript
import { toTurtle } from "@ldo/ldo"
// ...
const rawTurtle: string = await toTurtle(profile);
```

## Definition

```typescript
toTurtle(ldo: LdoBase): Promise<string> 
```

### Parameters
 - `ldo`: Any linked data object
