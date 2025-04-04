# Function: getStorageFromWebId

▸ **getStorageFromWebId**(`webId`, `dataset`): `Promise`\<[`GetStorageContainerFromWebIdSuccess`](../classes/GetStorageContainerFromWebIdSuccess.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`ReadResultError`](../types/ReadResultError.md)\<[`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md)\> \| [`NoRootContainerError`](../classes/NoRootContainerError.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

Gets a list of root storage containers for a user given their WebId

#### Parameters

| Name | Type |
| :------ | :------ |
| `webId` | [`SolidLeafUri`](../types/SolidLeafUri.md) |
| `dataset` | `ConnectedLdoDataset`\<(`ConnectedPlugin`\<`any`, `any`, `any`, `any`, `any`\> \| [`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md))[]\> |

#### Returns

`Promise`\<[`GetStorageContainerFromWebIdSuccess`](../classes/GetStorageContainerFromWebIdSuccess.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`ReadResultError`](../types/ReadResultError.md)\<[`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md)\> \| [`NoRootContainerError`](../classes/NoRootContainerError.md)\<[`SolidContainer`](../classes/SolidContainer.md)\>\>

A list of storages if successful, an error if not

**`Example`**

```typescript
import { getStorageFromWebId } from "@ldo/connected-solid";

const result = await getStorageFromWebId(
  solidLdoDataset,
  "https://example.com/profile/card#me"
);
if (result.isError) {
  // Do something
}
console.log(result.storageContainer[0].uri);
```

#### Defined in

[packages/connected-solid/src/getStorageFromWebId.ts:31](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/getStorageFromWebId.ts#L31)
