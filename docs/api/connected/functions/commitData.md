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

[packages/connected/src/methods.ts:76](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/methods.ts#L76)
