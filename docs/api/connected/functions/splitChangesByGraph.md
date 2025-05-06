# Function: splitChangesByGraph

▸ **splitChangesByGraph**(`changes`): `Map`\<`GraphNode`, `DatasetChanges`\<`Quad`\>\>

Splits all changes in a DatasetChanges into individual DatasetChanges grouped
by the quad graph.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> | Changes to split |

#### Returns

`Map`\<`GraphNode`, `DatasetChanges`\<`Quad`\>\>

A map between the quad graph and the changes associated with that
graph

#### Defined in

[packages/connected/src/util/splitChangesByGraph.ts:35](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/util/splitChangesByGraph.ts#L35)
