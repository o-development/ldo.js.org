# Class: DeleteSuccess\<ResourceType\>

Indicates that the request to delete a resource was a success.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceSuccess`\<`ResourceType`\>

  ↳ **`DeleteSuccess`**

## Constructors

### constructor

• **new DeleteSuccess**\<`ResourceType`\>(`resource`, `resourceExisted`): [`DeleteSuccess`](DeleteSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |
| `resourceExisted` | `boolean` |

#### Returns

[`DeleteSuccess`](DeleteSuccess.md)\<`ResourceType`\>

#### Overrides

ResourceSuccess\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/success/DeleteSuccess.ts:18](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/DeleteSuccess.ts#L18)

## Properties

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

### resourceExisted

• **resourceExisted**: `boolean`

True if there was a resource at the provided URI that was deleted. False if
a resource didn't exist.

#### Defined in

[packages/connected-solid/src/requester/results/success/DeleteSuccess.ts:16](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/DeleteSuccess.ts#L16)

___

### type

• **type**: ``"deleteSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/connected-solid/src/requester/results/success/DeleteSuccess.ts:10](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/DeleteSuccess.ts#L10)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
