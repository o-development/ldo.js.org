# `LdoDataset`

An LdoDataset is a utility for building a linked data object.

It is not recommended to instantiate an LdoDataset. Instead use the [`createLdoDataset`](createLdoDataset.md) function.

## Usage

```typescript
import { LdoDataset, createLdoDatasetFactory } from "@ldo/ldo";
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes";

const ldoDatasetFactory = createLdoDatasetFactory();
const ldoDataset = new LdoDataset();
const ldoBuilder = ldoDataset.usingType(FoafProfileShapeType);
```

## Definition

```typescript
class LdoDataset implements SubscribableDataset<Quad>, Dataset<Quad, Quad>
```

---

### `constructor`

```typescript
constructor(
  datasetFactory: DatasetFactory<InAndOutQuad, InAndOutQuad>,
  initialDataset?: Dataset<InAndOutQuad, InAndOutQuad>,
)
```

#### Parameters
 - `datasetFractory`: A RDF/JS Dataset Factory
 - `initialDataset` (Optional): An RDF/JS Dataset with initial Quads

---

### Dataset Methods

LdoDataset implements all methods defined in the [Dataset class](../dataset/Dataset.md).

---

### Subscribable Dataset Methods

LdoDataset implements all methods defined in the [SubscribableDataset class](../subscribable-dataset/SubscribableDataset.md).

---

### `usingType`

```
usingType<Type extends LdoBase>(shapeType: ShapeType<Type>): LdoBuilder<Type>
```

Creates an LdoBuilder for a given shapeType

#### Parameters
 - `shapeType`: A ShapeType
