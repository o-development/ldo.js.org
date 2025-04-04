# Class: BatchedRequester\<ResourceType\>

A singleton for handling batched requests

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |

## Hierarchy

- **`BatchedRequester`**

  ↳ [`ContainerBatchedRequester`](ContainerBatchedRequester.md)

  ↳ [`LeafBatchedRequester`](LeafBatchedRequester.md)

## Constructors

### constructor

• **new BatchedRequester**\<`ResourceType`\>(`context`): [`BatchedRequester`](BatchedRequester.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md) |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> | SolidLdoDatasetContext for the parent SolidLdoDataset |

#### Returns

[`BatchedRequester`](BatchedRequester.md)\<`ResourceType`\>

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:54](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L54)

## Properties

### context

• `Protected` **context**: `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\>

ConnectedContext for the parent Dataset

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:49](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L49)

___

### requestBatcher

• `Protected` `Readonly` **requestBatcher**: [`RequestBatcher`](RequestBatcher.md)

A request batcher to maintain state for ongoing requests

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:38](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L38)

___

### resource

• `Readonly` `Abstract` **resource**: `ResourceType`

The uri of the resource

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:43](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L43)

## Methods

### createDataResource

▸ **createDataResource**(`overwrite`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Creates a Resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `overwrite` | ``true`` | If true, this will orverwrite the resource if it already exists |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

A ContainerCreateAndOverwriteResult or a
LeafCreateAndOverwriteResult depending on this resource's URI

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:144](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L144)

▸ **createDataResource**(`overwrite?`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `overwrite?` | ``false`` |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:147](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L147)

▸ **createDataResource**(`overwrite?`): `Promise`\<[`ContainerReadSuccess`](ContainerReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `overwrite?` | `boolean` |

#### Returns

`Promise`\<[`ContainerReadSuccess`](ContainerReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:150](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L150)

___

### delete

▸ **delete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<`ResourceType`\>\>

Delete this resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<`ResourceType`\>\>

A DeleteResult

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:118](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L118)

___

### isCreating

▸ **isCreating**(): `boolean`

Checks if the resource is currently executing a create request

#### Returns

`boolean`

true if the resource is currently executing a create request

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:70](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L70)

___

### isDeletinng

▸ **isDeletinng**(): `boolean`

Checks if the resource is currently executing a delete request

#### Returns

`boolean`

true if the resource is currently executing a delete request

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:86](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L86)

___

### isLoading

▸ **isLoading**(): `boolean`

Checks if the resource is currently making any request

#### Returns

`boolean`

true if the resource is making any requests

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:62](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L62)

___

### isReading

▸ **isReading**(): `boolean`

Checks if the resource is currently executing a read request

#### Returns

`boolean`

true if the resource is currently executing a read request

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:78](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L78)

___

### read

▸ **read**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

Read this resource.

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

A ReadLeafResult or a ReadContainerResult depending on the uri of
this resource

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:95](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L95)
