# `createLdoDataset`

## Definition
```typescript
createLdoDataset(initialDataset?: Dataset<Quad, Quad> | Quad[]): Promise<LdoDataset>
```

### Parameters
 - `initialDataset`: An optional dataset or array of quads for the new dataset

## Usage

```typescript
import { createLdoDataset } from "@ldo/ldo";

const ldoDataset = createLdoDataset();
```
