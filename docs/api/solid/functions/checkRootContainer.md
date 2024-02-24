# Function: checkRootContainer

▸ **checkRootContainer**(`uri`, `options?`): `Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

Performs a request to the Pod to check if the given URI is a root container
as defined in the [solid specification section 4.1](https://solidproject.org/TR/protocol#storage-resource)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) | the URI of the container resource |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) | options variable to pass a fetch function |

#### Returns

`Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

CheckResourceSuccess if there is no error

**`Example`**

```typescript
import { checkRootContainer } from "@ldo/solid";
import { fetch } from "@inrupt/solid-client-authn-browser";

const result = await checkRootContainer("https://example.com/", { fetch });
if (!result.isError) {
  // true if the container is a root container
  console.log(result.isRootContainer);
}
```

#### Defined in

[packages/solid/src/requester/requests/checkRootContainer.ts:78](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/requests/checkRootContainer.ts#L78)
