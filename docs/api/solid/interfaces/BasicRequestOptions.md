# Interface: BasicRequestOptions

Request Options to be passed to request functions

## Hierarchy

- **`BasicRequestOptions`**

  ↳ [`DatasetRequestOptions`](DatasetRequestOptions.md)

## Properties

### fetch

• `Optional` **fetch**: (`input`: `RequestInfo` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>

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

#### Defined in

[packages/solid/src/requester/requests/requestOptions.ts:11](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/requester/requests/requestOptions.ts#L11)
