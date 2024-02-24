# Function: uploadResource

▸ **uploadResource**(`uri`, `blob`, `mimeType`, `overwrite`, `options?`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Uploads a binary resource at the provided URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) | The URI of the resource |
| `blob` | `Blob` | - |
| `mimeType` | `string` | - |
| `overwrite` | ``true`` | If true, the request will overwrite any previous resource at this URI. |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

One of many create results depending on the input

**`Example`**

Any local RDFJS dataset passed to the `options` field will be updated with
any new RDF data from the create process.

```typescript
import { createDataResource } from "@ldo/solid";
import { createDataset } from "@ldo/dataset"
import { fetch } from "@inrupt/solid-client-autn-js";

const localDataset = createDataset();
const result = await uploadResource(
  "https://example.com/container/someResource.txt",
  new Blob("some text."),
  "text/txt",
  true,
  { fetch, dataset: localDataset },
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/requester/requests/uploadResource.ts:50](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/requests/uploadResource.ts#L50)

▸ **uploadResource**(`uri`, `blob`, `mimeType`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/uploadResource.ts:57](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/requests/uploadResource.ts#L57)

▸ **uploadResource**(`uri`, `blob`, `mimeType`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/uploadResource.ts:64](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/requests/uploadResource.ts#L64)
