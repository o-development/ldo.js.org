# Class: NotificationSubscription\<Plugin, NotificationMessage\>

Abstract class for notification subscription methods.

## Type parameters

| Name | Type |
| :------ | :------ |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md) |
| `NotificationMessage` | `NotificationMessage` |

## Constructors

### constructor

• **new NotificationSubscription**\<`Plugin`, `NotificationMessage`\>(`resource`, `parentSubscription`, `context`): [`NotificationSubscription`](NotificationSubscription.md)\<`Plugin`, `NotificationMessage`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\> |
| `NotificationMessage` | `NotificationMessage` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `Plugin`[``"types"``][``"resource"``] |
| `parentSubscription` | (`message`: `NotificationMessage`) => `void` |
| `context` | [`ConnectedContext`](../types/ConnectedContext.md)\<`Plugin`[]\> |

#### Returns

[`NotificationSubscription`](NotificationSubscription.md)\<`Plugin`, `NotificationMessage`\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:24](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L24)

## Properties

### context

• `Protected` **context**: [`ConnectedContext`](../types/ConnectedContext.md)\<`Plugin`[]\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:17](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L17)

___

### isOpen

• `Private` **isOpen**: `boolean` = `false`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:22](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L22)

___

### parentSubscription

• `Protected` **parentSubscription**: (`message`: `NotificationMessage`) => `void`

#### Type declaration

▸ (`message`): `void`

##### Parameters

| Name | Type |
| :------ | :------ |
| `message` | `NotificationMessage` |

##### Returns

`void`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:16](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L16)

___

### resource

• `Protected` **resource**: `Plugin`[``"types"``][``"resource"``]

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:15](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L15)

___

### subscriptions

• `Protected` **subscriptions**: `Record`\<`string`, [`SubscriptionCallbacks`](../interfaces/SubscriptionCallbacks.md)\<`NotificationMessage`\>\> = `{}`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:18](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L18)

## Methods

### close

▸ **close**(): `Promise`\<`void`\>

Closes the subscription

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:103](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L103)

___

### isSubscribedToNotifications

▸ **isSubscribedToNotifications**(): `boolean`

#### Returns

`boolean`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:34](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L34)

___

### onNotification

▸ **onNotification**(`message`): `void`

onNotification

#### Parameters

| Name | Type |
| :------ | :------ |
| `message` | `NotificationMessage` |

#### Returns

`void`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:115](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L115)

___

### onNotificationError

▸ **onNotificationError**(`message`): `void`

onNotificationError

#### Parameters

| Name | Type |
| :------ | :------ |
| `message` | [`NotificationCallbackError`](../types/NotificationCallbackError.md)\<`Plugin`[``"types"``][``"resource"``]\> |

#### Returns

`void`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:126](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L126)

___

### open

▸ **open**(): `Promise`\<`void`\>

Opens the subscription

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:97](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L97)

___

### setIsOpen

▸ **setIsOpen**(`status`): `void`

setIsOpen

#### Parameters

| Name | Type |
| :------ | :------ |
| `status` | `boolean` |

#### Returns

`void`

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:141](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L141)

___

### subscribeToNotifications

▸ **subscribeToNotifications**(`subscriptionCallbacks?`): `Promise`\<`string`\>

subscribeToNotifications

#### Parameters

| Name | Type |
| :------ | :------ |
| `subscriptionCallbacks?` | [`SubscriptionCallbacks`](../interfaces/SubscriptionCallbacks.md)\<`NotificationMessage`\> |

#### Returns

`Promise`\<`string`\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:48](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L48)

___

### unsubscribeFromAllNotifications

▸ **unsubscribeFromAllNotifications**(): `Promise`\<`void`\>

unsubscribeFromAllNotifications

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:79](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L79)

___

### unsubscribeFromNotification

▸ **unsubscribeFromNotification**(`subscriptionId`): `Promise`\<`void`\>

unsubscribeFromNotification

#### Parameters

| Name | Type |
| :------ | :------ |
| `subscriptionId` | `string` |

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/notifications/NotificationSubscription.ts:64](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/NotificationSubscription.ts#L64)
