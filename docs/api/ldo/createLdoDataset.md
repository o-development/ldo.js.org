# `createLdoDataset`

A function that initializes an LdoDataset.

## Definition
```typescript
createLdoDataset(initialDataset?: Dataset<Quad, Quad> | Quad[]): LdoDataset
```

### Parameters
 - `initialDataset`: An optional dataset or array of quads for the new dataset

## Usage

```typescript
import { createLdoDataset } from "@ldo/ldo";

const ldoDataset = createLdoDataset();
```
