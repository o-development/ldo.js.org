# Class: Websocket2023NotificationSubscription

An implementation of the Websocket2023 notifiction spec

## Hierarchy

- `NotificationSubscription`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md), [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)\>

  ↳ **`Websocket2023NotificationSubscription`**

## Constructors

### constructor

• **new Websocket2023NotificationSubscription**(`resource`, `parentSubscription`, `context`, `createWebsocket?`): [`Websocket2023NotificationSubscription`](Websocket2023NotificationSubscription.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |
| `parentSubscription` | (`message`: [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)) => `void` |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> |
| `createWebsocket?` | (`address`: `string`) => `WebSocket` |

#### Returns

[`Websocket2023NotificationSubscription`](Websocket2023NotificationSubscription.md)

#### Overrides

NotificationSubscription\&lt;
  SolidConnectedPlugin,
  SolidNotificationMessage
\&gt;.constructor

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:44](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L44)

## Properties

### context

• `Protected` **context**: `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\>

#### Inherited from

NotificationSubscription.context

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:8

___

### createWebsocket

• `Private` **createWebsocket**: (`address`: `string`) => `WebSocket`

#### Type declaration

▸ (`address`): `WebSocket`

##### Parameters

| Name | Type |
| :------ | :------ |
| `address` | `string` |

##### Returns

`WebSocket`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:32](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L32)

___

### isManualClose

• `Private` **isManualClose**: `boolean` = `false`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:40](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L40)

___

### maxReconnectAttempts

• `Private` **maxReconnectAttempts**: `number` = `6`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:42](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L42)

___

### parentSubscription

• `Protected` **parentSubscription**: (`message`: [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)) => `void`

#### Type declaration

▸ (`message`): `void`

##### Parameters

| Name | Type |
| :------ | :------ |
| `message` | [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md) |

##### Returns

`void`

#### Inherited from

NotificationSubscription.parentSubscription

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:7

___

### reconnectAttempts

• `Private` **reconnectAttempts**: `number` = `0`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:38](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L38)

___

### reconnectInterval

• `Private` **reconnectInterval**: `number` = `5000`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:36](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L36)

___

### resource

• `Protected` **resource**: [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)

#### Inherited from

NotificationSubscription.resource

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:6

___

### socket

• `Private` **socket**: `undefined` \| `WebSocket`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:31](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L31)

___

### subscriptions

• `Protected` **subscriptions**: `Record`\<`string`, `SubscriptionCallbacks`\<[`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)\>\>

#### Inherited from

NotificationSubscription.subscriptions

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:9

## Methods

### close

▸ **close**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Overrides

NotificationSubscription.close

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:140](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L140)

___

### discoverNotificationChannel

▸ **discoverNotificationChannel**(): `Promise`\<`NotificationChannel`\>

#### Returns

`Promise`\<`NotificationChannel`\>

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:75](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L75)

___

### isSubscribedToNotifications

▸ **isSubscribedToNotifications**(): `boolean`

#### Returns

`boolean`

#### Inherited from

NotificationSubscription.isSubscribedToNotifications

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:12

___

### onClose

▸ **onClose**(): `void`

#### Returns

`void`

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:115](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L115)

___

### onNotification

▸ **onNotification**(`message`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `message` | [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md) |

#### Returns

`void`

#### Inherited from

NotificationSubscription.onNotification

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:18

___

### onNotificationError

▸ **onNotificationError**(`message`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `message` | `NotificationCallbackError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> |

#### Returns

`void`

#### Inherited from

NotificationSubscription.onNotificationError

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:19

___

### open

▸ **open**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Overrides

NotificationSubscription.open

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:54](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L54)

___

### setIsOpen

▸ **setIsOpen**(`status`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `status` | `boolean` |

#### Returns

`void`

#### Inherited from

NotificationSubscription.setIsOpen

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:20

___

### subscribeToNotifications

▸ **subscribeToNotifications**(`subscriptionCallbacks?`): `Promise`\<`string`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `subscriptionCallbacks?` | `SubscriptionCallbacks`\<[`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)\> |

#### Returns

`Promise`\<`string`\>

#### Inherited from

NotificationSubscription.subscribeToNotifications

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:13

___

### subscribeToWebsocket

▸ **subscribeToWebsocket**(`notificationChannel`): `Promise`\<`void`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `notificationChannel` | `NotificationChannel` |

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts:85](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/Websocket2023NotificationSubscription.ts#L85)

___

### unsubscribeFromAllNotifications

▸ **unsubscribeFromAllNotifications**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Inherited from

NotificationSubscription.unsubscribeFromAllNotifications

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:15

___

### unsubscribeFromNotification

▸ **unsubscribeFromNotification**(`subscriptionId`): `Promise`\<`void`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `subscriptionId` | `string` |

#### Returns

`Promise`\<`void`\>

#### Inherited from

NotificationSubscription.unsubscribeFromNotification

#### Defined in

packages/connected/dist/notifications/NotificationSubscription.d.ts:14
