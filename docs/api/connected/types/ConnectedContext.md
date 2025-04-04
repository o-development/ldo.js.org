# Type alias: ConnectedContext\<Plugins\>

Ƭ **ConnectedContext**\<`Plugins`\>: \{ `dataset`: [`ConnectedLdoDataset`](../classes/ConnectedLdoDataset.md)\<`Plugins`\>  } & \{ [P in Plugins[number] as P["name"]]: P["types"]["context"] }

Each Plugin comes with a context. This is the aggregate of all those contexts
It is passed between the various components of the "connected" library

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`\>[] |

#### Defined in

[packages/connected/src/ConnectedContext.ts:9](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/ConnectedContext.ts#L9)
