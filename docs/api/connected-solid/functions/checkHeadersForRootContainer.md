# Function: checkHeadersForRootContainer

▸ **checkHeadersForRootContainer**(`resource`, `headers`): [`CheckRootContainerSuccess`](../classes/CheckRootContainerSuccess.md)

Checks provided headers to see if a given URI is a root container as defined
in the [solid specification section 4.1](https://solidproject.org/TR/protocol#storage-resource)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) | - |
| `headers` | `Headers` | headers returned when making a GET request to the resource |

#### Returns

[`CheckRootContainerSuccess`](../classes/CheckRootContainerSuccess.md)

CheckRootContainerSuccess if there is not error

#### Defined in

[packages/connected-solid/src/requester/requests/checkRootContainer.ts:35](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/checkRootContainer.ts#L35)
