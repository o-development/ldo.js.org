# `createLdoDatasetFactory`

`createLdoDatasetFactory` is a helper function that creates an LdoDatasetFactory.

This function exists for parity with RDF/JS. Most developers will not use it. Instead, it's better to use [`createLdoDataset`](createLdoDataset.md).

## Usage

```typescript
import { createLdoDatasetFactory } from "@ldo/ldo";

const ldoDatasetFactory = createLdoDatasetFactory();
const ldoDataset = ldoDatasetFactory.dataset(initialDataset);
```


## Definition
```typescript
createLdoDatasetFactory(): Promise<LdoDatasetFactory>
```
