# Function: addRawTurtleToDataset

▸ **addRawTurtleToDataset**(`rawTurtle`, `dataset`, `baseUri`): `Promise`\<`undefined` \| `Error`\>

Adds raw turtle to the provided dataset

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `rawTurtle` | `string` | String of raw turtle |
| `dataset` | `Dataset`\<`Quad`, `Quad`\> | the dataset to modify |
| `baseUri` | `string` | base URI to parsing turtle |

#### Returns

`Promise`\<`undefined` \| `Error`\>

Undefined if successful, noncompliantPodError if not

#### Defined in

[packages/connected-solid/src/util/rdfUtils.ts:112](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/rdfUtils.ts#L112)
