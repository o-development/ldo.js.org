# Class: AccessRuleFetchError\<ResourceType\>

An error: Could not fetch access rules

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceError`\<`ResourceType`\>

  ↳ **`AccessRuleFetchError`**

## Constructors

### constructor

• **new AccessRuleFetchError**\<`ResourceType`\>(`resource`, `message?`): [`AccessRuleFetchError`](AccessRuleFetchError.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | `ResourceType` | The resource for which access rules couldn't be fetched |
| `message?` | `string` | A custom message for the error |

#### Returns

[`AccessRuleFetchError`](AccessRuleFetchError.md)\<`ResourceType`\>

#### Overrides

ResourceError\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/error/AccessControlError.ts:18](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/AccessControlError.ts#L18)

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

• `Readonly` **type**: ``"accessRuleFetchError"``

#### Overrides

ResourceError.type

#### Defined in

[packages/connected-solid/src/requester/results/error/AccessControlError.ts:11](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/AccessControlError.ts#L11)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceError.uri

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:9
