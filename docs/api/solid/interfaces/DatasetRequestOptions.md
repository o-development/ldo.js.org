# Interface: DatasetRequestOptions

Request options with a dataset component

## Hierarchy

- [`BasicRequestOptions`](BasicRequestOptions.md)

  ↳ **`DatasetRequestOptions`**

## Properties

### dataset

• `Optional` **dataset**: `IBulkEditableDataset`\<`Quad`\>

A dataset to be modified with any new information obtained from a request

#### Defined in

[packages/solid/src/requester/requests/requestOptions.ts:21](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/requestOptions.ts#L21)

___

### fetch

• `Optional` **fetch**: (`input`: `RequestInfo` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>(`input`: `string` \| `Request` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>

A fetch function usually imported from @inrupt/solid-client-authn-js

#### Type declaration

▸ (`input`, `init?`): `Promise`\<`Response`\>

A fetch function usually imported from @inrupt/solid-client-authn-js

##### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `RequestInfo` \| `URL` |
| `init?` | `RequestInit` |

##### Returns

`Promise`\<`Response`\>

▸ (`input`, `init?`): `Promise`\<`Response`\>

A fetch function usually imported from @inrupt/solid-client-authn-js

##### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `string` \| `Request` \| `URL` |
| `init?` | `RequestInit` |

##### Returns

`Promise`\<`Response`\>

#### Inherited from

[BasicRequestOptions](BasicRequestOptions.md).[fetch](BasicRequestOptions.md#fetch)

#### Defined in

[packages/solid/src/requester/requests/requestOptions.ts:11](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/requester/requests/requestOptions.ts#L11)
