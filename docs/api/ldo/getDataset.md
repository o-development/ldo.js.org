# `getDataset`

Returns the Linked Data Object's underlying RDFJS dataset. Modifying this dataset will change the Linked Data Object as well.

## Usage

```typescript
import { getDataset } from "@ldo/ldo"
const dataset = getDataset(profile);
```

## Definition

```typescript
getDataset(ldo: LdoBase): Dataset
```

### Parameters
 - `ldo`: Any linked data object
