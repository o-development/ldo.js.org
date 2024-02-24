# Class: SolidLdoTransactionDataset

A SolidLdoTransactionDataset has all the functionality of a SolidLdoDataset
and represents a transaction to the parent SolidLdoDataset.

It is recommended to use the `startTransaction` method on a SolidLdoDataset
to initialize this class

**`Example`**

```typescript
import { createSolidLdoDataset } from "@ldo/solid";
import { ProfileShapeType } from "./.ldo/profile.shapeTypes.ts"

// ...

const solidLdoDataset = createSolidLdoDataset();

const profileDocument = solidLdoDataset
  .getResource("https://example.com/profile");
await profileDocument.read();

const transaction = solidLdoDataset.startTransaction();

const profile = transaction
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
profile.name = "Some Name";
await transaction.commitToPod();
```

## Hierarchy

- `LdoTransactionDataset`

  ↳ **`SolidLdoTransactionDataset`**

## Implements

- `ISolidLdoDataset`

## Constructors

### constructor

• **new SolidLdoTransactionDataset**(`parentDataset`, `context`, `datasetFactory`, `transactionDatasetFactory`): [`SolidLdoTransactionDataset`](SolidLdoTransactionDataset.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `parentDataset` | [`SolidLdoDataset`](SolidLdoDataset.md) | - |
| `context` | [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md) | SolidLdoDatasetContext |
| `datasetFactory` | `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\> | An optional dataset factory |
| `transactionDatasetFactory` | `ITransactionDatasetFactory`\<`Quad`\> | A factory for creating transaction datasets |

#### Returns

[`SolidLdoTransactionDataset`](SolidLdoTransactionDataset.md)

#### Overrides

LdoTransactionDataset.constructor

#### Defined in

[packages/solid/src/SolidLdoTransactionDataset.ts:77](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/SolidLdoTransactionDataset.ts#L77)

## Properties

### context

• **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

#### Defined in

[packages/solid/src/SolidLdoTransactionDataset.ts:69](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/SolidLdoTransactionDataset.ts#L69)

___

### dataset

• `Protected` **dataset**: `DatasetCore`\<`Quad`, `Quad`\>

The main backing dataset

#### Inherited from

LdoTransactionDataset.dataset

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:22](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L22)

___

### datasetCoreFactory

• `Protected` **datasetCoreFactory**: `DatasetCoreFactory`\<`Quad`, `Quad`, `DatasetCore`\<`Quad`, `Quad`\>\>

A factory that generates datasets for the methods

#### Inherited from

LdoTransactionDataset.datasetCoreFactory

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:27](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L27)

___

### datasetFactory

• `Protected` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

DatasetFactory for creating new datasets

#### Inherited from

LdoTransactionDataset.datasetFactory

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:31](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L31)

___

### eventEmitter

• `Protected` **eventEmitter**: `EventEmitter`

The underlying event emitter

#### Inherited from

LdoTransactionDataset.eventEmitter

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:36](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L36)

___

### parentDataset

• `Readonly` **parentDataset**: `Dataset`\<`Quad`, `Quad`\>

The parent dataset that will be updated upon commit

#### Inherited from

LdoTransactionDataset.parentDataset

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:20](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L20)

___

### transactionDatasetFactory

• `Protected` **transactionDatasetFactory**: `ITransactionDatasetFactory`\<`Quad`\>

The underlying dataset factory for creating transaction datasets

#### Inherited from

LdoTransactionDataset.transactionDatasetFactory

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:40](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L40)

## Accessors

### size

• `get` **size**(): `number`

A non-negative integer that specifies the number of quads in the set.

#### Returns

`number`

#### Inherited from

LdoTransactionDataset.size

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:134](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L134)

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `any`, `undefined`\>

Returns an iterator

#### Returns

`Iterator`\<`Quad`, `any`, `undefined`\>

#### Inherited from

LdoTransactionDataset.[iterator]

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:177](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L177)

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

#### Inherited from

LdoTransactionDataset.add

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:148](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L148)

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

#### Inherited from

LdoTransactionDataset.addAll

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:62](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L62)

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

#### Inherited from

LdoTransactionDataset.addListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:248](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L248)

___

### bulk

▸ **bulk**(`changes`): `this`

Bulk add and remove triples

#### Parameters

| Name | Type |
| :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoTransactionDataset.bulk

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:73](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L73)

___

### commit

▸ **commit**(): `void`

Commits changes made to the parent dataset

#### Returns

`void`

#### Inherited from

LdoTransactionDataset.commit

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:256](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L256)

___

### commitToPod

▸ **commitToPod**(): `Promise`\<`AggregateSuccess`\<`ResourceResult`\<`UpdateSuccess` \| `UpdateDefaultGraphSuccess`, [`Leaf`](Leaf.md)\>\> \| `AggregateError`\<[`UpdateResultError`](../types/UpdateResultError.md) \| `InvalidUriError`\>\>

#### Returns

`Promise`\<`AggregateSuccess`\<`ResourceResult`\<`UpdateSuccess` \| `UpdateDefaultGraphSuccess`, [`Leaf`](Leaf.md)\>\> \| `AggregateError`\<[`UpdateResultError`](../types/UpdateResultError.md) \| `InvalidUriError`\>\>

#### Defined in

[packages/solid/src/SolidLdoTransactionDataset.ts:111](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/SolidLdoTransactionDataset.ts#L111)

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

#### Inherited from

LdoTransactionDataset.contains

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:68](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L68)

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

#### Inherited from

LdoTransactionDataset.delete

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:158](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L158)

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

#### Inherited from

LdoTransactionDataset.deleteMatches

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:86](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L86)

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

#### Inherited from

LdoTransactionDataset.difference

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:105](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L105)

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

#### Inherited from

LdoTransactionDataset.emit

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:262](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L262)

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

#### Inherited from

LdoTransactionDataset.equals

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:121](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L121)

___

### eventNames

▸ **eventNames**(): `QuadMatch`[]

Returns an array listing the events for which the emitter has registered listeners. The values in the array are strings or Symbols.

#### Returns

`QuadMatch`[]

#### Inherited from

LdoTransactionDataset.eventNames

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:272](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L272)

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

#### Inherited from

LdoTransactionDataset.every

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:140](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L140)

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

#### Inherited from

LdoTransactionDataset.filter

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:154](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L154)

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

#### Inherited from

LdoTransactionDataset.forEach

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:171](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L171)

___

### getChanges

▸ **getChanges**(): `DatasetChanges`\<`Quad`\>

#### Returns

`DatasetChanges`\<`Quad`\>

#### Inherited from

LdoTransactionDataset.getChanges

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:281](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L281)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

Returns the current max listener value for the EventEmitter which is either set by emitter.setMaxListeners(n) or defaults to events.defaultMaxListeners.

#### Returns

`number`

#### Inherited from

LdoTransactionDataset.getMaxListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:281](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L281)

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

ISolidLdoDataset.getResource

#### Defined in

[packages/solid/src/SolidLdoTransactionDataset.ts:104](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/SolidLdoTransactionDataset.ts#L104)

▸ **getResource**(`uri`, `options?`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Leaf`](Leaf.md)

#### Implementation of

ISolidLdoDataset.getResource

#### Defined in

[packages/solid/src/SolidLdoTransactionDataset.ts:105](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/SolidLdoTransactionDataset.ts#L105)

▸ **getResource**(`uri`, `options?`): [`Leaf`](Leaf.md) \| [`Container`](Container.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Leaf`](Leaf.md) \| [`Container`](Container.md)

#### Implementation of

ISolidLdoDataset.getResource

#### Defined in

[packages/solid/src/SolidLdoTransactionDataset.ts:106](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/SolidLdoTransactionDataset.ts#L106)

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

#### Inherited from

LdoTransactionDataset.has

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:167](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L167)

___

### import

▸ **import**(`stream`): `Promise`\<[`SolidLdoTransactionDataset`](SolidLdoTransactionDataset.md)\>

Imports all quads from the given stream into the dataset.
The stream events end and error are wrapped in a Promise.

#### Parameters

| Name | Type |
| :------ | :------ |
| `stream` | `Stream`\<`Quad`\> |

#### Returns

`Promise`\<[`SolidLdoTransactionDataset`](SolidLdoTransactionDataset.md)\>

#### Inherited from

LdoTransactionDataset.import

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:182](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L182)

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

#### Inherited from

LdoTransactionDataset.intersection

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:199](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L199)

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

#### Inherited from

LdoTransactionDataset.listenerCount

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:288](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L288)

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

#### Inherited from

LdoTransactionDataset.listeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:295](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L295)

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

#### Inherited from

LdoTransactionDataset.map

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:217](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L217)

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

#### Inherited from

LdoTransactionDataset.match

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:108](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L108)

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

#### Inherited from

LdoTransactionDataset.off

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:304](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L304)

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

#### Inherited from

LdoTransactionDataset.on

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:314](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L314)

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

#### Inherited from

LdoTransactionDataset.once

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:330](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L330)

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

#### Inherited from

LdoTransactionDataset.prependListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:341](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L341)

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

#### Inherited from

LdoTransactionDataset.prependOnceListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:352](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L352)

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

#### Inherited from

LdoTransactionDataset.rawListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:406](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L406)

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

#### Inherited from

LdoTransactionDataset.reduce

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:234](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L234)

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

#### Inherited from

LdoTransactionDataset.removeAllListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:366](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L366)

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

#### Inherited from

LdoTransactionDataset.removeListener

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:374](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L374)

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

#### Inherited from

LdoTransactionDataset.removeListenerFromAllEvents

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:385](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L385)

___

### rollback

▸ **rollback**(): `void`

Rolls back changes made to the parent dataset

#### Returns

`void`

#### Inherited from

LdoTransactionDataset.rollback

#### Defined in

[packages/subscribable-dataset/src/TransactionDataset.ts:268](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/TransactionDataset.ts#L268)

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

#### Inherited from

LdoTransactionDataset.setMaxListeners

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:398](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L398)

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

#### Inherited from

LdoTransactionDataset.some

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:259](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L259)

___

### startTransaction

▸ **startTransaction**(): `ITransactionDataset`\<`Quad`\>

Returns a transactional dataset that will update this dataset when its transaction is committed.

#### Returns

`ITransactionDataset`\<`Quad`\>

#### Inherited from

LdoTransactionDataset.startTransaction

#### Defined in

[packages/subscribable-dataset/src/SubscribableDataset.ts:421](https://github.com/o-development/ldo/blob/e8bb8b1/packages/subscribable-dataset/src/SubscribableDataset.ts#L421)

___

### toArray

▸ **toArray**(): `Quad`[]

Returns the set of quads within the dataset as a host language native sequence, for example an Array in ECMAScript-262.
Note: Since a DatasetCore is an unordered set, the order of the quads within the returned sequence is arbitrary.

#### Returns

`Quad`[]

#### Inherited from

LdoTransactionDataset.toArray

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:272](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L272)

___

### toCanonical

▸ **toCanonical**(): `string`

Returns an N-Quads string representation of the dataset, preprocessed with RDF Dataset Normalization algorithm.

#### Returns

`string`

#### Inherited from

LdoTransactionDataset.toCanonical

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:283](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L283)

___

### toStream

▸ **toStream**(): `Stream`\<`Quad`\>

Returns a stream that contains all quads of the dataset.

#### Returns

`Stream`\<`Quad`\>

#### Inherited from

LdoTransactionDataset.toStream

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:290](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L290)

___

### toString

▸ **toString**(): `string`

Returns an N-Quads string representation of the dataset.
No prior normalization is required, therefore the results for the same quads may vary depending on the Dataset implementation.

#### Returns

`string`

#### Inherited from

LdoTransactionDataset.toString

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:311](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L311)

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

#### Inherited from

LdoTransactionDataset.union

#### Defined in

[packages/dataset/src/ExtendedDataset.ts:319](https://github.com/o-development/ldo/blob/e8bb8b1/packages/dataset/src/ExtendedDataset.ts#L319)

___

### usingType

▸ **usingType**\<`Type`\>(`shapeType`): `LdoBuilder`\<`Type`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `shapeType` | `ShapeType`\<`Type`\> |

#### Returns

`LdoBuilder`\<`Type`\>

#### Inherited from

LdoTransactionDataset.usingType

#### Defined in

[packages/ldo/src/LdoTransactionDataset.ts:13](https://github.com/o-development/ldo/blob/e8bb8b1/packages/ldo/src/LdoTransactionDataset.ts#L13)
