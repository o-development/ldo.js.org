# Function: uploadResource

▸ **uploadResource**(`resource`, `blob`, `mimeType`, `overwrite`, `options?`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Uploads a binary resource at the provided URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) | - |
| `blob` | `Blob` | - |
| `mimeType` | `string` | - |
| `overwrite` | ``true`` | If true, the request will overwrite any previous resource at this URI. |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

One of many create results depending on the input

#### Defined in

[packages/connected-solid/src/requester/requests/uploadResource.ts:30](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/uploadResource.ts#L30)

▸ **uploadResource**(`resource`, `blob`, `mimeType`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/uploadResource.ts:37](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/uploadResource.ts#L37)
