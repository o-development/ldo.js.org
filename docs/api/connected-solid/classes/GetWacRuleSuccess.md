# Class: GetWacRuleSuccess\<ResourceType\>

Returned when a WAC rule is successfully retrieved

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidLeaf`](SolidLeaf.md) \| [`SolidContainer`](SolidContainer.md) |

## Hierarchy

- `ResourceSuccess`\<`ResourceType`\>

  ↳ **`GetWacRuleSuccess`**

## Constructors

### constructor

• **new GetWacRuleSuccess**\<`ResourceType`\>(`resoure`, `wacRule`): [`GetWacRuleSuccess`](GetWacRuleSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resoure` | `ResourceType` |
| `wacRule` | [`WacRule`](../interfaces/WacRule.md) |

#### Returns

[`GetWacRuleSuccess`](GetWacRuleSuccess.md)\<`ResourceType`\>

#### Overrides

ResourceSuccess\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/wac/results/GetWacRuleSuccess.ts:18](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/GetWacRuleSuccess.ts#L18)

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

• **type**: ``"getWacRuleSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/connected-solid/src/wac/results/GetWacRuleSuccess.ts:12](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/GetWacRuleSuccess.ts#L12)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8

___

### wacRule

• **wacRule**: [`WacRule`](../interfaces/WacRule.md)

The rule that was retrieved

#### Defined in

[packages/connected-solid/src/wac/results/GetWacRuleSuccess.ts:16](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/GetWacRuleSuccess.ts#L16)
