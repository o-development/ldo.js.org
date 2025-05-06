# Interface: IConnectedLdoDataset\<Plugins\>

A ConnectedLdoDataset has all the functionality of a LdoDataset with the
added functionality of keeping track of fetched remote Resources.

It is recommended to use the [createConnectedLdoDataset](../functions/createConnectedLdoDataset.md) to
initialize this class.

**`Example`**

```typescript
import { createConnectedLdoDataset } from "@ldo/connected";
import { ProfileShapeType } from "./.ldo/profile.shapeTypes.ts"

// At least one plugin needs to be provided to a ConnectedLdoDataset. In this
// example we'll use both the Solid and NextGraph plugins.
import { solidConnectedPlugin } from "@ldo/connected-solid";
import { nextGraphConnectedPlugin } from "@ldo/connected-nextgraph";

// ...

const connectedLdoDataset = createConnectedLdoDataset([
  solidConnectedPlugin,
  nextGraphConnectedPlugin
]);

const profileDocument = connectedLdoDataset
  .getResource("https://example.com/profile");
await profileDocument.read();

const profile = connectedLdoDataset
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
```

## Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](ConnectedPlugin.md)[] |

## Hierarchy

- `LdoDataset`

  ↳ **`IConnectedLdoDataset`**

## Implemented by

- [`ConnectedLdoDataset`](../classes/ConnectedLdoDataset.md)
- [`ConnectedLdoTransactionDataset`](../classes/ConnectedLdoTransactionDataset.md)

## Properties

### dataset

• `Protected` **dataset**: `DatasetCore`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.dataset

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:3

___

### datasetCoreFactory

• `Protected` **datasetCoreFactory**: `DatasetCoreFactory`\<`Quad`, `Quad`, `DatasetCore`\<`Quad`, `Quad`\>\>

#### Inherited from

LdoDataset.datasetCoreFactory

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:4

___

### datasetFactory

• `Protected` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

#### Inherited from

LdoDataset.datasetFactory

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:8

___

### eventEmitter

• `Protected` **eventEmitter**: `EventEmitter`\<`DefaultEventMap`\>

#### Inherited from

LdoDataset.eventEmitter

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:9

___

### transactionDatasetFactory

• `Protected` **transactionDatasetFactory**: `ITransactionDatasetFactory`\<`Quad`\>

#### Inherited from

LdoDataset.transactionDatasetFactory

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:10

## Accessors

### size

• `get` **size**(): `number`

#### Returns

`number`

#### Inherited from

LdoDataset.size

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:26

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `Quad`, `undefined`\>

#### Returns

`Iterator`\<`Quad`, `Quad`, `undefined`\>

#### Inherited from

LdoDataset.[iterator]

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:30

___

### add

▸ **add**(`quad`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Inherited from

LdoDataset.add

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:17

___

### addAll

▸ **addAll**(`quads`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Quad`[] \| `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.addAll

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:14

___

### addListener

▸ **addListener**(`eventName`, `listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.addListener

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:20

___

### bulk

▸ **bulk**(`changed`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `changed` | `DatasetChanges`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.bulk

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:15

___

### contains

▸ **contains**(`other`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Inherited from

LdoDataset.contains

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:8

___

### createResource

▸ **createResource**\<`Name`, `Plugin`\>(`name`, `createResourceOptions?`): `Promise`\<`ReturnType`\<`Plugin`[``"createResource"``]\>\>

Generates a random uri and creates a resource.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `name` | `Name` | - |
| `createResourceOptions?` | `Plugin`[``"types"``][``"createResourceOptions"``] | Some set of options specific to the plugin you've selected. |

#### Returns

`Promise`\<`ReturnType`\<`Plugin`[``"createResource"``]\>\>

A created resource or an error

**`Example`**

```typescript
const profileDocument = await connectedLdoDataset
  .createResource("solid");
```

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:124](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L124)

___

### delete

▸ **delete**(`quad`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Inherited from

LdoDataset.delete

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:18

___

### deleteMatches

▸ **deleteMatches**(`subject?`, `predicate?`, `object?`, `graph?`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject?` | `Term` |
| `predicate?` | `Term` |
| `object?` | `Term` |
| `graph?` | `Term` |

#### Returns

`this`

#### Inherited from

LdoDataset.deleteMatches

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:16

___

### difference

▸ **difference**(`other`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `DatasetCore`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.difference

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:10

___

### emit

▸ **emit**(`eventName`, `changes`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `changes` | `DatasetChanges`\<`Quad`\> |

#### Returns

`boolean`

#### Inherited from

LdoDataset.emit

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:21

___

### equals

▸ **equals**(`other`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Inherited from

LdoDataset.equals

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:11

___

### eventNames

▸ **eventNames**(): `QuadMatch`[]

#### Returns

`QuadMatch`[]

#### Inherited from

LdoDataset.eventNames

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:22

___

### every

▸ **every**(`iteratee`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`boolean`

#### Inherited from

LdoDataset.every

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:12

___

### filter

▸ **filter**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.filter

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:13

___

### forEach

▸ **forEach**(`iteratee`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `void` |

#### Returns

`void`

#### Inherited from

LdoDataset.forEach

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:14

___

### forgetAllResources

▸ **forgetAllResources**(): `void`

Removes all resources from memory

#### Returns

`void`

**`Example`**

```typescript
connectedLdoDataset.forgetAllResources();
```

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:152](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L152)

___

### forgetResource

▸ **forgetResource**(`uri`): `boolean`

Removes a resource from local memory

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `string` | the URI of the resource to remove |

#### Returns

`boolean`

true if the resource was present before removal

**`Example`**

```typescript
connectedLdoDataset.forgetResource("https://example.com/resource.ttl");
```

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:142](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L142)

___

### getFetchedResources

▸ **getFetchedResources**(): `Plugins`[`number`][``"types"``][``"resource"``][]

Retireves a representation of all Resources that have been fetched.

#### Returns

`Plugins`[`number`][``"types"``][``"resource"``][]

a Resource array

**`Example`**

```typescript
const allResources = connectedLdoDataset.getFetchedResources();
```

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:107](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L107)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Inherited from

LdoDataset.getMaxListeners

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:23

___

### getResource

▸ **getResource**\<`Name`, `Plugin`, `UriType`\>(`uri`, `pluginName?`): [`GetResourceReturnType`](../types/GetResourceReturnType.md)\<`Plugin`, `UriType`\>

Retireves a representation of a Resource at the given URI. This resource
represents the current state of the resource: whether it is currently
fetched or in the process of fetching as well as some information about it.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |
| `UriType` | extends `string` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `UriType` | the URI of the resource |
| `pluginName?` | `Name` | optionally, force this function to choose a specific plugin to use rather than perform content negotiation. |

#### Returns

[`GetResourceReturnType`](../types/GetResourceReturnType.md)\<`Plugin`, `UriType`\>

a Resource

**`Example`**

```typescript
const profileDocument = connectedLdoDataset
  .getResource("https://example.com/profile");
```

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:73](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L73)

___

### getResources

▸ **getResources**(): `Plugins`[`number`][``"types"``][``"resource"``][]

Retireves a representation of all Resources referenced by this dataset
This does not necessarily mean that it's been fetched (use the
`getFetchedResources` method for that). It simply means that at one point
it was referenced.

#### Returns

`Plugins`[`number`][``"types"``][``"resource"``][]

a Resource array

**`Example`**

```typescript
const allResources = connectedLdoDataset.getResources();
```

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:95](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L95)

___

### has

▸ **has**(`quad`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`boolean`

#### Inherited from

LdoDataset.has

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:29

___

### import

▸ **import**(`stream`): `Promise`\<[`IConnectedLdoDataset`](IConnectedLdoDataset.md)\<`Plugins`\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `stream` | `Stream`\<`Quad`\> |

#### Returns

`Promise`\<[`IConnectedLdoDataset`](IConnectedLdoDataset.md)\<`Plugins`\>\>

#### Inherited from

LdoDataset.import

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:15

___

### intersection

▸ **intersection**(`other`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.intersection

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:16

___

### listenerCount

▸ **listenerCount**(`eventName`): `number`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`number`

#### Inherited from

LdoDataset.listenerCount

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:24

___

### listeners

▸ **listeners**(`eventName`): `nodeEventListener`\<`Quad`\>[]

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`nodeEventListener`\<`Quad`\>[]

#### Inherited from

LdoDataset.listeners

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:25

___

### map

▸ **map**(`iteratee`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `Quad` |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.map

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:17

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

LdoDataset.match

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:25

___

### off

▸ **off**(`eventName`, `listener`): `void`

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

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:26

___

### on

▸ **on**(`eventName`, `listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.on

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:27

___

### once

▸ **once**(`eventName`, `listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.once

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:28

___

### prependListener

▸ **prependListener**(`eventName`, `listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.prependListener

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:29

___

### prependOnceListener

▸ **prependOnceListener**(`eventName`, `listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.prependOnceListener

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:30

___

### rawListeners

▸ **rawListeners**(`eventName`): `nodeEventListener`\<`Quad`\>[]

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`nodeEventListener`\<`Quad`\>[]

#### Inherited from

LdoDataset.rawListeners

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:35

___

### reduce

▸ **reduce**\<`A`\>(`iteratee`, `initialValue?`): `A`

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

LdoDataset.reduce

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:18

___

### removeAllListeners

▸ **removeAllListeners**(`eventName`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`this`

#### Inherited from

LdoDataset.removeAllListeners

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:31

___

### removeListener

▸ **removeListener**(`eventName`, `listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.removeListener

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:32

___

### removeListenerFromAllEvents

▸ **removeListenerFromAllEvents**(`listener`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

`this`

#### Inherited from

LdoDataset.removeListenerFromAllEvents

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:33

___

### setContext

▸ **setContext**\<`Name`, `Plugin`\>(`name`, `context`): `any`

Sets conetext for a specific plugin

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `name` | `Name` | - |
| `context` | `Plugin`[``"types"``][``"context"``] | the context for this specific plugin |

#### Returns

`any`

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:160](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L160)

___

### setMaxListeners

▸ **setMaxListeners**(`n`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `n` | `number` |

#### Returns

`this`

#### Inherited from

LdoDataset.setMaxListeners

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:34

___

### some

▸ **some**(`iteratee`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `iteratee` | (`quad`: `Quad`, `dataset`: `this`) => `boolean` |

#### Returns

`boolean`

#### Inherited from

LdoDataset.some

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:19

___

### startTransaction

▸ **startTransaction**(): `LdoTransactionDataset`

#### Returns

`LdoTransactionDataset`

#### Inherited from

LdoDataset.startTransaction

#### Defined in

packages/ldo/dist/LdoDataset.d.ts:10

___

### toArray

▸ **toArray**(): `Quad`[]

#### Returns

`Quad`[]

#### Inherited from

LdoDataset.toArray

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:20

___

### toCanonical

▸ **toCanonical**(): `string`

#### Returns

`string`

#### Inherited from

LdoDataset.toCanonical

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:21

___

### toStream

▸ **toStream**(): `Stream`\<`Quad`\>

#### Returns

`Stream`\<`Quad`\>

#### Inherited from

LdoDataset.toStream

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:22

___

### toString

▸ **toString**(): `string`

#### Returns

`string`

#### Inherited from

LdoDataset.toString

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:23

___

### union

▸ **union**(`other`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoDataset.union

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:24

___

### usingType

▸ **usingType**\<`Type`\>(`shapeType`): [`IConnectedLdoBuilder`](IConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `shapeType` | `ShapeType`\<`Type`\> |

#### Returns

[`IConnectedLdoBuilder`](IConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

#### Overrides

LdoDataset.usingType

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:168](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L168)
