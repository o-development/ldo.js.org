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

## Constructors

### constructor

• **new SolidLdoDataset**(`context`, `datasetFactory`, `initialDataset?`): [`SolidLdoDataset`](SolidLdoDataset.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md) | SolidLdoDatasetContext |
| `datasetFactory` | `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\> | An optional dataset factory |
| `initialDataset?` | `Dataset`\<`Quad`, `Quad`\> | A set of triples to initialize this dataset |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Overrides

LdoDataset.constructor

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:62](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L62)

## Properties

### context

• **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:55](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L55)

## Accessors

### size

• `get` **size**(): `number`

A non-negative integer that specifies the number of quads in the set.

#### Returns

`number`

#### Inherited from

LdoDataset.size

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:307](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L307)

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `unknown`, `undefined`\>

Returns an iterator

#### Returns

`Iterator`\<`Quad`, `unknown`, `undefined`\>

#### Inherited from

LdoDataset.[iterator]

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:349](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L349)

___

### add

▸ **add**(`quad`): [`SolidLdoDataset`](SolidLdoDataset.md)

Adds the specified quad to the dataset.
Existing quads, as defined in Quad.equals, will be ignored.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

the dataset instance it was called on.

#### Inherited from

LdoDataset.add

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:317](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L317)

___

### addAll

▸ **addAll**(`quads`): [`SolidLdoDataset`](SolidLdoDataset.md)

Imports the quads into this dataset.
This method differs from Dataset.union in that it adds all quads to the current instance, rather than combining quads and the current instance to create a new instance.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Quad`[] \| `Dataset`\<`Quad`, `Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

the dataset instance it was called on.

#### Inherited from

LdoDataset.addAll

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:76](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L76)

___

### addListener

▸ **addListener**(`eventName`, `listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Alias for emitter.on(eventName, listener).

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.addListener

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:439](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L439)

___

### bulk

▸ **bulk**(`changed`): [`SolidLdoDataset`](SolidLdoDataset.md)

Bulk add and remove triples

#### Parameters

| Name | Type |
| :------ | :------ |
| `changed` | `DatasetChanges`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.bulk

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:90](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L90)

___

### commitChangesToPod

▸ **commitChangesToPod**(`changes`): `Promise`\<`AggregateSuccess`\<`ResourceResult`\<`UpdateSuccess` \| `UpdateDefaultGraphSuccess`, [`Leaf`](Leaf.md)\>\> \| `AggregateError`\<[`UpdateResultError`](../types/UpdateResultError.md) \| `InvalidUriError`\>\>

Given dataset changes, commit all changes made to the proper place
on Solid Pods.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> | A set of changes that should be applied to Solid Pods |

#### Returns

`Promise`\<`AggregateSuccess`\<`ResourceResult`\<`UpdateSuccess` \| `UpdateDefaultGraphSuccess`, [`Leaf`](Leaf.md)\>\> \| `AggregateError`\<[`UpdateResultError`](../types/UpdateResultError.md) \| `InvalidUriError`\>\>

an AggregateSuccess if successful and an AggregateError if not

**`Example`**

```typescript
const result = await solidLdoDataset.commitChangesToPod({
  added: createDataset([
    quad(namedNode("a"), namedNode("b"), namedNode("d"));
  ]),
  removed: createDataset([
    quad(namedNode("a"), namedNode("b"), namedNode("c"));
  ])
});
if (result.isError()) {
  // handle error
}
```

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:118](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L118)

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

LdoDataset.contains

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:108](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L108)

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

[packages/solid/src/SolidLdoDataset.ts:198](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L198)

___

### delete

▸ **delete**(`quad`): [`SolidLdoDataset`](SolidLdoDataset.md)

Removes the specified quad from the dataset.
This method returns the dataset instance it was called on.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.delete

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:330](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L330)

___

### deleteMatches

▸ **deleteMatches**(`subject?`, `predicate?`, `object?`, `graph?`): [`SolidLdoDataset`](SolidLdoDataset.md)

This method removes the quads in the current instance that match the given arguments. The logic described in Quad Matching is applied for each quad in this dataset to select the quads which will be deleted.

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject?` | `Term` |
| `predicate?` | `Term` |
| `object?` | `Term` |
| `graph?` | `Term` |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

the dataset instance it was called on.

#### Inherited from

LdoDataset.deleteMatches

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:120](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L120)

___

### difference

▸ **difference**(`other`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset that contains alls quads from the current dataset, not included in the given dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.difference

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:138](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L138)

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

LdoDataset.emit

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:453](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L453)

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

LdoDataset.equals

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:148](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L148)

___

### eventNames

▸ **eventNames**(): `QuadMatch`[]

Returns an array listing the events for which the emitter has registered listeners. The values in the array are strings or Symbols.

#### Returns

`QuadMatch`[]

#### Inherited from

LdoDataset.eventNames

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:463](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L463)

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
| `iteratee` | (`quad`: `Quad`, `dataset`: [`SolidLdoDataset`](SolidLdoDataset.md)) => `boolean` |

#### Returns

`boolean`

#### Inherited from

LdoDataset.every

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:159](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L159)

___

### filter

▸ **filter**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

Creates a new dataset with all the quads that pass the test implemented by the provided iteratee.
Note: This method is aligned with Array.prototype.filter() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: [`SolidLdoDataset`](SolidLdoDataset.md)) => `boolean` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.filter

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:170](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L170)

___

### forEach

▸ **forEach**(`iteratee`): `void`

Executes the provided iteratee once on each quad in the dataset.
Note: This method is aligned with Array.prototype.forEach() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: [`SolidLdoDataset`](SolidLdoDataset.md)) => `void` |

#### Returns

`void`

#### Inherited from

LdoDataset.forEach

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:181](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L181)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

Returns the current max listener value for the EventEmitter which is either set by emitter.setMaxListeners(n) or defaults to events.defaultMaxListeners.

#### Returns

`number`

#### Inherited from

LdoDataset.getMaxListeners

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:472](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L472)

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

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:88](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L88)

▸ **getResource**(`uri`, `options?`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Leaf`](Leaf.md)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:89](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L89)

▸ **getResource**(`uri`, `options?`): [`Leaf`](Leaf.md) \| [`Container`](Container.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Leaf`](Leaf.md) \| [`Container`](Container.md)

#### Defined in

[packages/solid/src/SolidLdoDataset.ts:90](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/SolidLdoDataset.ts#L90)

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

LdoDataset.has

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:342](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L342)

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

#### Inherited from

LdoDataset.import

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:190](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L190)

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

LdoDataset.intersection

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:202](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L202)

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

LdoDataset.listenerCount

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:479](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L479)

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

LdoDataset.listeners

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:486](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L486)

___

### map

▸ **map**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset containing all quads returned by applying iteratee to each quad in the current dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: [`SolidLdoDataset`](SolidLdoDataset.md)) => `Quad` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.map

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:212](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L212)

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

LdoDataset.match

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:295](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L295)

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

LdoDataset.off

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:495](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L495)

___

### on

▸ **on**(`eventName`, `listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Adds the listener function to the end of the listeners array for the event named eventName. No checks are made to see if the listener has already been added. Multiple calls passing the same combination of eventName and listener will result in the listener being added, and called, multiple times.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.on

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:505](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L505)

___

### once

▸ **once**(`eventName`, `listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Adds a one-time listener function for the event named eventName. The next time eventName is triggered, this listener is removed and then invoked.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.once

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:521](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L521)

___

### prependListener

▸ **prependListener**(`eventName`, `listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Adds the listener function to the beginning of the listeners array for the event named eventName. No checks are made to see if the listener has already been added. Multiple calls passing the same combination of eventName and listener will result in the listener being added, and called, multiple times.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.prependListener

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:532](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L532)

___

### prependOnceListener

▸ **prependOnceListener**(`eventName`, `listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Adds a one-time listener function for the event named eventName to the beginning of the listeners array. The next time eventName is triggered, this listener is removed, and then invoked.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.prependOnceListener

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:543](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L543)

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

LdoDataset.rawListeners

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:597](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L597)

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
| `iteratee` | (`accumulator`: `A`, `quad`: `Quad`, `dataset`: [`SolidLdoDataset`](SolidLdoDataset.md)) => `A` |
| `initialValue?` | `A` |

#### Returns

`A`

#### Inherited from

LdoDataset.reduce

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:225](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L225)

___

### removeAllListeners

▸ **removeAllListeners**(`eventName`): [`SolidLdoDataset`](SolidLdoDataset.md)

Removes all listeners, or those of the specified eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.removeAllListeners

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:557](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L557)

___

### removeListener

▸ **removeListener**(`eventName`, `listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Removes the specified listener from the listener array for the event named eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.removeListener

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:565](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L565)

___

### removeListenerFromAllEvents

▸ **removeListenerFromAllEvents**(`listener`): [`SolidLdoDataset`](SolidLdoDataset.md)

Removes the specified listener from the listener array for the event named eventName.

#### Parameters

| Name | Type |
| :------ | :------ |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.removeListenerFromAllEvents

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:576](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L576)

___

### setMaxListeners

▸ **setMaxListeners**(`n`): [`SolidLdoDataset`](SolidLdoDataset.md)

By default EventEmitters will print a warning if more than 10 listeners are added for a particular event. This is a useful default that helps finding memory leaks. The emitter.setMaxListeners() method allows the limit to be modified for this specific EventEmitter instance. The value can be set to Infinity (or 0) to indicate an unlimited number of listeners.

#### Parameters

| Name | Type |
| :------ | :------ |
| `n` | `number` |

#### Returns

[`SolidLdoDataset`](SolidLdoDataset.md)

#### Inherited from

LdoDataset.setMaxListeners

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:589](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L589)

___

### some

▸ **some**(`iteratee`): `boolean`

Existential quantification method, tests whether some quads in the dataset pass the test implemented by the provided iteratee.
Note: This method is aligned with Array.prototype.some() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: [`SolidLdoDataset`](SolidLdoDataset.md)) => `boolean` |

#### Returns

`boolean`

boolean true once a quad that passes the test is found.

#### Inherited from

LdoDataset.some

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:241](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L241)

___

### startTransaction

▸ **startTransaction**(): `TransactionalDataset`\<`Quad`\>

Returns a transactional dataset that will update this dataset when its transaction is committed.

#### Returns

`TransactionalDataset`\<`Quad`\>

#### Inherited from

LdoDataset.startTransaction

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:612](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L612)

___

### toArray

▸ **toArray**(): `Quad`[]

Returns the set of quads within the dataset as a host language native sequence, for example an Array in ECMAScript-262.
Note: Since a DatasetCore is an unordered set, the order of the quads within the returned sequence is arbitrary.

#### Returns

`Quad`[]

#### Inherited from

LdoDataset.toArray

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:251](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L251)

___

### toCanonical

▸ **toCanonical**(): `string`

Returns an N-Quads string representation of the dataset, preprocessed with RDF Dataset Normalization algorithm.

#### Returns

`string`

#### Inherited from

LdoDataset.toCanonical

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:258](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L258)

___

### toStream

▸ **toStream**(): `Stream`\<`Quad`\>

Returns a stream that contains all quads of the dataset.

#### Returns

`Stream`\<`Quad`\>

#### Inherited from

LdoDataset.toStream

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:265](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L265)

___

### toString

▸ **toString**(): `string`

Returns an N-Quads string representation of the dataset.
No prior normalization is required, therefore the results for the same quads may vary depending on the Dataset implementation.

#### Returns

`string`

#### Inherited from

LdoDataset.toString

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:273](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L273)

___

### union

▸ **union**(`quads`): `Dataset`\<`Quad`, `Quad`\>

Returns a new Dataset that is a concatenation of this dataset and the quads given as an argument.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.union

#### Defined in

[packages/subscribable-dataset/src/WrapperSubscribableDataset.ts:281](https://github.com/o-development/ldo/blob/b955d3b/packages/subscribable-dataset/src/WrapperSubscribableDataset.ts#L281)

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

#### Inherited from

LdoDataset.usingType

#### Defined in

[packages/ldo/src/LdoDataset.ts:32](https://github.com/o-development/ldo/blob/b955d3b/packages/ldo/src/LdoDataset.ts#L32)
