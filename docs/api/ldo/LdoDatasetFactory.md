# `LdoDatasetFactory`

`LdoDatasetFactory` is a helper class that includes methods for creating LdoDatasets.

This class exists for parity with RDF/JS. Most developers will not use it. Instead, it's better to use [`createLdoDataset`](createLdoDataset.md).

## Usage

```typescript
import { createLdoDatasetFactory } from "ldo";

const datasetFactory = // some RDF/JS Dataset Factory
const ldoDatasetFactory = new LdoDatasetFactory(datasetFactory);
const ldoDataset = ldoDatasetFactory.dataset(initialDataset);
```

## Definition
```typescript
class LdoDatasetFactory implements DatasetFactory<Quad, Quad>
```

---

### `constructor`
```typescript
new LdoDatasetFactory(datasetFactory: DatasetFactory<Quad, Quad>)
```

#### Parameters
 - `datasetFactory`: A generic dataset factory this factory will wrap

---

### `dataset`
```typescript
dataset(quads?: Dataset<Quad, Quad> | Quad[]): LdoDataset
```

#### Parameters
 - `quads`: A list of quads to initialize the dataset
