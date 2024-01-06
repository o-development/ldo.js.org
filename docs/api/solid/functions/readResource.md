# Function: readResource

▸ **readResource**(`uri`, `options?`): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

Reads resource at a provided URI and returns the result

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) | The URI of the resource |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

ReadResult

**`Example`**

```typescript
import { deleteResource } from "@ldo/solid";
import { createDataset } from "@ldo/dataset"
import { fetch } from "@inrupt/solid-client-autn-js";

const dataset = createDataset();
const result = await readResource(
  "https://example.com/container/someResource.ttl",
  { fetch, dataset },
);
if (!result.isError) {
  if (result.type === "absentReadSuccess") {
    // There was no problem reading the resource, but it doesn't exist
  } else if (result.type === "dataReadSuccess") {
    // The resource was read and it is an RDF resource. The dataset provided
    // dataset will also be loaded with the data from the resource
  } else if (result.type === "binaryReadSuccess") {
    // The resource is a binary
    console.log(result.blob);
    console.log(result.mimeType);
  }
}
```

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:83](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/requester/requests/readResource.ts#L83)

▸ **readResource**(`uri`, `options?`): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:87](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/requester/requests/readResource.ts#L87)

▸ **readResource**(`uri`, `options?`): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md) \| [`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md) \| [`ReadContainerResult`](../types/ReadContainerResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:91](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/requester/requests/readResource.ts#L91)
