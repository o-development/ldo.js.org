# Interface: ConnectedPlugin\<Name, UriType, ResourceType, ContextType, CreateResourceOptions\>

A ConnectedPlugin can be passed to a ConnectedDataset to allow it to connect
to a remote platform.

## Type parameters

| Name | Type |
| :------ | :------ |
| `Name` | extends `string` = `any` |
| `UriType` | extends `string` = `any` |
| `ResourceType` | extends [`Resource`](Resource.md)\<`UriType`\> = `any` |
| `ContextType` | `any` |
| `CreateResourceOptions` | `any` |

## Properties

### initialContext

• **initialContext**: `ContextType`

A starting context

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:55](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L55)

___

### name

• **name**: `Name`

The name of the plugin ("solid" for example).

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:20](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L20)

___

### normalizeUri

• `Optional` **normalizeUri**: (`uri`: `UriType`) => `UriType`

Optional function that takes in a URI and returns a normalized uri. For
example `https://example.com/profile#me` becomes
`https://example.com/profile`.

#### Type declaration

▸ (`uri`): `UriType`

##### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `UriType` | The uri to normalize |

##### Returns

`UriType`

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:51](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L51)

___

### types

• **types**: `Object`

This object exists to transfer typescript types. It does not need to be
filled out in an actual instance.

#### Type declaration

| Name | Type |
| :------ | :------ |
| `context` | `ContextType` |
| `createResourceOptions` | `CreateResourceOptions` |
| `resource` | `ResourceType` |
| `uri` | `UriType` |

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:60](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L60)

## Methods

### createResource

▸ **createResource**(`context`, `createResourceOptions?`): `Promise`\<[`ErrorResult`](../classes/ErrorResult.md) \| `ResourceType`\>

A function that will create a resource on the remote at a random URI.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | [`ConnectedContext`](../types/ConnectedContext.md)\<[`ConnectedPlugin`](ConnectedPlugin.md)\<`Name`, `UriType`, `ResourceType`, `ContextType`, `CreateResourceOptions`\>[]\> | the context for the plugin |
| `createResourceOptions?` | `CreateResourceOptions` | special options for creating a resource that varies based on the plugin |

#### Returns

`Promise`\<[`ErrorResult`](../classes/ErrorResult.md) \| `ResourceType`\>

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:34](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L34)

___

### getResource

▸ **getResource**(`uri`, `context`): `ResourceType`

A function that returns a newly minted resource on this platform. This
function does not fetch the resource or interface with a cache.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `UriType` | The uri of the resource |
| `context` | [`ConnectedContext`](../types/ConnectedContext.md)\<[`ConnectedPlugin`](ConnectedPlugin.md)\<`Name`, `UriType`, `ResourceType`, `ContextType`, `CreateResourceOptions`\>[]\> | The context for the plugin |

#### Returns

`ResourceType`

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:27](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L27)

___

### isUriValid

▸ **isUriValid**(`uri`): uri is UriType

Checks if a specific uri is valid for this plugin

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | `string` | the URI to check |

#### Returns

uri is UriType

true if this is a valid URI

#### Defined in

[packages/connected/src/types/ConnectedPlugin.ts:43](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ConnectedPlugin.ts#L43)
