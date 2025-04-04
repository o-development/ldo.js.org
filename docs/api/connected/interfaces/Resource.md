# Interface: Resource\<UriType\>

A resource is an abstract representation for a group of data on a remote
platform. For example, "Solid" has resources that could be containers or
leafs.

## Type parameters

| Name | Type |
| :------ | :------ |
| `UriType` | extends `string` = `string` |

## Hierarchy

- [`ResourceEventEmitter`](../types/ResourceEventEmitter.md)

  ↳ **`Resource`**

## Implemented by

- [`InvalidIdentifierResource`](../classes/InvalidIdentifierResource.md)

## Properties

### isError

• `Readonly` **isError**: ``false``

Indicates that this is not an error

#### Defined in

[packages/connected/src/Resource.ts:27](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L27)

___

### status

• **status**: [`ConnectedResult`](ConnectedResult.md)

The most recent result from one of the resource methods.

#### Defined in

[packages/connected/src/Resource.ts:39](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L39)

___

### type

• `Readonly` **type**: `string`

The name of the resource. For example "NextGraphResource"

#### Defined in

[packages/connected/src/Resource.ts:35](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L35)

___

### uri

• `Readonly` **uri**: `UriType`

The uri of the resource

#### Defined in

[packages/connected/src/Resource.ts:31](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L31)

## Methods

### addListener

▸ **addListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.addListener

#### Defined in

node_modules/typed-emitter/index.d.ts:22

___

### emit

▸ **emit**\<`E`\>(`event`, `...args`): `boolean`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `...args` | `Parameters`\<\{ `notification`: () => `void` ; `update`: () => `void`  }[`E`]\> |

#### Returns

`boolean`

#### Inherited from

ResourceEventEmitter.emit

#### Defined in

node_modules/typed-emitter/index.d.ts:32

___

### eventNames

▸ **eventNames**(): (`string` \| `symbol`)[]

#### Returns

(`string` \| `symbol`)[]

#### Inherited from

ResourceEventEmitter.eventNames

#### Defined in

node_modules/typed-emitter/index.d.ts:34

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Inherited from

ResourceEventEmitter.getMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:39

___

### isAbsent

▸ **isAbsent**(): `undefined` \| `boolean`

Returns true if its confirmed that this resource doesn't exist. Returns
undefined if that is currently unknown.

#### Returns

`undefined` \| `boolean`

#### Defined in

[packages/connected/src/Resource.ts:65](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L65)

___

### isDoingInitialFetch

▸ **isDoingInitialFetch**(): `boolean`

Returns true if this resource is currently performing its first fetch

#### Returns

`boolean`

#### Defined in

[packages/connected/src/Resource.ts:55](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L55)

___

### isFetched

▸ **isFetched**(): `boolean`

Returns true if this resource has performed a fetch at least once

#### Returns

`boolean`

#### Defined in

[packages/connected/src/Resource.ts:47](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L47)

___

### isLoading

▸ **isLoading**(): `boolean`

Returns true if this resource is currently loading.

#### Returns

`boolean`

#### Defined in

[packages/connected/src/Resource.ts:43](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L43)

___

### isPresent

▸ **isPresent**(): `undefined` \| `boolean`

Returns true if this resource exists. Returns undefined if that is
currently unknown.

#### Returns

`undefined` \| `boolean`

#### Defined in

[packages/connected/src/Resource.ts:60](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L60)

___

### isSubscribedToNotifications

▸ **isSubscribedToNotifications**(): `boolean`

Returns true if this resource is currently subscribed to notifications.

#### Returns

`boolean`

#### Defined in

[packages/connected/src/Resource.ts:69](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L69)

___

### isUnfetched

▸ **isUnfetched**(): `boolean`

Returns true if this reosource has not performed a fetch at least once

#### Returns

`boolean`

#### Defined in

[packages/connected/src/Resource.ts:51](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L51)

___

### listenerCount

▸ **listenerCount**\<`E`\>(`event`): `number`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

`number`

#### Inherited from

ResourceEventEmitter.listenerCount

#### Defined in

node_modules/typed-emitter/index.d.ts:37

___

### listeners

▸ **listeners**\<`E`\>(`event`): \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

\{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Inherited from

ResourceEventEmitter.listeners

#### Defined in

node_modules/typed-emitter/index.d.ts:36

___

### off

▸ **off**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.off

#### Defined in

node_modules/typed-emitter/index.d.ts:28

___

### on

▸ **on**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.on

#### Defined in

node_modules/typed-emitter/index.d.ts:23

___

### once

▸ **once**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.once

#### Defined in

node_modules/typed-emitter/index.d.ts:24

___

### prependListener

▸ **prependListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.prependListener

#### Defined in

node_modules/typed-emitter/index.d.ts:25

___

### prependOnceListener

▸ **prependOnceListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.prependOnceListener

#### Defined in

node_modules/typed-emitter/index.d.ts:26

___

### rawListeners

▸ **rawListeners**\<`E`\>(`event`): \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

\{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Inherited from

ResourceEventEmitter.rawListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:35

___

### read

▸ **read**(): `Promise`\<[`ReadSuccess`](../classes/ReadSuccess.md)\<`any`\> \| [`ResourceError`](../classes/ResourceError.md)\<`any`\>\>

Fetches the resource.

#### Returns

`Promise`\<[`ReadSuccess`](../classes/ReadSuccess.md)\<`any`\> \| [`ResourceError`](../classes/ResourceError.md)\<`any`\>\>

#### Defined in

[packages/connected/src/Resource.ts:73](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L73)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<[`ReadSuccess`](../classes/ReadSuccess.md)\<`any`\> \| [`ResourceError`](../classes/ResourceError.md)\<`any`\>\>

Fetches the resource if it hasn't been fetched yet.

#### Returns

`Promise`\<[`ReadSuccess`](../classes/ReadSuccess.md)\<`any`\> \| [`ResourceError`](../classes/ResourceError.md)\<`any`\>\>

#### Defined in

[packages/connected/src/Resource.ts:77](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L77)

___

### removeAllListeners

▸ **removeAllListeners**\<`E`\>(`event?`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `E` |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.removeAllListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:29

___

### removeListener

▸ **removeListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.removeListener

#### Defined in

node_modules/typed-emitter/index.d.ts:30

___

### setMaxListeners

▸ **setMaxListeners**(`maxListeners`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `maxListeners` | `number` |

#### Returns

`this`

#### Inherited from

ResourceEventEmitter.setMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:40

___

### subscribeToNotifications

▸ **subscribeToNotifications**(`callbacks?`): `Promise`\<`string`\>

Begins a subscription to this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `callbacks?` | `Object` | optional set of callbacks to be called when this resource is updated |
| `callbacks.onNotification` | (`message`: `any`) => `void` | - |
| `callbacks.onNotificationError` | (`err`: `Error`) => `void` | - |

#### Returns

`Promise`\<`string`\>

#### Defined in

[packages/connected/src/Resource.ts:92](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L92)

___

### unsubscribeFromAllNotifications

▸ **unsubscribeFromAllNotifications**(): `Promise`\<`void`\>

Unsubscribes from all notifications.

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/Resource.ts:104](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L104)

___

### unsubscribeFromNotifications

▸ **unsubscribeFromNotifications**(`subscriptionId`): `Promise`\<`void`\>

Unsubscribes from notifications on this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `subscriptionId` | `string` | the Id of the subscription to unsubscribe |

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/Resource.ts:100](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L100)

___

### update

▸ **update**(`datasetChanges`): `Promise`\<[`ResourceError`](../classes/ResourceError.md)\<`any`\> \| [`UpdateSuccess`](../classes/UpdateSuccess.md)\<`any`\> \| [`IgnoredInvalidUpdateSuccess`](../classes/IgnoredInvalidUpdateSuccess.md)\<`any`\>\>

Applies updates to this resource.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `datasetChanges` | `DatasetChanges`\<`BaseQuad`\> | A list of changes to data |

#### Returns

`Promise`\<[`ResourceError`](../classes/ResourceError.md)\<`any`\> \| [`UpdateSuccess`](../classes/UpdateSuccess.md)\<`any`\> \| [`IgnoredInvalidUpdateSuccess`](../classes/IgnoredInvalidUpdateSuccess.md)\<`any`\>\>

#### Defined in

[packages/connected/src/Resource.ts:82](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/Resource.ts#L82)
