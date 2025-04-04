# Class: UnsupportedNotificationError\<ResourceType\>

Indicates that the requested method for receiving notifications is not
supported by this Pod.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceError`\<`ResourceType`\>

  ↳ **`UnsupportedNotificationError`**

## Constructors

### constructor

• **new UnsupportedNotificationError**\<`ResourceType`\>(`resource`, `message?`): [`UnsupportedNotificationError`](UnsupportedNotificationError.md)\<`ResourceType`\>

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

[`UnsupportedNotificationError`](UnsupportedNotificationError.md)\<`ResourceType`\>

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

• `Readonly` **type**: ``"unsupportedNotificationError"``

#### Overrides

ResourceError.type

#### Defined in

[packages/connected-solid/src/notifications/results/NotificationErrors.ts:17](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/notifications/results/NotificationErrors.ts#L17)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceError.uri

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:9
