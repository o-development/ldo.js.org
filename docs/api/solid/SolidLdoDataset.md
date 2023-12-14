# `LdoDataset`

A SolidLdoDataset is an RDF/JS Dataset designed to represent a slice of the Solidverse. It holds information about resources and the RDF or Binary data on that resource.

It is not recommended to instantiate a SolidLdoDataset. Instead use the [`createSolidLdoDataset`](createSolidLdoDataset.md) function.

## Usage

```typescript
import { createSolidLdoDataset } from "@ldo/solid";
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes";

const solidLdoDataset = createSolidLdoDataset();
const someResource = solidLdoDataset
  .getResource("https://example.com/something.ttl");
```

## Definition

```typescript
class SolidLdoDataset extends LdoDataset
```

---

### `constructor`

```typescript
constructor(
  context: SolidLdoDatasetContext,
  datasetFactory: DatasetFactory,
  initialDataset?: Dataset,
)
```

#### Parameters
 - `context`: A SolidLdoDatasetContext, an object with three parameters:
   - `solidLdoDataset`: A circular reference to itself
   - `resourceStore`: A LDO Resource store
   - `fetch`: An http fetch function that should be used to query Pods. Typically this is the fetch function provided by @inrupt/solid-client-authn-js
 - `datasetFractory`: A RDF/JS Dataset Factory
 - `initialDataset` (Optional): An RDF/JS Dataset with initial Quads

---

### LdoDataset Methods

SolidLdoDataset implements all methods defined in the [LdoDataset class](../ldo/LdoDataset.md).

---

### Dataset Methods

SolidLdoDataset implements all methods defined in the [Dataset class](../dataset/Dataset.md).

---

### Subscribable Dataset Methods

SolidLdoDataset implements all methods defined in the [SubscribableDataset class](../subscribable-dataset/SubscribableDataset.md).

---

### `getResource`

```typescript
getResource(uri: ContainerUri, options?: ResourceGetterOptions): Container;
getResource(uri: LeafUri, options?: ResourceGetterOptions): Leaf;
getResource(uri: string, options?: ResourceGetterOptions): Leaf | Container;
getResource(uri: string, options?: ResourceGetterOptions): Leaf | Container
```

Given a URI returns a resource representation associated with that URI.

This method does NOT fetch the resource it only returns a resource representation with methods that will allow you to control when it is fetched.

#### Parameters
 - `uri`: A LeafUri or ContainerUri of the desired resoruce
 - `options` (optional): An object with one property:
   - `autoLoad` (optional): A boolean. If true, once this method is called the resource will be fetched automatically. Defaults to false.

---

###  `commitChangesToPod`

```typescript
async commitChangesToPod(
  changes: DatasetChanges<Quad>,
): Promise<
  | AggregateSuccess<ResourceResult<UpdateSuccess, Leaf>>
  | AggregateError<UpdateResultError | InvalidUriError>
>
```

Given DatasetChanges it will commit all changes to any number of Solid Pods

#### Parameters
 - `changes`: DatasetChanges that should be committed

#### Returns
[AggregateSuccess](results/AggregateSuccess.md) or [AggregateError]()
