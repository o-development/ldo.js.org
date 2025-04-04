# Function: createDataResource

▸ **createDataResource**(`resource`, `overwrite`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

Creates a data resource (RDF resource) at the provided URI. This resource
could also be a container.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidLeaf`](../classes/SolidLeaf.md) | The resource |
| `overwrite` | ``true`` | If true, the request will overwrite any previous resource at this URI. |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

One of many create results depending on the input

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:88](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L88)

▸ **createDataResource**(`resouce`, `overwrite`, `options?`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resouce` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:93](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L93)

▸ **createDataResource**(`resouce`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resouce` | [`SolidContainer`](../classes/SolidContainer.md) |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:98](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L98)

▸ **createDataResource**(`resouce`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resouce` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:103](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L103)

▸ **createDataResource**(`resouce`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resouce` | [`SolidContainer`](../classes/SolidContainer.md) |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:108](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L108)

▸ **createDataResource**(`resouce`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resouce` | [`SolidLeaf`](../classes/SolidLeaf.md) |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:113](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L113)

▸ **createDataResource**(`resource`, `overwrite`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:118](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L118)

▸ **createDataResource**(`resource`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:123](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L123)

▸ **createDataResource**(`resource`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md) \| [`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md) \| [`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/requests/createDataResource.ts:128](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/createDataResource.ts#L128)
