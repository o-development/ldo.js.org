# Interface: CreateSolidLdoDatasetOptions

Options for createSolidDataset

## Properties

### dataset

• `Optional` **dataset**: `Dataset`\<`Quad`, `Quad`\>

An initial dataset

**`Default`**

```ts
A blank dataset
```

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:22](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/createSolidLdoDataset.ts#L22)

___

### datasetFactory

• `Optional` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

An RDFJS DatasetFactory

**`Default`**

```ts
An extended RDFJS DatasetFactory
```

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:27](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/createSolidLdoDataset.ts#L27)

___

### fetch

• `Optional` **fetch**: (`input`: `RequestInfo` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>(`input`: `string` \| `Request` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>

A fetch function. Most often, this is the fetch function from @inrupt/solid-clieht-authn-js

#### Type declaration

▸ (`input`, `init?`): `Promise`\<`Response`\>

A fetch function. Most often, this is the fetch function from @inrupt/solid-clieht-authn-js

##### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `RequestInfo` \| `URL` |
| `init?` | `RequestInit` |

##### Returns

`Promise`\<`Response`\>

▸ (`input`, `init?`): `Promise`\<`Response`\>

A fetch function. Most often, this is the fetch function from @inrupt/solid-clieht-authn-js

##### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `string` \| `Request` \| `URL` |
| `init?` | `RequestInit` |

##### Returns

`Promise`\<`Response`\>

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:17](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/createSolidLdoDataset.ts#L17)
