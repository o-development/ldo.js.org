# Function: createConnectedLdoDataset

▸ **createConnectedLdoDataset**\<`Plugins`\>(`plugins`): [`ConnectedLdoDataset`](../classes/ConnectedLdoDataset.md)\<`Plugins`\>

Creates a ConnectedLdoDataset

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `plugins` | `Plugins` | An array of plugins for platforms to connect to |

#### Returns

[`ConnectedLdoDataset`](../classes/ConnectedLdoDataset.md)\<`Plugins`\>

- A ConnectedLdoDataset

**`Example`**

```typescript
import { createConnectedLdoDataset } from "@ldo/connected";

// At least one plugin needs to be provided to a ConnectedLdoDataset. In this
// example we'll use both the Solid and NextGraph plugins.
import { solidConnectedPlugin } from "@ldo/connected-solid";
import { nextGraphConnectedPlugin } from "@ldo/connected-nextgraph";

// ...

const connectedLdoDataset = createConnectedLdoDataset([
  solidConnectedPlugin,
  nextGraphConnectedPlugin
]);
```

#### Defined in

[packages/connected/src/createConntectedLdoDataset.ts:28](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/createConntectedLdoDataset.ts#L28)
