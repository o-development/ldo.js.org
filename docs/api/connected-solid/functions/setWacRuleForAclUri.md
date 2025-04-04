# Function: setWacRuleForAclUri

▸ **setWacRuleForAclUri**(`aclUri`, `newRule`, `resource`, `options?`): `Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

Given the URI of an ACL document and some WAC rules, set the WAC rules of
that document

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | [`SolidLeafUri`](../types/SolidLeafUri.md) |
| `newRule` | [`WacRule`](../interfaces/WacRule.md) |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

SetWacRuleResult

#### Defined in

[packages/connected-solid/src/wac/setWacRule.ts:35](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/setWacRule.ts#L35)

▸ **setWacRuleForAclUri**(`aclUri`, `newRule`, `resource`, `options?`): `Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | [`SolidLeafUri`](../types/SolidLeafUri.md) |
| `newRule` | [`WacRule`](../interfaces/WacRule.md) |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/wac/setWacRule.ts:41](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/setWacRule.ts#L41)

▸ **setWacRuleForAclUri**(`aclUri`, `newRule`, `resource`, `options?`): `Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\<[`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | [`SolidLeafUri`](../types/SolidLeafUri.md) |
| `newRule` | [`WacRule`](../interfaces/WacRule.md) |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`SetWacRuleResult`](../types/SetWacRuleResult.md)\<[`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/wac/setWacRule.ts:47](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/setWacRule.ts#L47)
