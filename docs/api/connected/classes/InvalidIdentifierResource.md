# Class: InvalidIdentifierResource

A resource that represents a URI that does not have a valid URI given the
plugins available to the ConnectedLdoDataset.

## Hierarchy

- `TypedEventEmitter`\<\{ `notification`: () => `void` ; `update`: () => `void`  }, `this`\>

  ↳ **`InvalidIdentifierResource`**

## Implements

- [`Resource`](../interfaces/Resource.md)

## Constructors

### constructor

• **new InvalidIdentifierResource**(`uri`): [`InvalidIdentifierResource`](InvalidIdentifierResource.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |

#### Returns

[`InvalidIdentifierResource`](InvalidIdentifierResource.md)

#### Overrides

(EventEmitter as new () &#x3D;\&gt; ResourceEventEmitter).constructor

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:18](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L18)

## Properties

### isError

• `Readonly` **isError**: ``false``

Indicates that this is not an error

#### Implementation of

[Resource](../interfaces/Resource.md).[isError](../interfaces/Resource.md#iserror)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:16](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L16)

___

### status

• **status**: [`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>

The most recent result from one of the resource methods.

#### Implementation of

[Resource](../interfaces/Resource.md).[status](../interfaces/Resource.md#status)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:15](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L15)

___

### type

• `Readonly` **type**: ``"InvalidIdentifierResouce"``

The name of the resource. For example "NextGraphResource"

#### Implementation of

[Resource](../interfaces/Resource.md).[type](../interfaces/Resource.md#type)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:14](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L14)

___

### uri

• `Readonly` **uri**: `string`

The uri of the resource

#### Implementation of

[Resource](../interfaces/Resource.md).[uri](../interfaces/Resource.md#uri)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:13](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L13)

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

#### Implementation of

[Resource](../interfaces/Resource.md).[addListener](../interfaces/Resource.md#addlistener)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).addListener

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

#### Implementation of

[Resource](../interfaces/Resource.md).[emit](../interfaces/Resource.md#emit)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).emit

#### Defined in

node_modules/typed-emitter/index.d.ts:32

___

### eventNames

▸ **eventNames**(): (`string` \| `symbol`)[]

#### Returns

(`string` \| `symbol`)[]

#### Implementation of

[Resource](../interfaces/Resource.md).[eventNames](../interfaces/Resource.md#eventnames)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).eventNames

#### Defined in

node_modules/typed-emitter/index.d.ts:34

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Implementation of

[Resource](../interfaces/Resource.md).[getMaxListeners](../interfaces/Resource.md#getmaxlisteners)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).getMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:39

___

### isAbsent

▸ **isAbsent**(): `boolean`

Returns true if its confirmed that this resource doesn't exist. Returns
undefined if that is currently unknown.

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isAbsent](../interfaces/Resource.md#isabsent)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:39](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L39)

___

### isDoingInitialFetch

▸ **isDoingInitialFetch**(): `boolean`

Returns true if this resource is currently performing its first fetch

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isDoingInitialFetch](../interfaces/Resource.md#isdoinginitialfetch)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:33](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L33)

___

### isFetched

▸ **isFetched**(): `boolean`

Returns true if this resource has performed a fetch at least once

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isFetched](../interfaces/Resource.md#isfetched)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:27](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L27)

___

### isLoading

▸ **isLoading**(): `boolean`

Returns true if this resource is currently loading.

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isLoading](../interfaces/Resource.md#isloading)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:24](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L24)

___

### isPresent

▸ **isPresent**(): `boolean`

Returns true if this resource exists. Returns undefined if that is
currently unknown.

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isPresent](../interfaces/Resource.md#ispresent)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:36](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L36)

___

### isSubscribedToNotifications

▸ **isSubscribedToNotifications**(): `boolean`

Returns true if this resource is currently subscribed to notifications.

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isSubscribedToNotifications](../interfaces/Resource.md#issubscribedtonotifications)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:42](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L42)

___

### isUnfetched

▸ **isUnfetched**(): `boolean`

Returns true if this reosource has not performed a fetch at least once

#### Returns

`boolean`

#### Implementation of

[Resource](../interfaces/Resource.md).[isUnfetched](../interfaces/Resource.md#isunfetched)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:30](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L30)

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

#### Implementation of

[Resource](../interfaces/Resource.md).[listenerCount](../interfaces/Resource.md#listenercount)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).listenerCount

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

#### Implementation of

[Resource](../interfaces/Resource.md).[listeners](../interfaces/Resource.md#listeners)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).listeners

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

#### Implementation of

[Resource](../interfaces/Resource.md).[off](../interfaces/Resource.md#off)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).off

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

#### Implementation of

[Resource](../interfaces/Resource.md).[on](../interfaces/Resource.md#on)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).on

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

#### Implementation of

[Resource](../interfaces/Resource.md).[once](../interfaces/Resource.md#once)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).once

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

#### Implementation of

[Resource](../interfaces/Resource.md).[prependListener](../interfaces/Resource.md#prependlistener)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).prependListener

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

#### Implementation of

[Resource](../interfaces/Resource.md).[prependOnceListener](../interfaces/Resource.md#prependoncelistener)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).prependOnceListener

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

#### Implementation of

[Resource](../interfaces/Resource.md).[rawListeners](../interfaces/Resource.md#rawlisteners)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).rawListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:35

___

### read

▸ **read**(): `Promise`\<[`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>\>

Fetches the resource.

#### Returns

`Promise`\<[`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>\>

#### Implementation of

[Resource](../interfaces/Resource.md).[read](../interfaces/Resource.md#read)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:45](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L45)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<[`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>\>

Fetches the resource if it hasn't been fetched yet.

#### Returns

`Promise`\<[`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>\>

#### Implementation of

[Resource](../interfaces/Resource.md).[readIfUnfetched](../interfaces/Resource.md#readifunfetched)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:48](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L48)

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

#### Implementation of

[Resource](../interfaces/Resource.md).[removeAllListeners](../interfaces/Resource.md#removealllisteners)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).removeAllListeners

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

#### Implementation of

[Resource](../interfaces/Resource.md).[removeListener](../interfaces/Resource.md#removelistener)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).removeListener

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

#### Implementation of

[Resource](../interfaces/Resource.md).[setMaxListeners](../interfaces/Resource.md#setmaxlisteners)

#### Inherited from

(EventEmitter as new () =\> ResourceEventEmitter).setMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:40

___

### subscribeToNotifications

▸ **subscribeToNotifications**(`_callbacks?`): `Promise`\<`string`\>

Begins a subscription to this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `_callbacks?` | `Object` | optional set of callbacks to be called when this resource is updated |
| `_callbacks.onNotification` | (`message`: `unknown`) => `void` | - |
| `_callbacks.onNotificationError` | (`err`: `Error`) => `void` | - |

#### Returns

`Promise`\<`string`\>

#### Implementation of

[Resource](../interfaces/Resource.md).[subscribeToNotifications](../interfaces/Resource.md#subscribetonotifications)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:54](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L54)

___

### unsubscribeFromAllNotifications

▸ **unsubscribeFromAllNotifications**(): `Promise`\<`void`\>

Unsubscribes from all notifications.

#### Returns

`Promise`\<`void`\>

#### Implementation of

[Resource](../interfaces/Resource.md).[unsubscribeFromAllNotifications](../interfaces/Resource.md#unsubscribefromallnotifications)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:63](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L63)

___

### unsubscribeFromNotifications

▸ **unsubscribeFromNotifications**(`_subscriptionId`): `Promise`\<`void`\>

Unsubscribes from notifications on this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `_subscriptionId` | `string` | the Id of the subscription to unsubscribe |

#### Returns

`Promise`\<`void`\>

#### Implementation of

[Resource](../interfaces/Resource.md).[unsubscribeFromNotifications](../interfaces/Resource.md#unsubscribefromnotifications)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:60](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L60)

___

### update

▸ **update**(): `Promise`\<[`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>\>

Applies updates to this resource.

#### Returns

`Promise`\<[`InvalidUriError`](InvalidUriError.md)\<[`InvalidIdentifierResource`](InvalidIdentifierResource.md)\>\>

#### Implementation of

[Resource](../interfaces/Resource.md).[update](../interfaces/Resource.md#update)

#### Defined in

[packages/connected/src/InvalidIdentifierResource.ts:51](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/InvalidIdentifierResource.ts#L51)
