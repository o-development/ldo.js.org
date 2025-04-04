# Class: CreateSuccess\<ResourceType\>

Indicates that the request to create the resource was a success.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceSuccess`\<`ResourceType`\>

  ↳ **`CreateSuccess`**

## Constructors

### constructor

• **new CreateSuccess**\<`ResourceType`\>(`resource`, `didOverwrite`): [`CreateSuccess`](CreateSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |
| `didOverwrite` | `boolean` |

#### Returns

[`CreateSuccess`](CreateSuccess.md)\<`ResourceType`\>

#### Overrides

ResourceSuccess\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/success/CreateSuccess.ts:17](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CreateSuccess.ts#L17)

## Properties

### didOverwrite

• **didOverwrite**: `boolean`

True if there was a resource that existed before at the given URI that was
overwritten

#### Defined in

[packages/connected-solid/src/requester/results/success/CreateSuccess.ts:15](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CreateSuccess.ts#L15)

___

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

ResourceSuccess.isError

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:5

___

### resource

• **resource**: `ResourceType`

#### Inherited from

ResourceSuccess.resource

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:9

___

### type

• **type**: ``"createSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/connected-solid/src/requester/results/success/CreateSuccess.ts:10](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CreateSuccess.ts#L10)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
