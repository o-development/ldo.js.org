# Interface: SubscriptionCallbacks\<NotificationMessage\>

A set of callback functions that are called when a resource recieves a
notification

## Type parameters

| Name |
| :------ |
| `NotificationMessage` |

## Properties

### onNotification

• `Optional` **onNotification**: (`message`: `NotificationMessage`) => `void`

Triggers when a notification was received.

#### Type declaration

▸ (`message`): `void`

##### Parameters

| Name | Type |
| :------ | :------ |
| `message` | `NotificationMessage` |

##### Returns

`void`

#### Defined in

[packages/connected/src/notifications/SubscriptionCallbacks.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/SubscriptionCallbacks.ts#L9)

___

### onNotificationError

• `Optional` **onNotificationError**: (`error`: `Error`) => `void`

Triggers when a notification error was received.

#### Type declaration

▸ (`error`): `void`

##### Parameters

| Name | Type |
| :------ | :------ |
| `error` | `Error` |

##### Returns

`void`

#### Defined in

[packages/connected/src/notifications/SubscriptionCallbacks.ts:14](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/notifications/SubscriptionCallbacks.ts#L14)
