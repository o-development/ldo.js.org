# Type alias: GetResourceReturnType\<Plugin, UriType\>

Ƭ **GetResourceReturnType**\<`Plugin`, `UriType`\>: `UriType` extends `Plugin`[``"types"``][``"uri"``] ? [`ReturnTypeFromArgs`](ReturnTypeFromArgs.md)\<`Plugin`[``"getResource"``], `UriType`\> : `ReturnType`\<`Plugin`[``"getResource"``]\> \| [`InvalidIdentifierResource`](../classes/InvalidIdentifierResource.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md) |
| `UriType` | extends `string` |

#### Defined in

[packages/connected/src/IConnectedLdoDataset.ts:13](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/IConnectedLdoDataset.ts#L13)
