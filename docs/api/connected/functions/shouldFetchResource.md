# Function: shouldFetchResource

▸ **shouldFetchResource**\<`Type`, `Plugins`\>(`dataset`, `ldObject`, `queryInput`, `encounteredDuringThisExploration`): `boolean`

Determines if a resource needs to be fetched based on given data

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type |
| :------ | :------ |
| `dataset` | [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\> |
| `ldObject` | `Type` |
| `queryInput` | `Partial`\<\{ [key in string \| number \| symbol]: LQInputFlattenSet\<Type[key]\> }\> |
| `encounteredDuringThisExploration` | `Set`\<`string`\> |

#### Returns

`boolean`

#### Defined in

[packages/connected/src/linkTraversal/exploreLinks.ts:136](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/exploreLinks.ts#L136)
