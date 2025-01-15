# Function: commitData

▸ **commitData**(`input`): `ReturnType`\<[`SolidLdoTransactionDataset`](../classes/SolidLdoTransactionDataset.md)[``"commitToPod"``]\>

Commits the transaction to the global dataset, syncing all subscribing
components and Solid Pods

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `LdoBase` | A transactable linked data object |

#### Returns

`ReturnType`\<[`SolidLdoTransactionDataset`](../classes/SolidLdoTransactionDataset.md)[``"commitToPod"``]\>

**`Example`**

```typescript
import { changeData } from "@ldo/solid";

// ...

const profile = solidLdoDataset
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
const resource = solidLdoDataset.getResource("https://example.com/profile");

const cProfile = changeData(profile, resource);
cProfile.name = "My New Name";
const result = await commitData(cProfile);
```

#### Defined in

[packages/solid/src/methods.ts:71](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/methods.ts#L71)
