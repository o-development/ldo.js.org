# Class: ConnectedLdoDataset\<Plugins\>

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
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`\>[] |

## Hierarchy

- `LdoDataset`

  ↳ **`ConnectedLdoDataset`**

## Implements

- [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\>

## Constructors

### constructor

• **new ConnectedLdoDataset**\<`Plugins`\>(`plugins`, `datasetFactory`, `transactionDatasetFactory`, `initialDataset?`): [`ConnectedLdoDataset`](ConnectedLdoDataset.md)\<`Plugins`\>

It is recommended to use the `createConnectedLdoDataset` function to
instantiate a ConnectedLdoDataset.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `plugins` | `Plugins` | An array of plugins for each platform to connect to |
| `datasetFactory` | `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\> | Creates Datasets |
| `transactionDatasetFactory` | `ITransactionDatasetFactory`\<`Quad`\> | Creates Transaction Datasets |
| `initialDataset?` | `Dataset`\<`Quad`, `Quad`\> | Initial quads |

#### Returns

[`ConnectedLdoDataset`](ConnectedLdoDataset.md)\<`Plugins`\>

#### Overrides

LdoDataset.constructor

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:86](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L86)

## Properties

### context

• `Protected` **context**: [`ConnectedContext`](../types/ConnectedContext.md)\<`Plugins`\>

Context for each plugin (usually utilities for authentication)

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:75](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L75)

___

### dataset

• `Protected` **dataset**: `DatasetCore`\<`Quad`, `Quad`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[dataset](../interfaces/IConnectedLdoDataset.md#dataset)

#### Inherited from

LdoDataset.dataset

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:3

___

### datasetCoreFactory

• `Protected` **datasetCoreFactory**: `DatasetCoreFactory`\<`Quad`, `Quad`, `DatasetCore`\<`Quad`, `Quad`\>\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[datasetCoreFactory](../interfaces/IConnectedLdoDataset.md#datasetcorefactory)

#### Inherited from

LdoDataset.datasetCoreFactory

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:4

___

### datasetFactory

• `Protected` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[datasetFactory](../interfaces/IConnectedLdoDataset.md#datasetfactory)

#### Inherited from

LdoDataset.datasetFactory

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:8

___

### eventEmitter

• `Protected` **eventEmitter**: `EventEmitter`\<`DefaultEventMap`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[eventEmitter](../interfaces/IConnectedLdoDataset.md#eventemitter)

#### Inherited from

LdoDataset.eventEmitter

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:9

___

### plugins

• `Private` **plugins**: `Plugins`

A list of plugins used by this dataset

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:62](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L62)

___

### resourceMap

• `Protected` **resourceMap**: `Map`\<`string`, `Plugins`[`number`][``"types"``][``"resource"``]\>

A mapping between a resource URI and a resource

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:68](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L68)

___

### transactionDatasetFactory

• `Protected` **transactionDatasetFactory**: `ITransactionDatasetFactory`\<`Quad`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[transactionDatasetFactory](../interfaces/IConnectedLdoDataset.md#transactiondatasetfactory)

#### Inherited from

LdoDataset.transactionDatasetFactory

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

LdoDataset.size

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:26

## Methods

### [iterator]

▸ **[iterator]**(): `Iterator`\<`Quad`, `Quad`, `undefined`\>

#### Returns

`Iterator`\<`Quad`, `Quad`, `undefined`\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[[iterator]](../interfaces/IConnectedLdoDataset.md#[iterator])

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[add](../interfaces/IConnectedLdoDataset.md#add)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[addAll](../interfaces/IConnectedLdoDataset.md#addall)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[addListener](../interfaces/IConnectedLdoDataset.md#addlistener)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[bulk](../interfaces/IConnectedLdoDataset.md#bulk)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[contains](../interfaces/IConnectedLdoDataset.md#contains)

#### Inherited from

LdoDataset.contains

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:8

___

### createData

▸ **createData**\<`Type`\>(`shapeType`, `subject`, `resource`, `...additionalResources`): `Type`

Shorthand for connectedLdoDataset
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
| `resource` | `Plugins`[`number`][``"types"``][``"resource"``] | - |
| `...additionalResources` | `Plugins`[`number`][``"types"``][``"resource"``][] | - |

#### Returns

`Type`

**`Example`**

```typescript
import { ProfielShapeType } from "./.ldo/foafProfile.shapeType.ts"

const resource = connectedLdoDataset
  .getResource("https://example.com/profile");
const profile = connectedLdoDataset.createData(
  ProfileShapeType,
  "https://example.com/profile#me",
  resource
);
```

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:261](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L261)

___

### createResource

▸ **createResource**\<`Name`, `Plugin`\>(`pluginName`, `createResourceOptions?`): `Promise`\<`ReturnType`\<`Plugin`[``"createResource"``]\>\>

Generates a random uri and creates a resource.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `pluginName` | `Name` | A string name for the platform you'd like to create the resource on. |
| `createResourceOptions?` | `Plugin`[``"types"``][``"createResourceOptions"``] | Some set of options specific to the plugin you've selected. |

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

[packages/connected/src/ConnectedLdoDataset.ts:188](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L188)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[deleteMatches](../interfaces/IConnectedLdoDataset.md#deletematches)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[difference](../interfaces/IConnectedLdoDataset.md#difference)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[emit](../interfaces/IConnectedLdoDataset.md#emit)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[equals](../interfaces/IConnectedLdoDataset.md#equals)

#### Inherited from

LdoDataset.equals

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[every](../interfaces/IConnectedLdoDataset.md#every)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[filter](../interfaces/IConnectedLdoDataset.md#filter)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[forEach](../interfaces/IConnectedLdoDataset.md#foreach)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[forgetAllResources](../interfaces/IConnectedLdoDataset.md#forgetallresources)

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:235](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L235)

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

[packages/connected/src/ConnectedLdoDataset.ts:221](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L221)

___

### getFetchedResources

▸ **getFetchedResources**(): [`GetResourceReturnType`](../types/GetResourceReturnType.md)\<`Plugins`[`number`], `string`\>[]

Retireves a representation of all Resources that have been fetched.

#### Returns

[`GetResourceReturnType`](../types/GetResourceReturnType.md)\<`Plugins`[`number`], `string`\>[]

a Resource array

**`Example`**

```typescript
const allResources = connectedLdoDataset.getFetchedResources();
```

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getFetchedResources](../interfaces/IConnectedLdoDataset.md#getfetchedresources)

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:169](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L169)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getMaxListeners](../interfaces/IConnectedLdoDataset.md#getmaxlisteners)

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

[packages/connected/src/ConnectedLdoDataset.ts:147](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L147)

___

### getResources

▸ **getResources**(): [`GetResourceReturnType`](../types/GetResourceReturnType.md)\<`Plugins`[`number`], `string`\>[]

Retireves a representation of all Resources referenced by this dataset
This does not necessarily mean that it's been fetched (use the
`getFetchedResources` method for that). It simply means that at one point
it was referenced.

#### Returns

[`GetResourceReturnType`](../types/GetResourceReturnType.md)\<`Plugins`[`number`], `string`\>[]

a Resource array

**`Example`**

```typescript
const allResources = connectedLdoDataset.getResources();
```

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[getResources](../interfaces/IConnectedLdoDataset.md#getresources)

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:165](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L165)

___

### getValidPlugin

▸ **getValidPlugin**(`uri`, `pluginName?`): `undefined` \| `Plugins`[`number`]

A helper function to return a plugin based in the plugin name and uri.

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `pluginName?` | `string` |

#### Returns

`undefined` \| `Plugins`[`number`]

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:110](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L110)

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

LdoDataset.has

#### Defined in

packages/dataset/dist/ExtendedDataset.d.ts:29

___

### import

▸ **import**(`stream`): `Promise`\<[`ConnectedLdoDataset`](ConnectedLdoDataset.md)\<`Plugins`\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `stream` | `Stream`\<`Quad`\> |

#### Returns

`Promise`\<[`ConnectedLdoDataset`](ConnectedLdoDataset.md)\<`Plugins`\>\>

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[import](../interfaces/IConnectedLdoDataset.md#import)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[intersection](../interfaces/IConnectedLdoDataset.md#intersection)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[listenerCount](../interfaces/IConnectedLdoDataset.md#listenercount)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[listeners](../interfaces/IConnectedLdoDataset.md#listeners)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[map](../interfaces/IConnectedLdoDataset.md#map)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[match](../interfaces/IConnectedLdoDataset.md#match)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[off](../interfaces/IConnectedLdoDataset.md#off)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[on](../interfaces/IConnectedLdoDataset.md#on)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[once](../interfaces/IConnectedLdoDataset.md#once)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[prependListener](../interfaces/IConnectedLdoDataset.md#prependlistener)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[prependOnceListener](../interfaces/IConnectedLdoDataset.md#prependoncelistener)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[rawListeners](../interfaces/IConnectedLdoDataset.md#rawlisteners)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[reduce](../interfaces/IConnectedLdoDataset.md#reduce)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[removeAllListeners](../interfaces/IConnectedLdoDataset.md#removealllisteners)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[removeListener](../interfaces/IConnectedLdoDataset.md#removelistener)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[removeListenerFromAllEvents](../interfaces/IConnectedLdoDataset.md#removelistenerfromallevents)

#### Inherited from

LdoDataset.removeListenerFromAllEvents

#### Defined in

packages/subscribable-dataset/dist/SubscribableDataset.d.ts:33

___

### setContext

▸ **setContext**\<`Name`, `Plugin`\>(`pluginName`, `context`): `void`

Sets conetext for a specific plugin

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `any` |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `pluginName` | `Name` | the name of the plugin |
| `context` | `Plugin`[``"types"``][``"context"``] | the context for this specific plugin |

#### Returns

`void`

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[setContext](../interfaces/IConnectedLdoDataset.md#setcontext)

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:281](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L281)

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[some](../interfaces/IConnectedLdoDataset.md#some)

#### Inherited from

LdoDataset.some

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

LdoDataset.startTransaction

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:297](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L297)

___

### toArray

▸ **toArray**(): `Quad`[]

#### Returns

`Quad`[]

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[toArray](../interfaces/IConnectedLdoDataset.md#toarray)

#### Inherited from

LdoDataset.toArray

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

LdoDataset.toCanonical

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

LdoDataset.toStream

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

#### Implementation of

[IConnectedLdoDataset](../interfaces/IConnectedLdoDataset.md).[union](../interfaces/IConnectedLdoDataset.md#union)

#### Inherited from

LdoDataset.union

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

LdoDataset.usingType

#### Defined in

[packages/connected/src/ConnectedLdoDataset.ts:290](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoDataset.ts#L290)
