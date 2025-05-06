# Class: ConnectedLdoTransactionDataset\<Plugins\>

A ConnectedLdoTransactionDataset has all the functionality of a
ConnectedLdoDataset and represents a transaction to the parent
ConnectedLdoDataset.

It is recommended to use the `startTransaction` method on a SolidLdoDataset
to initialize this class

**`Example`**

```typescript
import { createConnectedLdoDataset } from "@ldo/connected";
import { ProfileShapeType } from "./.ldo/profile.shapeTypes.ts"
import { solidConnectedPlugin } from "connected-solid";

// ...

const connectedLdoDataset = createConnectedLdoDataset([
  solidConnectedPlugin
]);

const profileDocument = connectedLdoDataset
  .getResource("https://example.com/profile");
await profileDocument.read();

const transaction = connectedLdoDataset.startTransaction();

const profile = transaction
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
profile.name = "Some Name";
const result = await transaction.commitToRemote();
if (result.isError) {
  // handle error
}
```

## Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)[] |

## Hierarchy

- `LdoTransactionDataset`

  ↳ **`ConnectedLdoTransactionDataset`**

## Implements

- [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\>

## Constructors

### constructor

• **new ConnectedLdoTransactionDataset**\<`Plugins`\>(`parentDataset`, `context`, `datasetFactory`, `transactionDatasetFactory`): [`ConnectedLdoTransactionDataset`](ConnectedLdoTransactionDataset.md)\<`Plugins`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `parentDataset` | [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\> | - |
| `context` | [`ConnectedContext`](../types/ConnectedContext.md)\<`Plugins`\> | SolidLdoDatasetContext |
| `datasetFactory` | `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\> | An optional dataset factory |
| `transactionDatasetFactory` | `ITransactionDatasetFactory`\<`Quad`\> | A factory for creating transaction datasets |

#### Returns

[`ConnectedLdoTransactionDataset`](ConnectedLdoTransactionDataset.md)\<`Plugins`\>

#### Overrides

LdoTransactionDataset.constructor

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:86](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L86)

## Properties

### context

• **context**: [`ConnectedContext`](../types/ConnectedContext.md)\<`Plugins`\>

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:71](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L71)

___

### dataset

• `Protected` **dataset**: `DatasetCore`\<`Quad`, `Quad`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[dataset](../interfaces/IConnectedLdoDataset.md#dataset)

#### Inherited from

LdoTransactionDataset.dataset

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:3

___

### datasetCoreFactory

• `Protected` **datasetCoreFactory**: `DatasetCoreFactory`\<`Quad`, `Quad`, `DatasetCore`\<`Quad`, `Quad`\>\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[datasetCoreFactory](../interfaces/IConnectedLdoDataset.md#datasetcorefactory)

#### Inherited from

LdoTransactionDataset.datasetCoreFactory

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:4

___

### datasetFactory

• `Protected` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[datasetFactory](../interfaces/IConnectedLdoDataset.md#datasetfactory)

#### Inherited from

LdoTransactionDataset.datasetFactory

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:8

___

### eventEmitter

• `Protected` **eventEmitter**: `EventEmitter`\<`DefaultEventMap`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[eventEmitter](../interfaces/IConnectedLdoDataset.md#eventemitter)

#### Inherited from

LdoTransactionDataset.eventEmitter

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:9

___

### parentDataset

• `Readonly` **parentDataset**: `Dataset`\<`Quad`, `Quad`\>

#### Inherited from

LdoTransactionDataset.parentDataset

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:6

___

### resourceMap

• `Protected` **resourceMap**: `Map`\<`string`, `Plugins`[`number`][``"types"``][``"resource"``]\>

Serves no purpose

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:77](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L77)

___

### transactionDatasetFactory

• `Protected` **transactionDatasetFactory**: `ITransactionDatasetFactory`\<`Quad`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[transactionDatasetFactory](../interfaces/IConnectedLdoDataset.md#transactiondatasetfactory)

#### Inherited from

LdoTransactionDataset.transactionDatasetFactory

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:10

## Accessors

### size

• `get` **size**(): `number`

#### Returns

`number`

#### Implementation of

IConnectedLdoDataset.size

#### Inherited from

LdoTransactionDataset.size

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:14

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `any`, `undefined`\>

#### Returns

`Iterator`\<`Quad`, `any`, `undefined`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[[iterator]](../interfaces/IConnectedLdoDataset.md#[iterator])

#### Inherited from

LdoTransactionDataset.[iterator]

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:18

___

### add

▸ **add**(`quad`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[add](../interfaces/IConnectedLdoDataset.md#add)

#### Inherited from

LdoTransactionDataset.add

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:15

___

### addAll

▸ **addAll**(`quads`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quads` | `Quad`[] \| `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`this`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[addAll](../interfaces/IConnectedLdoDataset.md#addall)

#### Inherited from

LdoTransactionDataset.addAll

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:10

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[addListener](../interfaces/IConnectedLdoDataset.md#addlistener)

#### Inherited from

LdoTransactionDataset.addListener

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:20

___

### bulk

▸ **bulk**(`changes`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> |

#### Returns

`this`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[bulk](../interfaces/IConnectedLdoDataset.md#bulk)

#### Inherited from

LdoTransactionDataset.bulk

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:11

___

### commit

▸ **commit**(): `void`

#### Returns

`void`

#### Inherited from

LdoTransactionDataset.commit

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:22

___

### commitToRemote

▸ **commitToRemote**(): `Promise`\<[`AggregateSuccess`](AggregateSuccess.md)\<[`UpdateDefaultGraphSuccess`](UpdateDefaultGraphSuccess.md) \| `Extract`\<`Awaited`\<`ReturnType`\<...[...][``"types"``][``"resource"``][``"update"``]\>\>, \{ `isError`: ``false``  }\> \| [`IgnoredInvalidUpdateSuccess`](IgnoredInvalidUpdateSuccess.md)\<`Plugins`[`number`][``"types"``][``"resource"``]\>\> \| [`AggregateError`](AggregateError.md)\<`Extract`\<`Awaited`\<`ReturnType`\<`Plugins`[`number`][``"types"``][``"resource"``][``"update"``]\>\>, \{ `isError`: ``true``  }\>\>\>

Commits all changes made in this transaction to the remote connected
platforms as well as the parent dataset.

#### Returns

`Promise`\<[`AggregateSuccess`](AggregateSuccess.md)\<[`UpdateDefaultGraphSuccess`](UpdateDefaultGraphSuccess.md) \| `Extract`\<`Awaited`\<`ReturnType`\<...[...][``"types"``][``"resource"``][``"update"``]\>\>, \{ `isError`: ``false``  }\> \| [`IgnoredInvalidUpdateSuccess`](IgnoredInvalidUpdateSuccess.md)\<`Plugins`[`number`][``"types"``][``"resource"``]\>\> \| [`AggregateError`](AggregateError.md)\<`Extract`\<`Awaited`\<`ReturnType`\<`Plugins`[`number`][``"types"``][``"resource"``][``"update"``]\>\>, \{ `isError`: ``true``  }\>\>\>

A success or failure

**`Example`**

```typescript
import { createConnectedLdoDataset } from "@ldo/connected";
import { ProfileShapeType } from "./.ldo/profile.shapeTypes.ts"
import { solidConnectedPlugin } from "connected-solid";

// ...

const connectedLdoDataset = createConnectedLdoDataset([solidConnectedPlugin]);

const profileDocument = connectedLdoDataset
  .getResource("https://example.com/profile");
await profileDocument.read();

const transaction = connectedLdoDataset.startTransaction();

const profile = transaction
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
profile.name = "Some Name";
const result = await transaction.commitToRemote();
if (result.isError) {
  // handle error
}
```

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:174](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L174)

___

### contains

▸ **contains**(`other`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `Dataset`\<`Quad`, `Quad`\> |

#### Returns

`boolean`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[contains](../interfaces/IConnectedLdoDataset.md#contains)

#### Inherited from

LdoTransactionDataset.contains

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:8

___

### createResource

▸ **createResource**\<`Name`, `Plugin`\>(`name`): `Promise`\<`ReturnType`\<`Plugin`[``"createResource"``]\>\>

Generates a random uri and creates a resource.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `name` | `Name` |

#### Returns

`Promise`\<`ReturnType`\<`Plugin`[``"createResource"``]\>\>

A created resource or an error

**`Example`**

```typescript
const profileDocument = await connectedLdoDataset
  .createResource("solid");
```

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[createResource](../interfaces/IConnectedLdoDataset.md#createresource)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:112](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L112)

___

### delete

▸ **delete**(`quad`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`this`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[delete](../interfaces/IConnectedLdoDataset.md#delete)

#### Inherited from

LdoTransactionDataset.delete

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:16

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[deleteMatches](../interfaces/IConnectedLdoDataset.md#deletematches)

#### Inherited from

LdoTransactionDataset.deleteMatches

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:12

___

### difference

▸ **difference**(`other`): `Dataset`\<`Quad`, `Quad`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `other` | `DatasetCore`\<`Quad`, `Quad`\> |

#### Returns

`Dataset`\<`Quad`, `Quad`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[difference](../interfaces/IConnectedLdoDataset.md#difference)

#### Inherited from

LdoTransactionDataset.difference

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[emit](../interfaces/IConnectedLdoDataset.md#emit)

#### Inherited from

LdoTransactionDataset.emit

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[equals](../interfaces/IConnectedLdoDataset.md#equals)

#### Inherited from

LdoTransactionDataset.equals

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:11

___

### eventNames

▸ **eventNames**(): `QuadMatch`[]

#### Returns

`QuadMatch`[]

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[eventNames](../interfaces/IConnectedLdoDataset.md#eventnames)

#### Inherited from

LdoTransactionDataset.eventNames

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[every](../interfaces/IConnectedLdoDataset.md#every)

#### Inherited from

LdoTransactionDataset.every

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[filter](../interfaces/IConnectedLdoDataset.md#filter)

#### Inherited from

LdoTransactionDataset.filter

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[forEach](../interfaces/IConnectedLdoDataset.md#foreach)

#### Inherited from

LdoTransactionDataset.forEach

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[forgetAllResources](../interfaces/IConnectedLdoDataset.md#forgetallresources)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:129](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L129)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[forgetResource](../interfaces/IConnectedLdoDataset.md#forgetresource)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:126](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L126)

___

### getChanges

▸ **getChanges**(): `DatasetChanges`\<`Quad`\>

#### Returns

`DatasetChanges`\<`Quad`\>

#### Inherited from

LdoTransactionDataset.getChanges

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:24

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getFetchedResources](../interfaces/IConnectedLdoDataset.md#getfetchedresources)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:108](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L108)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getMaxListeners](../interfaces/IConnectedLdoDataset.md#getmaxlisteners)

#### Inherited from

LdoTransactionDataset.getMaxListeners

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
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |
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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getResource](../interfaces/IConnectedLdoDataset.md#getresource)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:96](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L96)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getResources](../interfaces/IConnectedLdoDataset.md#getresources)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:104](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L104)

___

### has

▸ **has**(`quad`): `boolean`

#### Parameters

| Name | Type |
| :------ | :------ |
| `quad` | `Quad` |

#### Returns

`boolean`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[has](../interfaces/IConnectedLdoDataset.md#has)

#### Inherited from

LdoTransactionDataset.has

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:17

___

### import

▸ **import**(`stream`): `Promise`\<[`ConnectedLdoTransactionDataset`](ConnectedLdoTransactionDataset.md)\<`Plugins`\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `stream` | `Stream`\<`Quad`\> |

#### Returns

`Promise`\<[`ConnectedLdoTransactionDataset`](ConnectedLdoTransactionDataset.md)\<`Plugins`\>\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[import](../interfaces/IConnectedLdoDataset.md#import)

#### Inherited from

LdoTransactionDataset.import

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[intersection](../interfaces/IConnectedLdoDataset.md#intersection)

#### Inherited from

LdoTransactionDataset.intersection

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[listenerCount](../interfaces/IConnectedLdoDataset.md#listenercount)

#### Inherited from

LdoTransactionDataset.listenerCount

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[listeners](../interfaces/IConnectedLdoDataset.md#listeners)

#### Inherited from

LdoTransactionDataset.listeners

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[map](../interfaces/IConnectedLdoDataset.md#map)

#### Inherited from

LdoTransactionDataset.map

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[match](../interfaces/IConnectedLdoDataset.md#match)

#### Inherited from

LdoTransactionDataset.match

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:13

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[off](../interfaces/IConnectedLdoDataset.md#off)

#### Inherited from

LdoTransactionDataset.off

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[on](../interfaces/IConnectedLdoDataset.md#on)

#### Inherited from

LdoTransactionDataset.on

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[once](../interfaces/IConnectedLdoDataset.md#once)

#### Inherited from

LdoTransactionDataset.once

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[prependListener](../interfaces/IConnectedLdoDataset.md#prependlistener)

#### Inherited from

LdoTransactionDataset.prependListener

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[prependOnceListener](../interfaces/IConnectedLdoDataset.md#prependoncelistener)

#### Inherited from

LdoTransactionDataset.prependOnceListener

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[rawListeners](../interfaces/IConnectedLdoDataset.md#rawlisteners)

#### Inherited from

LdoTransactionDataset.rawListeners

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[reduce](../interfaces/IConnectedLdoDataset.md#reduce)

#### Inherited from

LdoTransactionDataset.reduce

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[removeAllListeners](../interfaces/IConnectedLdoDataset.md#removealllisteners)

#### Inherited from

LdoTransactionDataset.removeAllListeners

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[removeListener](../interfaces/IConnectedLdoDataset.md#removelistener)

#### Inherited from

LdoTransactionDataset.removeListener

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[removeListenerFromAllEvents](../interfaces/IConnectedLdoDataset.md#removelistenerfromallevents)

#### Inherited from

LdoTransactionDataset.removeListenerFromAllEvents

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:33

___

### rollback

▸ **rollback**(): `void`

#### Returns

`void`

#### Inherited from

LdoTransactionDataset.rollback

#### Defined in

packages/subscribable-dataset/dist/TransactionDataset.d.ts:23

___

### setContext

▸ **setContext**\<`Name`, `Plugin`\>(`name`, `context`): `void`

Sets conetext for a specific plugin

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `name` | `Name` | - |
| `context` | `Plugin`[``"types"``][``"context"``] | the context for this specific plugin |

#### Returns

`void`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[setContext](../interfaces/IConnectedLdoDataset.md#setcontext)

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:119](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L119)

___

### setMaxListeners

▸ **setMaxListeners**(`n`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `n` | `number` |

#### Returns

`this`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[setMaxListeners](../interfaces/IConnectedLdoDataset.md#setmaxlisteners)

#### Inherited from

LdoTransactionDataset.setMaxListeners

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[some](../interfaces/IConnectedLdoDataset.md#some)

#### Inherited from

LdoTransactionDataset.some

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:19

___

### startTransaction

▸ **startTransaction**(): [`ConnectedLdoTransactionDataset`](ConnectedLdoTransactionDataset.md)\<`Plugins`\>

#### Returns

[`ConnectedLdoTransactionDataset`](ConnectedLdoTransactionDataset.md)\<`Plugins`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[startTransaction](../interfaces/IConnectedLdoDataset.md#starttransaction)

#### Overrides

LdoTransactionDataset.startTransaction

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:133](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L133)

___

### toArray

▸ **toArray**(): `Quad`[]

#### Returns

`Quad`[]

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[toArray](../interfaces/IConnectedLdoDataset.md#toarray)

#### Inherited from

LdoTransactionDataset.toArray

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:20

___

### toCanonical

▸ **toCanonical**(): `string`

#### Returns

`string`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[toCanonical](../interfaces/IConnectedLdoDataset.md#tocanonical)

#### Inherited from

LdoTransactionDataset.toCanonical

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:21

___

### toStream

▸ **toStream**(): `Stream`\<`Quad`\>

#### Returns

`Stream`\<`Quad`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[toStream](../interfaces/IConnectedLdoDataset.md#tostream)

#### Inherited from

LdoTransactionDataset.toStream

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:22

___

### toString

▸ **toString**(): `string`

#### Returns

`string`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[toString](../interfaces/IConnectedLdoDataset.md#tostring)

#### Inherited from

LdoTransactionDataset.toString

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[union](../interfaces/IConnectedLdoDataset.md#union)

#### Inherited from

LdoTransactionDataset.union

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:24

___

### usingType

▸ **usingType**\<`Type`\>(`shapeType`): [`ConnectedLdoBuilder`](ConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `shapeType` | `ShapeType`\<`Type`\> |

#### Returns

[`ConnectedLdoBuilder`](ConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[usingType](../interfaces/IConnectedLdoDataset.md#usingtype)

#### Overrides

LdoTransactionDataset.usingType

#### Defined in

[packages/connected/src/ConnectedLdoTransactionDataset.ts:240](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoTransactionDataset.ts#L240)
