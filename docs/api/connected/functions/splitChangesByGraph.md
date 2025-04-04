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

[packages/connected/src/util/splitChangesByGraph.ts:35](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/util/splitChangesByGraph.ts#L35)
