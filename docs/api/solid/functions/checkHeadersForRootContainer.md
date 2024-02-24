# Function: checkHeadersForRootContainer

▸ **checkHeadersForRootContainer**(`uri`, `headers`): `CheckRootContainerSuccess` \| `NoncompliantPodError`

Checks provided headers to see if a given URI is a root container as defined
in the [solid specification section 4.1](https://solidproject.org/TR/protocol#storage-resource)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) | the URI of the container resource |
| `headers` | `Headers` | headers returned when making a GET request to the resource |

#### Returns

`CheckRootContainerSuccess` \| `NoncompliantPodError`

CheckRootContainerSuccess if there is not error

#### Defined in

[packages/solid/src/requester/requests/checkRootContainer.ts:37](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/requests/checkRootContainer.ts#L37)
