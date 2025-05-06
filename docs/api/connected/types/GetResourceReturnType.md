# Type alias: GetResourceReturnType\<Plugin, UriType\>

Ƭ **GetResourceReturnType**\<`Plugin`, `UriType`\>: `UriType` extends `Plugin`[``"types"``][``"uri"``] ? [`ReturnTypeFromArgs`](ReturnTypeFromArgs.md)\<`Plugin`[``"getResource"``], `UriType`\> : `ReturnType`\<`Plugin`[``"getResource"``]\> \| [`InvalidIdentifierResource`](../classes/InvalidIdentifierResource.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugin` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md) |
| `UriType` | extends `string` |

#### Defined in

[packages/connected/src/types/IConnectedLdoDataset.ts:14](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoDataset.ts#L14)
