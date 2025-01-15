# Function: setWacRuleForAclUri

▸ **setWacRuleForAclUri**(`aclUri`, `newRule`, `accessTo`, `options?`): `Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\>

Given the URI of an ACL document and some WAC rules, set the WAC rules of
that document

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | [`LeafUri`](../types/LeafUri.md) |
| `newRule` | [`WacRule`](../interfaces/WacRule.md) |
| `accessTo` | `string` |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\>

SetWacRuleResult

#### Defined in

[packages/solid/src/resource/wac/setWacRule.ts:28](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/wac/setWacRule.ts#L28)
