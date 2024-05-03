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
| `resource` | [`Resource`](../classes/Resource.md) | A resource that all additions will eventually be committed to |
| `...additionalResources` | [`Resource`](../classes/Resource.md)[] | Any additional resources that changes will eventually be committed to |

#### Returns

`Type`

A transactable Linked Data Object

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

[packages/solid/src/methods.ts:33](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/methods.ts#L33)
