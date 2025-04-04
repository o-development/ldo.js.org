# Class: GetWacUriSuccess\<ResourceType\>

Returned when the URI for a resources ACL document was successfully retried

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |

## Hierarchy

- `ResourceSuccess`\<`ResourceType`\>

  ↳ **`GetWacUriSuccess`**

## Constructors

### constructor

• **new GetWacUriSuccess**\<`ResourceType`\>(`resource`, `wacUri`): [`GetWacUriSuccess`](GetWacUriSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |
| `wacUri` | [`SolidLeafUri`](../types/SolidLeafUri.md) |

#### Returns

[`GetWacUriSuccess`](GetWacUriSuccess.md)\<`ResourceType`\>

#### Overrides

ResourceSuccess\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/wac/results/GetWacUriSuccess.ts:18](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/GetWacUriSuccess.ts#L18)

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

### type

• **type**: ``"getWacUriSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/connected-solid/src/wac/results/GetWacUriSuccess.ts:12](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/GetWacUriSuccess.ts#L12)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8

___

### wacUri

• **wacUri**: [`SolidLeafUri`](../types/SolidLeafUri.md)

The URI of the ACL document

#### Defined in

[packages/connected-solid/src/wac/results/GetWacUriSuccess.ts:16](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/GetWacUriSuccess.ts#L16)
