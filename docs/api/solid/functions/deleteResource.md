# Function: deleteResource

▸ **deleteResource**(`uri`, `options?`): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

Deletes a resource on a Pod at a given URL.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `string` | The URI for the resource that should be deleted |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

a DeleteResult

**`Example`**

`deleteResource` will send a request to a Solid Pod using the provided fetch
function. A local dataset can also be provided. It will be updated with any
new information from the delete.

```typescript
import { deleteResource } from "@ldo/solid";
import { createDataset } from "@ldo/dataset"
import { fetch } from "@inrupt/solid-client-autn-js";

const localDataset = createDataset();
const result = await deleteResource(
  "https://example.com/container/someResource.ttl",
  { fetch, dataset: localDataset },
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/requester/requests/deleteResource.ts:51](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/deleteResource.ts#L51)
