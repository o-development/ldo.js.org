# Type alias: ConnectedContext\<Plugins\>

Ƭ **ConnectedContext**\<`Plugins`\>: \{ `dataset`: [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\>  } & \{ [P in Plugins[number] as P["name"]]: P["types"]["context"] }

Each Plugin comes with a context. This is the aggregate of all those contexts
It is passed between the various components of the "connected" library

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`\>[] |

#### Defined in

[packages/connected/src/types/ConnectedContext.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedContext.ts#L9)
