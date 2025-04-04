# Function: commitData

▸ **commitData**(`input`): `Promise`\<[`AggregateSuccess`](../classes/AggregateSuccess.md)\<[`SuccessResult`](../classes/SuccessResult.md)\> \| [`AggregateError`](../classes/AggregateError.md)\<[`ErrorResult`](../classes/ErrorResult.md)\>\>

Commits the transaction to the global dataset, syncing all subscribing
components and connected Pods

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `LdoBase` | A transactable linked data object |

#### Returns

`Promise`\<[`AggregateSuccess`](../classes/AggregateSuccess.md)\<[`SuccessResult`](../classes/SuccessResult.md)\> \| [`AggregateError`](../classes/AggregateError.md)\<[`ErrorResult`](../classes/ErrorResult.md)\>\>

**`Example`**

```typescript
import { changeData } from "@ldo/connected";

// ...

const profile = connectedLdoDataset
  .using(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
const resource = connectedLdoDataset.getResource("https://example.com/profile");

const cProfile = changeData(profile, resource);
cProfile.name = "My New Name";
const result = await commitData(cProfile);
```

#### Defined in

[packages/connected/src/methods.ts:76](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/methods.ts#L76)
