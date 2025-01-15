# Class: SolidLdoDataset

A SolidLdoDataset has all the functionality of an LdoDataset with the added
functionality of keeping track of fetched Solid Resources.

It is recommended to use the [createSolidLdoDataset](../functions/createSolidLdoDataset.md) to initialize
this class

**`Example`**

```typescript
import { createSolidLdoDataset } from "@ldo/solid";
import { ProfileShapeType } from "./.ldo/profile.shapeTypes.ts"

// ...

const solidLdoDataset = createSolidLdoDataset();

const profileDocument = solidLdoDataset
  .getResource("https://example.com/profile");
await profileDocument.read();

const profile = solidLdoDataset
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
```

## Hierarchy

- `LdoDataset`

  ↳ **`SolidLdoDataset`**

## Implements

- [`ISolidLdoDataset`](../interfaces/ISolidLdoDataset.md)

## Constructors

### constructor

• **new SolidLdoDataset**(`context`, `datasetFactory`, `transactionDatasetFactory`, `initialDataset?`): [`SolidLdoDataset`](SolidLdoDataset.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md) | SolidLdoDatasetContext |
| `datasetFactory` | `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\> | An optional dataset factory |
| `transactionDatasetFactory` | `ITransactionDatasetFactory`\<`Quad`\> | A factory for creating transaction datasets |
| `initialDataset?` | `Dataset`\<`Quad`, `Quad`\> | A set of triples to initialize this dataset |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Overrides

LdoDataset.constructor

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:57](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L57)

## Properties

### context

• **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:49](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L49)

___

### dataset

• `Protected` **dataset**: `DatasetCore`\<`Quad`, `Quad`\>

The main backing dataset

#### Inherited from

LdoDataset.dataset

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:22](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L22)

___

### datasetCoreFactory

• `Protected` **datasetCoreFactory**: `DatasetCoreFactory`\<`Quad`, `Quad`, `DatasetCore`\<`Quad`, `Quad`\>\>

A factory that generates datasets for the methods

#### Inherited from

LdoDataset.datasetCoreFactory

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:27](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L27)

___

### datasetFactory

• `Protected` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

DatasetFactory for creating new datasets

#### Inherited from

LdoDataset.datasetFactory

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:31](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L31)

___

### eventEmitter

• `Protected` **eventEmitter**: `EventEmitter`

The underlying event emitter

#### Inherited from

LdoDataset.eventEmitter

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:36](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L36)

___

### transactionDatasetFactory

• `Protected` **transactionDatasetFactory**: `ITransactionDatasetFactory`\<`Quad`\>

The underlying dataset factory for creating transaction datasets

#### Inherited from

LdoDataset.transactionDatasetFactory

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:40](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L40)

## Accessors

### size

• `get` **size**(): `number`

A non-negative integer that specifies the number of quads in the set.

#### Returns

`number`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[size](../interfaces/ISolidLdoDataset.md#size)

#### Inherited from

LdoDataset.size

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:355](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L355)

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `Quad`, `undefined`\>

Returns an iterator

#### Returns

`Iterator`\<`Quad`, `Quad`, `undefined`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[[iterator]](../interfaces/ISolidLdoDataset.md#[iterator])

#### Inherited from

LdoDataset.[iterator]

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:391](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L391)

___

### add

▸ **add**(`quad`): `this`

Adds the specified quad to the dataset.
Existing quads, as defined in Quad.equals, will be ignored.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

the dataset instance it was called on.

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[add](../interfaces/ISolidLdoDataset.md#add)

#### Inherited from

LdoDataset.add

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:141](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L141)

___

### addAll

▸ **addAll**(`quads`): `this`

Imports the quads into this dataset.
This method differs from Dataset.union in that it adds all quads to the current instance, rather than combining quads and the current instance to create a new instance.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Quad`[] \| `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`this`

the dataset instance it was called on.

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[addAll](../interfaces/ISolidLdoDataset.md#addall)

#### Inherited from

LdoDataset.addAll

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:86](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L86)

___

### addListener

▸ **addListener**(`eventName`, `listener`): `this`

Alias for emitter.on(eventName, listener).

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[addListener](../interfaces/ISolidLdoDataset.md#addlistener)

#### Inherited from

LdoDataset.addListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:248](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L248)

___

### bulk

▸ **bulk**(`changed`): `this`

Bulk add and remove triples

#### Parameters

| Name | Type |
| :------ | :------ |
| `changed` | `DatasetChanges`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[bulk](../interfaces/ISolidLdoDataset.md#bulk)

#### Inherited from

LdoDataset.bulk

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:100](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L100)

___

### contains

▸ **contains**(`other`): `boolean`

Returns true if the current instance is a superset of the given dataset; differently put: if the given dataset is a subset of, is contained in the current dataset.
Blank Nodes will be normalized.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[contains](../interfaces/ISolidLdoDataset.md#contains)

#### Inherited from

LdoDataset.contains

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:68](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L68)

___

### createData

▸ **createData**\<`Type`\>(`shapeType`, `subject`, `resource`, `...additionalResources`): `Type`

Shorthand for solidLdoDataset
  .usingType(shapeType)
  .write(...resources.map((r) => r.uri))
  .fromSubject(subject);

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `shapeType` | `ShapeType`\<`Type`\> | The shapetype to represent the data |
| `subject` | `string` \| `SubjectNode` | A subject URI |
| `resource` | [`Resource`](Resource.md) | - |
| `...additionalResources` | [`Resource`](Resource.md)[] | - |

#### Returns

`Type`

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:109](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L109)

___

### delete

▸ **delete**(`quad`): `this`

Removes the specified quad from the dataset.
This method returns the dataset instance it was called on.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[delete](../interfaces/ISolidLdoDataset.md#delete)

#### Inherited from

LdoDataset.delete

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:154](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L154)

___

### deleteMatches

▸ **deleteMatches**(`subject?`, `predicate?`, `object?`, `graph?`): `this`

This method removes the quads in the current instance that match the given arguments. The logic described in Quad Matching is applied for each quad in this dataset to select the quads which will be deleted.

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject?` | `Term` |
| `predicate?` | `Term` |
| `object?` | `Term` |
| `graph?` | `Term` |

#### Returns

`this`

the dataset instance it was called on.

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[deleteMatches](../interfaces/ISolidLdoDataset.md#deletematches)

#### Inherited from

LdoDataset.deleteMatches

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:121](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L121)

___

### difference

▸ **difference**(`other`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset that contains alls quads from the current dataset, not included in the given dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `DatasetCore`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[difference](../interfaces/ISolidLdoDataset.md#difference)

#### Inherited from

LdoDataset.difference

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:105](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L105)

___

### emit

▸ **emit**(`eventName`, `changes`): `boolean`

Synchronously calls each of the listeners registered for the event named eventName, in the order they were registered, passing the supplied arguments to each.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `changes` | `DatasetChanges`\<`Quad`\> |

#### Returns

`boolean`

true if the event had listeners, false otherwise.

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[emit](../interfaces/ISolidLdoDataset.md#emit)

#### Inherited from

LdoDataset.emit

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:262](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L262)

___

### equals

▸ **equals**(`other`): `boolean`

Returns true if the current instance contains the same graph structure as the given dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[equals](../interfaces/ISolidLdoDataset.md#equals)

#### Inherited from

LdoDataset.equals

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:121](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L121)

___

### eventNames

▸ **eventNames**(): `QuadMatch`[]

Returns an array listing the events for which the emitter has registered listeners. The values in the array are strings or Symbols.

#### Returns

`QuadMatch`[]

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[eventNames](../interfaces/ISolidLdoDataset.md#eventnames)

#### Inherited from

LdoDataset.eventNames

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:272](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L272)

___

### every

▸ **every**(`iteratee`): `boolean`

Universal quantification method, tests whether every quad in the dataset passes the test implemented by the provided iteratee.
This method immediately returns boolean false once a quad that does not pass the test is found.
This method always returns boolean true on an empty dataset.
Note: This method is aligned with Array.prototype.every() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`boolean`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[every](../interfaces/ISolidLdoDataset.md#every)

#### Inherited from

LdoDataset.every

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:140](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L140)

___

### filter

▸ **filter**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

Creates a new dataset with all the quads that pass the test implemented by the provided iteratee.
Note: This method is aligned with Array.prototype.filter() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[filter](../interfaces/ISolidLdoDataset.md#filter)

#### Inherited from

LdoDataset.filter

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:154](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L154)

___

### forEach

▸ **forEach**(`iteratee`): `void`

Executes the provided iteratee once on each quad in the dataset.
Note: This method is aligned with Array.prototype.forEach() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `void` |

#### Returns

`void`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[forEach](../interfaces/ISolidLdoDataset.md#foreach)

#### Inherited from

LdoDataset.forEach

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:171](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L171)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

Returns the current max listener value for the EventEmitter which is either set by emitter.setMaxListeners(n) or defaults to events.defaultMaxListeners.

#### Returns

`number`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[getMaxListeners](../interfaces/ISolidLdoDataset.md#getmaxlisteners)

#### Inherited from

LdoDataset.getMaxListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:281](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L281)

___

### getResource

▸ **getResource**(`uri`, `options?`): [`Container`](Container.md)

Retireves a representation (either a LeafResource or a ContainerResource)
of a Solid Resource at the given URI. This resource represents the
current state of the resource: whether it is currently fetched or in the
process of fetching as well as some information about it.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) | the URI of the resource |
| `options?` | `ResourceGetterOptions` | Special options for getting the resource |

#### Returns

[`Container`](Container.md)

a Leaf or Container Resource

**`Example`**

```typescript
const profileDocument = solidLdoDataset
  .getResource("https://example.com/profile");
```

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[getResource](../interfaces/ISolidLdoDataset.md#getresource)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:84](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L84)

▸ **getResource**(`uri`, `options?`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Leaf`](Leaf.md)

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[getResource](../interfaces/ISolidLdoDataset.md#getresource)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:85](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L85)

▸ **getResource**(`uri`, `options?`): [`Container`](Container.md) \| [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Container`](Container.md) \| [`Leaf`](Leaf.md)

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[getResource](../interfaces/ISolidLdoDataset.md#getresource)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:86](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L86)

___

### getStorageFromWebId

▸ **getStorageFromWebId**(`webId`): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `GetStorageContainerFromWebIdSuccess` \| `NoRootContainerError`\>

Gets a list of root storage containers for a user given their WebId

#### Parameters

| Name | Type |
| :------ | :------ |
| `webId` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `GetStorageContainerFromWebIdSuccess` \| `NoRootContainerError`\>

A list of storages if successful, an error if not

**`Example`**

```typescript
const result = await solidLdoDataset
  .getStorageFromWebId("https://example.com/profile/card#me");
if (result.isError) {
  // Do something
}
console.log(result.storageContainer[0].uri);
```

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:137](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L137)

___

### has

▸ **has**(`quad`): `boolean`

Determines whether a dataset includes a certain quad, returning true or false as appropriate.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`boolean`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[has](../interfaces/ISolidLdoDataset.md#has)

#### Inherited from

LdoDataset.has

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:384](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L384)

___

### import

▸ **import**(`stream`): `Promise`\<[`SolidLdoDataset`](SolidLdoDataset.md)\>

Imports all quads from the given stream into the dataset.
The stream events end and error are wrapped in a Promise.

#### Parameters

| Name | Type |
| :------ | :------ |
| `stream` | `Stream`\<`Quad`\> |

#### Returns

`Promise`\<[`SolidLdoDataset`](SolidLdoDataset.md)\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[import](../interfaces/ISolidLdoDataset.md#import)

#### Inherited from

LdoDataset.import

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:182](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L182)

___

### intersection

▸ **intersection**(`other`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset containing alls quads from the current dataset that are also included in the given dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[intersection](../interfaces/ISolidLdoDataset.md#intersection)

#### Inherited from

LdoDataset.intersection

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:199](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L199)

___

### listenerCount

▸ **listenerCount**(`eventName`): `number`

Returns the number of listeners listening to the event named eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`number`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[listenerCount](../interfaces/ISolidLdoDataset.md#listenercount)

#### Inherited from

LdoDataset.listenerCount

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:288](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L288)

___

### listeners

▸ **listeners**(`eventName`): `nodeEventListener`\<`Quad`\>[]

Returns a copy of the array of listeners for the event named eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`nodeEventListener`\<`Quad`\>[]

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[listeners](../interfaces/ISolidLdoDataset.md#listeners)

#### Inherited from

LdoDataset.listeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:295](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L295)

___

### map

▸ **map**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset containing all quads returned by applying iteratee to each quad in the current dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `Quad` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[map](../interfaces/ISolidLdoDataset.md#map)

#### Inherited from

LdoDataset.map

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:217](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L217)

___

### match

▸ **match**(`subject?`, `predicate?`, `object?`, `graph?`): `Dataset`\<`Quad`, `Quad`\>

This method returns a new dataset that is comprised of all quads in the current instance matching the given arguments. The logic described in Quad Matching is applied for each quad in this dataset to check if it should be included in the output dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject?` | ``null`` \| `Term` |
| `predicate?` | ``null`` \| `Term` |
| `object?` | ``null`` \| `Term` |
| `graph?` | ``null`` \| `Term` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

a Dataset with matching triples

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[match](../interfaces/ISolidLdoDataset.md#match)

#### Inherited from

LdoDataset.match

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:340](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L340)

___

### off

▸ **off**(`eventName`, `listener`): `void`

Alias for emitter.removeListener()

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`void`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[off](../interfaces/ISolidLdoDataset.md#off)

#### Inherited from

LdoDataset.off

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:304](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L304)

___

### on

▸ **on**(`eventName`, `listener`): `this`

Adds the listener function to the end of the listeners array for the event named eventName. No checks are made to see if the listener has already been added. Multiple calls passing the same combination of eventName and listener will result in the listener being added, and called, multiple times.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[on](../interfaces/ISolidLdoDataset.md#on)

#### Inherited from

LdoDataset.on

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:314](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L314)

___

### once

▸ **once**(`eventName`, `listener`): `this`

Adds a one-time listener function for the event named eventName. The next time eventName is triggered, this listener is removed and then invoked.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[once](../interfaces/ISolidLdoDataset.md#once)

#### Inherited from

LdoDataset.once

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:330](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L330)

___

### prependListener

▸ **prependListener**(`eventName`, `listener`): `this`

Adds the listener function to the beginning of the listeners array for the event named eventName. No checks are made to see if the listener has already been added. Multiple calls passing the same combination of eventName and listener will result in the listener being added, and called, multiple times.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[prependListener](../interfaces/ISolidLdoDataset.md#prependlistener)

#### Inherited from

LdoDataset.prependListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:341](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L341)

___

### prependOnceListener

▸ **prependOnceListener**(`eventName`, `listener`): `this`

Adds a one-time listener function for the event named eventName to the beginning of the listeners array. The next time eventName is triggered, this listener is removed, and then invoked.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[prependOnceListener](../interfaces/ISolidLdoDataset.md#prependoncelistener)

#### Inherited from

LdoDataset.prependOnceListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:352](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L352)

___

### rawListeners

▸ **rawListeners**(`eventName`): `nodeEventListener`\<`Quad`\>[]

Returns a copy of the array of listeners for the event named eventName, including any wrappers (such as those created by .once()).

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`nodeEventListener`\<`Quad`\>[]

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[rawListeners](../interfaces/ISolidLdoDataset.md#rawlisteners)

#### Inherited from

LdoDataset.rawListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:406](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L406)

___

### reduce

▸ **reduce**\<`A`\>(`iteratee`, `initialValue?`): `A`

This method calls the iteratee on each quad of the DatasetCore. The first time the iteratee is called, the accumulator value is the initialValue or, if not given, equals to the first quad of the Dataset. The return value of the iteratee is used as accumulator value for the next calls.
This method returns the return value of the last iteratee call.
Note: This method is aligned with Array.prototype.reduce() in ECMAScript-262.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `A` | `unknown` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`accumulator`: `A`, `quad`: `Quad`, `dataset`: `this`) => `A` |
| `initialValue?` | `A` |

#### Returns

`A`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[reduce](../interfaces/ISolidLdoDataset.md#reduce)

#### Inherited from

LdoDataset.reduce

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:234](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L234)

___

### removeAllListeners

▸ **removeAllListeners**(`eventName`): `this`

Removes all listeners, or those of the specified eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[removeAllListeners](../interfaces/ISolidLdoDataset.md#removealllisteners)

#### Inherited from

LdoDataset.removeAllListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:366](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L366)

___

### removeListener

▸ **removeListener**(`eventName`, `listener`): `this`

Removes the specified listener from the listener array for the event named eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[removeListener](../interfaces/ISolidLdoDataset.md#removelistener)

#### Inherited from

LdoDataset.removeListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:374](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L374)

___

### removeListenerFromAllEvents

▸ **removeListenerFromAllEvents**(`listener`): `this`

Removes the specified listener from the listener array for the event named eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[removeListenerFromAllEvents](../interfaces/ISolidLdoDataset.md#removelistenerfromallevents)

#### Inherited from

LdoDataset.removeListenerFromAllEvents

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:385](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L385)

___

### setMaxListeners

▸ **setMaxListeners**(`n`): `this`

By default EventEmitters will print a warning if more than 10 listeners are added for a particular event. This is a useful default that helps finding memory leaks. The emitter.setMaxListeners() method allows the limit to be modified for this specific EventEmitter instance. The value can be set to Infinity (or 0) to indicate an unlimited number of listeners.

#### Parameters

| Name | Type |
| :------ | :------ |
| `n` | `number` |

#### Returns

`this`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[setMaxListeners](../interfaces/ISolidLdoDataset.md#setmaxlisteners)

#### Inherited from

LdoDataset.setMaxListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:398](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/SubscribableDataset.ts#L398)

___

### some

▸ **some**(`iteratee`): `boolean`

Existential quantification method, tests whether some quads in the dataset pass the test implemented by the provided iteratee.
Note: This method is aligned with Array.prototype.some() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`boolean`

boolean true once a quad that passes the test is found.

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[some](../interfaces/ISolidLdoDataset.md#some)

#### Inherited from

LdoDataset.some

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:259](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L259)

___

### startTransaction

▸ **startTransaction**(): [`SolidLdoTransactionDataset`](SolidLdoTransactionDataset.md)

#### Returns

[`SolidLdoTransactionDataset`](SolidLdoTransactionDataset.md)

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[startTransaction](../interfaces/ISolidLdoDataset.md#starttransaction)

#### Overrides

LdoDataset.startTransaction

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:91](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDataset.ts#L91)

___

### toArray

▸ **toArray**(): `Quad`[]

Returns the set of quads within the dataset as a host language native sequence, for example an Array in ECMAScript-262.
Note: Since a DatasetCore is an unordered set, the order of the quads within the returned sequence is arbitrary.

#### Returns

`Quad`[]

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[toArray](../interfaces/ISolidLdoDataset.md#toarray)

#### Inherited from

LdoDataset.toArray

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:272](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L272)

___

### toCanonical

▸ **toCanonical**(): `string`

Returns an N-Quads string representation of the dataset, preprocessed with RDF Dataset Normalization algorithm.

#### Returns

`string`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[toCanonical](../interfaces/ISolidLdoDataset.md#tocanonical)

#### Inherited from

LdoDataset.toCanonical

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:283](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L283)

___

### toStream

▸ **toStream**(): `Stream`\<`Quad`\>

Returns a stream that contains all quads of the dataset.

#### Returns

`Stream`\<`Quad`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[toStream](../interfaces/ISolidLdoDataset.md#tostream)

#### Inherited from

LdoDataset.toStream

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:290](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L290)

___

### toString

▸ **toString**(): `string`

Returns an N-Quads string representation of the dataset.
No prior normalization is required, therefore the results for the same quads may vary depending on the Dataset implementation.

#### Returns

`string`

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[toString](../interfaces/ISolidLdoDataset.md#tostring)

#### Inherited from

LdoDataset.toString

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:311](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L311)

___

### union

▸ **union**(`other`): `Dataset`\<`Quad`, `Quad`\>

Returns a new Dataset that is a concatenation of this dataset and the quads given as an argument.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[union](../interfaces/ISolidLdoDataset.md#union)

#### Inherited from

LdoDataset.union

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:319](https://github.com/o-development/ldo/blob/c70613a/packages/dataset/src/ExtendedDataset.ts#L319)

___

### usingType

▸ **usingType**\<`Type`\>(`shapeType`): `LdoBuilder`\<`Type`\>

Creates an LdoBuilder for a given shapeType

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `shapeType` | `ShapeType`\<`Type`\> | A ShapeType |

#### Returns

`LdoBuilder`\<`Type`\>

A builder for the given type

#### Implementation of

[ISolidLdoDataset](../interfaces/ISolidLdoDataset.md).[usingType](../interfaces/ISolidLdoDataset.md#usingtype)

#### Inherited from

LdoDataset.usingType

#### Defined in

[packages/ldo/src/LdoDataset.ts:37](https://github.com/o-development/ldo/blob/c70613a/packages/ldo/src/LdoDataset.ts#L37)
