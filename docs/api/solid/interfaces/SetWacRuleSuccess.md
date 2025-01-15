# Interface: SetWacRuleSuccess

Returned when rules were successfully written

## Hierarchy

- `ResourceSuccess`

  ↳ **`SetWacRuleSuccess`**

## Properties

### isError

• **isError**: ``false``

#### Inherited from

ResourceSuccess.isError

#### Defined in

[packages/solid/src/requester/results/success/SuccessResult.ts:7](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/results/success/SuccessResult.ts#L7)

___

### type

• **type**: ``"setWacRuleSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/solid/src/resource/wac/results/SetWacRuleSuccess.ts:8](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/wac/results/SetWacRuleSuccess.ts#L8)

___

### uri

• **uri**: `string`

The URI of the resource

#### Inherited from

ResourceSuccess.uri

#### Defined in

[packages/solid/src/requester/results/success/SuccessResult.ts:17](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/results/success/SuccessResult.ts#L17)

___

### wacRule

• **wacRule**: [`WacRule`](WacRule.md)

The written rule

#### Defined in

[packages/solid/src/resource/wac/results/SetWacRuleSuccess.ts:12](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/wac/results/SetWacRuleSuccess.ts#L12)
