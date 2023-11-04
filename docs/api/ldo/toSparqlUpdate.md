# `toNTriples`

Converts a "transactable" Linked Data Object (A Linked Data Object that has been passed as a parameter to the `startTransaction` function) to a SPARQL/Update string.

## Usage

```typescript
import { toSparqlUpdate, startTransaction } from "@ldo/ldo"
// ...
startTransaction(profile);
const sparqlUpdate: string = await toSparqlUpdate(profile);
```

## Definition

```typescript
toSparqlUpdate(ldo: LdoBase): Promise<string>
```

### Parameters
 - `ldo`: Any linked data object that is currently "transactable"
