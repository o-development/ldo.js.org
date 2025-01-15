# Interface: SolidLdoDatasetContext

Context to be shared between aspects of a SolidLdoDataset

## Properties

### fetch

• **fetch**: (`input`: `RequestInfo` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>(`input`: `string` \| `Request` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>

Http fetch function

#### Type declaration

▸ (`input`, `init?`): `Promise`\<`Response`\>

Http fetch function

##### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `RequestInfo` \| `URL` |
| `init?` | `RequestInit` |

##### Returns

`Promise`\<`Response`\>

▸ (`input`, `init?`): `Promise`\<`Response`\>

Http fetch function

##### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `string` \| `Request` \| `URL` |
| `init?` | `RequestInit` |

##### Returns

`Promise`\<`Response`\>

#### Defined in

[packages/solid/src/SolidLdoDatasetContext.ts:19](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDatasetContext.ts#L19)

___

### resourceStore

• **resourceStore**: `ResourceStore`

The resource store of the SolidLdoDataset

#### Defined in

[packages/solid/src/SolidLdoDatasetContext.ts:15](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDatasetContext.ts#L15)

___

### solidLdoDataset

• **solidLdoDataset**: [`SolidLdoDataset`](../classes/SolidLdoDataset.md)

A pointer to the parent SolidLdoDataset

#### Defined in

[packages/solid/src/SolidLdoDatasetContext.ts:11](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/SolidLdoDatasetContext.ts#L11)
