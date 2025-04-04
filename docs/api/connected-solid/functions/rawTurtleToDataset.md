# Function: rawTurtleToDataset

▸ **rawTurtleToDataset**(`rawTurtle`, `baseUri`): `Promise`\<`LdoDataset` \| `Error`\>

Creates a dataset from raw turtle string

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `rawTurtle` | `string` | the Raw turtle string |
| `baseUri` | `string` | A base url for relative uris |

#### Returns

`Promise`\<`LdoDataset` \| `Error`\>

LdoDataset or Error

#### Defined in

[packages/connected-solid/src/util/rdfUtils.ts:138](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/rdfUtils.ts#L138)
