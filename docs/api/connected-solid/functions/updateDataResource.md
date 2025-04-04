# Function: updateDataResource

▸ **updateDataResource**(`resource`, `datasetChanges`, `options?`): `Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

Updates a specific data resource with the provided dataset changes

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) | - |
| `datasetChanges` | `DatasetChanges`\<`Quad`\> | A set of triples added and removed from this dataset |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

An UpdateResult

#### Defined in

[packages/connected-solid/src/requester/requests/updateDataResource.ts:37](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/updateDataResource.ts#L37)

▸ **updateDataResource**(`resource`, `datasetChanges`, `options?`): `Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) |
| `datasetChanges` | `DatasetChanges`\<`Quad`\> |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/requests/updateDataResource.ts:42](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/updateDataResource.ts#L42)

▸ **updateDataResource**(`resource`, `datasetChanges`, `options?`): `Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `datasetChanges` | `DatasetChanges`\<`Quad`\> |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/requests/updateDataResource.ts:47](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/updateDataResource.ts#L47)
