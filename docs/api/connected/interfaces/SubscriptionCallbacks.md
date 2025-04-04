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

[packages/connected/src/SubscriptionCallbacks.ts:9](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/SubscriptionCallbacks.ts#L9)

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

[packages/connected/src/SubscriptionCallbacks.ts:14](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/SubscriptionCallbacks.ts#L14)
