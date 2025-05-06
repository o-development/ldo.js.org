# Interface: TrackingProxyContextOptions

Options to be passed to the tracking proxy

## Hierarchy

- `ProxyContextOptions`

  ↳ **`TrackingProxyContextOptions`**

## Properties

### contextUtil

• **contextUtil**: `ContextUtil`

#### Inherited from

ProxyContextOptions.contextUtil

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:10

___

### dataset

• **dataset**: `SubscribableDataset`\<`Quad`\>

#### Overrides

ProxyContextOptions.dataset

#### Defined in

[packages/connected/src/trackingProxy/TrackingProxyContext.ts:21](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingProxyContext.ts#L21)

___

### languageOrdering

• **languageOrdering**: `LanguageOrdering`

#### Inherited from

ProxyContextOptions.languageOrdering

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:12

___

### state

• `Optional` **state**: `Record`\<`string`, `unknown`\>

#### Inherited from

ProxyContextOptions.state

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:13

___

### writeGraphs

• **writeGraphs**: `GraphNode`[]

#### Inherited from

ProxyContextOptions.writeGraphs

#### Defined in

packages/jsonld-dataset-proxy/dist/ProxyContext.d.ts:11
