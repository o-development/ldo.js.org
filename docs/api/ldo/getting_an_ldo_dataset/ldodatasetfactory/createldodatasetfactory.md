# `createLdoDatasetFactory`

## Definition
```typescript
createLdoDatasetFactory(): Promise<LdoDatasetFactory>
```

## Usage

```typescript
import { createLdoDatasetFactory } from "ldo";

const ldoDatasetFactory = createLdoDatasetFactory();
const ldoDataset = ldoDatasetFactory.dataset(initialDataset);
```
