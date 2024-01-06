# Function: commitData

▸ **commitData**(`input`): `ReturnType`\<[`SolidLdoDataset`](../classes/SolidLdoDataset.md)[``"commitChangesToPod"``]\>

Commits the transaction to the global dataset, syncing all subscribing
components and Solid Pods

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `LdoBase` | A transactable linked data object |

#### Returns

`ReturnType`\<[`SolidLdoDataset`](../classes/SolidLdoDataset.md)[``"commitChangesToPod"``]\>

**`Example`**

```typescript
import { changeData } from "@ldo/solid";

// ...

const profile = solidLdoDataset
  .using(ProfileShapeType)
  .fromSubject("https://example.com/proifle#me");
const resource = solidLdoDataset.getResource("https://example.com/profile");

const cProfile = changeData(profile, resource);
cProfile.name = "My New Name";
await commitData(cProfile);
```

#### Defined in

[packages/solid/src/methods.ts:78](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/methods.ts#L78)
