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

[packages/connected-solid/src/requester/requests/deleteResource.ts:84](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/deleteResource.ts#L84)
