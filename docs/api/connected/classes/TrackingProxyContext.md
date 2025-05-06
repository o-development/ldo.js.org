# Class: TrackingProxyContext

This proxy exists to ensure react components rerender at the right time. It
keeps track of every key accessed in a Linked Data Object and only when the
dataset is updated with that key does it rerender the react component.

## Hierarchy

- `ProxyContext`

  ↳ **`TrackingProxyContext`**

## Constructors

### constructor

• **new TrackingProxyContext**(`options`, `listener`): [`TrackingProxyContext`](TrackingProxyContext.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `options` | [`TrackingProxyContextOptions`](../interfaces/TrackingProxyContextOptions.md) |
| `listener` | `nodeEventListener`\<`Quad`\> |

#### Returns

[`TrackingProxyContext`](TrackingProxyContext.md)

#### Overrides

ProxyContext.constructor

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:39](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L39)

## Properties

### contextUtil

• `Readonly` **contextUtil**: `ContextUtil`

#### Inherited from

ProxyContext.contextUtil

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:19

___

### dataset

• `Readonly` **dataset**: `Dataset`\<`Quad`, `Quad`\>

#### Inherited from

ProxyContext.dataset

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:18

___

### languageOrdering

• `Readonly` **languageOrdering**: `LanguageOrdering`

#### Inherited from

ProxyContext.languageOrdering

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:21

___

### listener

• `Private` **listener**: `nodeEventListener`\<`Quad`\>

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:36](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L36)

___

### state

• **state**: `Record`\<`string`, `unknown`\>

#### Inherited from

ProxyContext.state

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:22

___

### subscribableDataset

• `Private` **subscribableDataset**: `SubscribableDataset`\<`Quad`\>

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:37](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L37)

___

### writeGraphs

• `Readonly` **writeGraphs**: `GraphNode`[]

#### Inherited from

ProxyContext.writeGraphs

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:20

## Methods

### addListener

▸ **addListener**(`eventName`): `void`

#### Parameters

| Name | Type |
| :------ | :------ |
| `eventName` | `QuadMatch` |

#### Returns

`void`

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:49](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L49)

___

### createNewSetProxy

▸ **createNewSetProxy**(`quadMatch`, `isSubjectOriented?`, `isLangStringSet?`): `SetProxy`\<`NonNullable`\<`RawValue`\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `quadMatch` | `QuadMatch` |
| `isSubjectOriented?` | `boolean` |
| `isLangStringSet?` | `boolean` |

#### Returns

`SetProxy`\<`NonNullable`\<`RawValue`\>\>

#### Overrides

ProxyContext.createNewSetProxy

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:60](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L60)

___

### createNewSubjectProxy

▸ **createNewSubjectProxy**(`node`): `SubjectProxy`

#### Parameters

| Name | Type |
| :------ | :------ |
| `node` | `BlankNode` \| `NamedNode`\<`string`\> |

#### Returns

`SubjectProxy`

#### Overrides

ProxyContext.createNewSubjectProxy

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:56](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L56)

___

### createSetProxy

▸ **createSetProxy**(`quadMatch`, `isSubjectOriented?`, `isLangStringSet?`): `SetProxy`\<`NonNullable`\<`RawValue`\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `quadMatch` | `QuadMatch` |
| `isSubjectOriented?` | `boolean` |
| `isLangStringSet?` | `boolean` |

#### Returns

`SetProxy`\<`NonNullable`\<`RawValue`\>\>

#### Inherited from

ProxyContext.createSetProxy

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:27

___

### createSubjectProxy

▸ **createSubjectProxy**(`node`): `SubjectProxy`

#### Parameters

| Name | Type |
| :------ | :------ |
| `node` | `BlankNode` \| `NamedNode`\<`string`\> |

#### Returns

`SubjectProxy`

#### Inherited from

ProxyContext.createSubjectProxy

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:24

___

### duplicate

▸ **duplicate**(`alternativeOptions`): `ProxyContext`

#### Parameters

| Name | Type |
| :------ | :------ |
| `alternativeOptions` | `Partial`\<`ProxyContextOptions`\> |

#### Returns

`ProxyContext`

#### Inherited from

ProxyContext.duplicate

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:29

___

### getRdfType

▸ **getRdfType**(`subjectNode`): `NamedNode`\<`string`\>[]

#### Parameters

| Name | Type |
| :------ | :------ |
| `subjectNode` | `SubjectNode` |

#### Returns

`NamedNode`\<`string`\>[]

#### Inherited from

ProxyContext.getRdfType

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:30
