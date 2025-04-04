# Function: deleteResource

▸ **deleteResource**(`resource`, `options?`): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

Deletes a resource on a Pod at a given URL.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) | - |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

a DeleteResult

#### Defined in

[packages/connected-solid/src/requester/requests/deleteResource.ts:39](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/deleteResource.ts#L39)

▸ **deleteResource**(`resource`, `options?`): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/requests/deleteResource.ts:43](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/deleteResource.ts#L43)

▸ **deleteResource**(`resource`, `options?`): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/requests/deleteResource.ts:47](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/deleteResource.ts#L47)
