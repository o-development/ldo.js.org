# Function: readResource

▸ **readResource**(`resource`, `options?`): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

Reads resource at a provided URI and returns the result

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) | - |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

ReadResult

#### Defined in

[packages/connected-solid/src/requester/requests/readResource.ts:60](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/readResource.ts#L60)

▸ **readResource**(`resource`, `options?`): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/readResource.ts:64](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/readResource.ts#L64)

▸ **readResource**(`resource`, `options?`): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md) \| [`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md) \| [`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/readResource.ts:68](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/readResource.ts#L68)
