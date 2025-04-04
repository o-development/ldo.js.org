# Function: checkRootContainer

▸ **checkRootContainer**(`resource`, `options?`): `Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

Performs a request to the Pod to check if the given URI is a root container
as defined in the [solid specification section 4.1](https://solidproject.org/TR/protocol#storage-resource)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) | the the container resource |
| `options?` | [`BasicRequestOptions`](../interfaces/BasicRequestOptions.md) | options variable to pass a fetch function |

#### Returns

`Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

CheckResourceSuccess if there is no error

#### Defined in

[packages/connected-solid/src/requester/requests/checkRootContainer.ts:61](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/checkRootContainer.ts#L61)
