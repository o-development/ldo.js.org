# Function: updateDatasetOnSuccessfulDelete

▸ **updateDatasetOnSuccessfulDelete**(`uri`, `dataset`): `void`

Assuming a successful delete has just been performed, this function updates
datastores to reflect that.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `string` | The uri of the resouce that was removed |
| `dataset` | `IBulkEditableDataset`\<`Quad`\> | The dataset that should be updated |

#### Returns

`void`

#### Defined in

[packages/solid/src/requester/requests/deleteResource.ts:89](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/deleteResource.ts#L89)
