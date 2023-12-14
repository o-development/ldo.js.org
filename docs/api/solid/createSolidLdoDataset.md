# `createSolidLdoDataset`

A function that initializes a SolidLdoDataset.

## Definition
```typescript
createSolidLdoDataset(options?: CreateSolidLdoDatasetOptions): SolidLdoDataset
```

### Parameters
 - `options` (optional): An object with three parameters:
   - `fetch` (optional): An http fetch function that should be used to query Pods. Typically this is the fetch function provided by @inrupt/solid-client-authn-js
   - `dataset` (optional): An initial dataset
   - `datasetFactory` (optional): A DatasetFactory that will generate new datasets

## Usage

```typescript
import { createLdoDataset } from "@ldo/ldo";

const ldoDataset = createLdoDataset();
```
