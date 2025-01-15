# Function: createSolidLdoDataset

▸ **createSolidLdoDataset**(`options?`): [`SolidLdoDataset`](../classes/SolidLdoDataset.md)

Creates a SolidLdoDataset

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | [`CreateSolidLdoDatasetOptions`](../interfaces/CreateSolidLdoDatasetOptions.md) | CreateSolidLdoDatasetOptions |

#### Returns

[`SolidLdoDataset`](../classes/SolidLdoDataset.md)

A SolidLdoDataset

**`Example`**

```typescript
import { createSolidLdoDataset } from "@ldo/solid";
import { fetch } from "@inrupt/solid-client-authn-browswer";

const solidLdoDataset = createSolidLdoDataset({ fetch });
```

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:44](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/createSolidLdoDataset.ts#L44)
