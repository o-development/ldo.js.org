# Class: WacRuleAbsent\<ResourceType\>

Returned if no WAC rule was returned from the server

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidLeaf`](SolidLeaf.md) \| [`SolidContainer`](SolidContainer.md) |

## Hierarchy

- `ResourceSuccess`\<`ResourceType`\>

  ↳ **`WacRuleAbsent`**

## Constructors

### constructor

• **new WacRuleAbsent**\<`ResourceType`\>(`resource`): [`WacRuleAbsent`](WacRuleAbsent.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |

#### Returns

[`WacRuleAbsent`](WacRuleAbsent.md)\<`ResourceType`\>

#### Inherited from

ResourceSuccess\<ResourceType\>.constructor

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:10

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

• **type**: ``"wacRuleAbsent"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/connected-solid/src/wac/results/WacRuleAbsent.ts:11](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/results/WacRuleAbsent.ts#L11)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
