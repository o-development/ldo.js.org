# Function: changeData

▸ **changeData**\<`Type`\>(`input`, `resource`, `...additionalResources`): `Type`

Begins tracking changes to eventually commit.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `Type` | A linked data object to track changes on |
| `resource` | [`Resource`](../interfaces/Resource.md)\<`string`\> | A resource that all additions will eventually be committed to |
| `...additionalResources` | [`Resource`](../interfaces/Resource.md)\<`string`\>[] | Any additional resources that changes will eventually be committed to |

#### Returns

`Type`

A transactable Linked Data Object

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

[packages/connected/src/methods.ts:38](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/methods.ts#L38)
