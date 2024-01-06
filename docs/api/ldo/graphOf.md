# `graphOf`

The graph of specific information can be detected using the `graphOf(subject, predicate, object)` function.

## Usage

```typescript
import { graphOf } from "@ldo/ldo";

graphOf(person, "name", 0); // returns defaultGraph()
graphOf(person, "age"); // returns defaultGraph()
```

## Definition

```typescript
import { graphOf } from "@ldo/ldo"

graphOf(
  subject: LdoBase,
  predicate: string | Symbol,
  object?: number | LdoBase
): GraphNode[]
```

### Parameters
 - `subject`: A Linked Data Object that represents the subject of a quad.
 - `predicate`: A field on the given Linked Data Object
 - `object` (Optional): An optional parameter that represents the direct object of a statement. This could be a Linked Data Object or a number to indicate the location in an array. This argument can be left blank if the given field is not an array.

### Return

A GraphNode (defaultGraph or namedNode).
