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

[packages/solid/src/createSolidLdoDataset.ts:21](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/createSolidLdoDataset.ts#L21)

___

### datasetFactory

• `Optional` **datasetFactory**: `DatasetFactory`\<`Quad`, `Quad`, `Dataset`\<`Quad`, `Quad`\>\>

An RDFJS DatasetFactory

**`Default`**

```ts
An extended RDFJS DatasetFactory
```

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:26](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/createSolidLdoDataset.ts#L26)

___

### fetch

• `Optional` **fetch**: (`input`: `RequestInfo` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>

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

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:16](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/createSolidLdoDataset.ts#L16)
