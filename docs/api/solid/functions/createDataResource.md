# Function: createDataResource

▸ **createDataResource**(`uri`, `overwrite`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

Creates a data resource (RDF resource) at the provided URI. This resource
could also be a container.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) | The URI of the resource |
| `overwrite` | ``true`` | If true, the request will overwrite any previous resource at this URI. |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

One of many create results depending on the input

**`Example`**

`createDataResource` can be used to create containers.

```typescript
import { createDataResource } from "@ldo/solid";
import { fetch } from "@inrupt/solid-client-autn-js";

const result = await createDataResource(
  "https://example.com/container/",
  true,
  { fetch },
);
if (!result.isError) {
  // Do something
}
```

**`Example`**

`createDataResource` can also create a blank data resource at the provided
URI.

```typescript
import { createDataResource } from "@ldo/solid";
import { fetch } from "@inrupt/solid-client-autn-js";

const result = await createDataResource(
  "https://example.com/container/someResource.ttl",
  true,
  { fetch },
);
if (!result.isError) {
  // Do something
}
```

**`Example`**

Any local RDFJS dataset passed to the `options` field will be updated with
any new RDF data from the create process.

```typescript
import { createDataResource } from "@ldo/solid";
import { createDataset } from "@ldo/dataset"
import { fetch } from "@inrupt/solid-client-autn-js";

const localDataset = createDataset();
const result = await createDataResource(
  "https://example.com/container/someResource.ttl",
  true,
  { fetch, dataset: localDataset },
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:135](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L135)

▸ **createDataResource**(`uri`, `overwrite`, `options?`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:140](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L140)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:145](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L145)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:150](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L150)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:155](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L155)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:160](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L160)

▸ **createDataResource**(`uri`, `overwrite`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:165](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L165)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:170](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L170)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md) \| [`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md) \| [`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:175](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/createDataResource.ts#L175)
