# Function: updateDataResource

▸ **updateDataResource**(`uri`, `datasetChanges`, `options?`): `Promise`\<[`UpdateResult`](../types/UpdateResult.md)\>

Updates a specific data resource with the provided dataset changes

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) | the URI of the data resource |
| `datasetChanges` | `DatasetChanges`\<`Quad`\> | A set of triples added and removed from this dataset |
| `options?` | [`DatasetRequestOptions`](../interfaces/DatasetRequestOptions.md) | Options to provide a fetch function and a local dataset to update. |

#### Returns

`Promise`\<[`UpdateResult`](../types/UpdateResult.md)\>

An UpdateResult

**`Example`**

```typescript
import {
  updateDataResource,
  transactionChanges,
  changeData,
  createSolidLdoDataset,
} from "@ldo/solid";
import { fetch } from "@inrupt/solid-client-authn-browser";

// Initialize an LDO dataset
const solidLdoDataset = createSolidLdoDataset();
// Get a Linked Data Object
const profile = solidLdoDataset
  .usingType(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
// Create a transaction to change data
const cProfile = changeData(
  profile,
  solidLdoDataset.getResource("https://example.com/profile"),
);
cProfile.name = "John Doe";
// Get data in "DatasetChanges" form
const datasetChanges = transactionChanges(someLinkedDataObject);
// Use "updateDataResource" to apply the changes
const result = await updateDataResource(
  "https://example.com/profile",
  datasetChanges,
  { fetch, dataset: solidLdoDataset },
);
```

#### Defined in

[packages/solid/src/requester/requests/updateDataResource.ts:63](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/updateDataResource.ts#L63)
