# Class: DisconnectedNotAttemptingReconnectError\<ResourceType\>

Indicates that the socket has disconnected and is attempting to reconnect.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceError`\<`ResourceType`\>

  ↳ **`DisconnectedNotAttemptingReconnectError`**

## Constructors

### constructor

• **new DisconnectedNotAttemptingReconnectError**\<`ResourceType`\>(`resource`, `message?`): [`DisconnectedNotAttemptingReconnectError`](DisconnectedNotAttemptingReconnectError.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |
| `message?` | `string` |

#### Returns

[`DisconnectedNotAttemptingReconnectError`](DisconnectedNotAttemptingReconnectError.md)\<`ResourceType`\>

#### Inherited from

ResourceError\<ResourceType\>.constructor

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:11

## Properties

### isError

• `Readonly` **isError**: ``true``

#### Inherited from

ResourceError.isError

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:5

___

### resource

• `Readonly` **resource**: `ResourceType`

#### Inherited from

ResourceError.resource

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:10

___

### type

• `Readonly` **type**: ``"disconnectedNotAttemptingReconnectError"``

#### Overrides

ResourceError.type

#### Defined in

[packages/connected-solid/src/notifications/results/NotificationErrors.ts:35](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/results/NotificationErrors.ts#L35)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceError.uri

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:9
