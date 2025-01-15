# Interface: ISolidLdoDataset

A SolidLdoDataset provides methods for getting Solid resources.

## Hierarchy

- `ILdoDataset`

  ↳ **`ISolidLdoDataset`**

## Implemented by

- [`SolidLdoDataset`](../classes/SolidLdoDataset.md)
- [`SolidLdoTransactionDataset`](../classes/SolidLdoTransactionDataset.md)

## Properties

### size

• `Readonly` **size**: `number`

A non-negative integer that specifies the number of quads in the set.

#### Inherited from

ILdoDataset.size

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:11

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `any`, `undefined`\>

#### Returns

`Iterator`\<`Quad`, `any`, `undefined`\>

#### Inherited from

ILdoDataset.[iterator]

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:47

___

### add

▸ **add**(`quad`): `this`

Adds the specified quad to the dataset.

Existing quads, as defined in `Quad.equals`, will be ignored.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Inherited from

ILdoDataset.add

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:18

___

### addAll

▸ **addAll**(`quads`): `this`

Imports the quads into this dataset.

This method differs from `Dataset.union` in that it adds all `quads` to the current instance, rather than
combining `quads` and the current instance to create a new instance.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Quad`[] \| `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`this`

#### Inherited from

ILdoDataset.addAll

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:64

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

ILdoDataset.addListener

#### Defined in

[packages/subscribable-dataset/src/types.ts:43](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L43)

___

### bulk

▸ **bulk**(`changes`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

ILdoDataset.bulk

#### Defined in

[packages/subscribable-dataset/src/types.ts:16](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L16)

___

### contains

▸ **contains**(`other`): `boolean`

Returns `true` if the current instance is a superset of the given dataset; differently put: if the given dataset
is a subset of, is contained in the current dataset.

Blank Nodes will be normalized.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Inherited from

ILdoDataset.contains

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:72

___

### delete

▸ **delete**(`quad`): `this`

Removes the specified quad from the dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Inherited from

ILdoDataset.delete

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:23

___

### deleteMatches

▸ **deleteMatches**(`subject?`, `predicate?`, `object?`, `graph?`): `this`

This method removes the quads in the current instance that match the given arguments.

The logic described in [Matching](https://rdf.js.org/dataset-spec/#quad-matching|Quad) is applied for each
quad in this dataset to select the quads which will be deleted.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `subject?` | `Term` | The optional exact subject to match. |
| `predicate?` | `Term` | The optional exact predicate to match. |
| `object?` | `Term` | The optional exact object to match. |
| `graph?` | `Term` | The optional exact graph to match. |

#### Returns

`this`

#### Inherited from

ILdoDataset.deleteMatches

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:85

___

### difference

▸ **difference**(`other`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset that contains all quads from the current dataset, not included in the given dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

ILdoDataset.difference

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:90

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

ILdoDataset.emit

#### Defined in

[packages/subscribable-dataset/src/types.ts:54](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L54)

___

### equals

▸ **equals**(`other`): `boolean`

Returns true if the current instance contains the same graph structure as the given dataset.

Blank Nodes will be normalized.

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Inherited from

ILdoDataset.equals

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:97

___

### eventNames

▸ **eventNames**(): `QuadMatch`[]

Returns an array listing the events for which the emitter has registered listeners. The values in the array are strings or Symbols.

#### Returns

`QuadMatch`[]

#### Inherited from

ILdoDataset.eventNames

#### Defined in

[packages/subscribable-dataset/src/types.ts:59](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L59)

___

### every

▸ **every**(`iteratee`): `boolean`

Universal quantification method, tests whether every quad in the dataset passes the test implemented by the
provided `iteratee`.

This method immediately returns boolean `false` once a quad that does not pass the test is found.

This method always returns boolean `true` on an empty dataset.

This method is aligned with `Array.prototype.every()` in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`boolean`

#### Inherited from

ILdoDataset.every

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:109

___

### filter

▸ **filter**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

Creates a new dataset with all the quads that pass the test implemented by the provided `iteratee`.

This method is aligned with Array.prototype.filter() in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

ILdoDataset.filter

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:116

___

### forEach

▸ **forEach**(`callback`): `void`

Executes the provided `iteratee` once on each quad in the dataset.

This method is aligned with `Array.prototype.forEach()` in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `callback` | (`quad`: `Quad`, `dataset`: `this`) => `void` |

#### Returns

`void`

#### Inherited from

ILdoDataset.forEach

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:123

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

Returns the current max listener value for the EventEmitter which is either set by emitter.setMaxListeners(n) or defaults to events.defaultMaxListeners.

#### Returns

`number`

#### Inherited from

ILdoDataset.getMaxListeners

#### Defined in

[packages/subscribable-dataset/src/types.ts:64](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L64)

___

### getResource

▸ **getResource**(`uri`, `options?`): [`Container`](../classes/Container.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Container`](../classes/Container.md)

#### Defined in

[packages/solid/src/types.ts:14](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/types.ts#L14)

▸ **getResource**(`uri`, `options?`): [`Leaf`](../classes/Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Leaf`](../classes/Leaf.md)

#### Defined in

[packages/solid/src/types.ts:15](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/types.ts#L15)

▸ **getResource**(`uri`, `options?`): [`Container`](../classes/Container.md) \| [`Leaf`](../classes/Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Container`](../classes/Container.md) \| [`Leaf`](../classes/Leaf.md)

#### Defined in

[packages/solid/src/types.ts:16](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/types.ts#L16)

▸ **getResource**(`uri`, `options?`): [`Container`](../classes/Container.md) \| [`Leaf`](../classes/Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | `ResourceGetterOptions` |

#### Returns

[`Container`](../classes/Container.md) \| [`Leaf`](../classes/Leaf.md)

#### Defined in

[packages/solid/src/types.ts:17](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/types.ts#L17)

___

### has

▸ **has**(`quad`): `boolean`

Determines whether a dataset includes a certain quad.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`boolean`

#### Inherited from

ILdoDataset.has

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:28

___

### import

▸ **import**(`stream`): `Promise`\<[`ISolidLdoDataset`](ISolidLdoDataset.md)\>

Imports all quads from the given stream into the dataset.

The stream events `end` and `error` are wrapped in a Promise.

#### Parameters

| Name | Type |
| :------ | :------ |
| `stream` | `Stream`\<`Quad`\> |

#### Returns

`Promise`\<[`ISolidLdoDataset`](ISolidLdoDataset.md)\>

#### Inherited from

ILdoDataset.import

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:130

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

ILdoDataset.intersection

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:135

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

ILdoDataset.listenerCount

#### Defined in

[packages/subscribable-dataset/src/types.ts:69](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L69)

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

ILdoDataset.listeners

#### Defined in

[packages/subscribable-dataset/src/types.ts:74](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L74)

___

### map

▸ **map**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

Returns a new dataset containing all quads returned by applying `iteratee` to each quad in the current dataset.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `Dataset`\<`Quad`, `Quad`\>) => `Quad` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

ILdoDataset.map

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:140

___

### match

▸ **match**(`subject?`, `predicate?`, `object?`, `graph?`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject?` | ``null`` \| `Term` |
| `predicate?` | ``null`` \| `Term` |
| `object?` | ``null`` \| `Term` |
| `graph?` | ``null`` \| `Term` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

ILdoDataset.match

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:195

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

ILdoDataset.off

#### Defined in

[packages/subscribable-dataset/src/types.ts:79](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L79)

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

ILdoDataset.on

#### Defined in

[packages/subscribable-dataset/src/types.ts:84](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L84)

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

ILdoDataset.once

#### Defined in

[packages/subscribable-dataset/src/types.ts:89](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L89)

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

ILdoDataset.prependListener

#### Defined in

[packages/subscribable-dataset/src/types.ts:94](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L94)

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

ILdoDataset.prependOnceListener

#### Defined in

[packages/subscribable-dataset/src/types.ts:102](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L102)

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

ILdoDataset.rawListeners

#### Defined in

[packages/subscribable-dataset/src/types.ts:133](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L133)

___

### reduce

▸ **reduce**\<`A`\>(`callback`, `initialValue?`): `A`

This method calls the `iteratee` on each `quad` of the `Dataset`. The first time the `iteratee` is called, the
`accumulator` value is the `initialValue` or, if not given, equals to the first quad of the `Dataset`. The return
value of the `iteratee` is used as `accumulator` value for the next calls.

This method returns the return value of the last `iteratee` call.

This method is aligned with `Array.prototype.reduce()` in ECMAScript-262.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `A` | `any` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `callback` | (`accumulator`: `A`, `quad`: `Quad`, `dataset`: `this`) => `A` |
| `initialValue?` | `A` |

#### Returns

`A`

#### Inherited from

ILdoDataset.reduce

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:151

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

ILdoDataset.removeAllListeners

#### Defined in

[packages/subscribable-dataset/src/types.ts:110](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L110)

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

ILdoDataset.removeListener

#### Defined in

[packages/subscribable-dataset/src/types.ts:115](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L115)

___

### removeListenerFromAllEvents

▸ **removeListenerFromAllEvents**(`listener`): `this`

Removes the specified listener from all events

#### Parameters

| Name | Type |
| :------ | :------ |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

ILdoDataset.removeListenerFromAllEvents

#### Defined in

[packages/subscribable-dataset/src/types.ts:123](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L123)

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

ILdoDataset.setMaxListeners

#### Defined in

[packages/subscribable-dataset/src/types.ts:128](https://github.com/o-development/ldo/blob/c70613a/packages/subscribable-dataset/src/types.ts#L128)

___

### some

▸ **some**(`iteratee`): `boolean`

Existential quantification method, tests whether some quads in the dataset pass the test implemented by the
provided `iteratee`.

This method immediately returns boolean `true` once a quad that passes the test is found.

This method is aligned with `Array.prototype.some()` in ECMAScript-262.

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`boolean`

#### Inherited from

ILdoDataset.some

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:161

___

### startTransaction

▸ **startTransaction**(): [`SolidLdoTransactionDataset`](../classes/SolidLdoTransactionDataset.md)

#### Returns

[`SolidLdoTransactionDataset`](../classes/SolidLdoTransactionDataset.md)

#### Overrides

ILdoDataset.startTransaction

#### Defined in

[packages/solid/src/types.ts:12](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/types.ts#L12)

___

### toArray

▸ **toArray**(): `Quad`[]

Returns the set of quads within the dataset as a host language native sequence, for example an `Array` in
ECMAScript-262.

Since a `Dataset` is an unordered set, the order of the quads within the returned sequence is arbitrary.

#### Returns

`Quad`[]

#### Inherited from

ILdoDataset.toArray

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:169

___

### toCanonical

▸ **toCanonical**(): `string`

Returns an N-Quads string representation of the dataset, preprocessed with
[Dataset Normalization](https://json-ld.github.io/normalization/spec/|RDF) algorithm.

#### Returns

`string`

#### Inherited from

ILdoDataset.toCanonical

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:175

___

### toStream

▸ **toStream**(): `Stream`\<`Quad`\>

Returns a stream that contains all quads of the dataset.

#### Returns

`Stream`\<`Quad`\>

#### Inherited from

ILdoDataset.toStream

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:180

___

### toString

▸ **toString**(): `string`

Returns an N-Quads string representation of the dataset.

No prior normalization is required, therefore the results for the same quads may vary depending on the `Dataset`
implementation.

#### Returns

`string`

#### Inherited from

ILdoDataset.toString

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:188

___

### union

▸ **union**(`quads`): `Dataset`\<`Quad`, `Quad`\>

Returns a new `Dataset` that is a concatenation of this dataset and the quads given as an argument.

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

ILdoDataset.union

#### Defined in

node_modules/@rdfjs/types/dataset.d.ts:193

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

ILdoDataset.usingType

#### Defined in

[packages/ldo/src/types.ts:8](https://github.com/o-development/ldo/blob/c70613a/packages/ldo/src/types.ts#L8)
