# Function: getWacRuleWithAclUri

▸ **getWacRuleWithAclUri**(`aclUri`, `resource`, `options?`): `Promise`\<[`GetWacRuleResult`](../types/GetWacRuleResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

Given the URI of an ACL document, return the Web Access Control (WAC) rules

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | `string` |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`GetWacRuleResult`](../types/GetWacRuleResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

GetWacRuleResult

#### Defined in

[packages/connected-solid/src/wac/getWacRule.ts:34](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/getWacRule.ts#L34)

▸ **getWacRuleWithAclUri**(`aclUri`, `resource`, `options?`): `Promise`\<[`GetWacRuleResult`](../types/GetWacRuleResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | `string` |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`GetWacRuleResult`](../types/GetWacRuleResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/wac/getWacRule.ts:39](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/getWacRule.ts#L39)

▸ **getWacRuleWithAclUri**(`aclUri`, `resource`, `options?`): `Promise`\<[`GetWacRuleResult`](../types/GetWacRuleResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `aclUri` | `string` |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`GetWacRuleResult`](../types/GetWacRuleResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md)\>\>

#### Defined in

[packages/connected-solid/src/wac/getWacRule.ts:44](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/wac/getWacRule.ts#L44)
