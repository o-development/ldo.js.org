# Class: ContainerBatchedRequester

A singleton to handle batched requests for containers

## Hierarchy

- [`BatchedRequester`](BatchedRequester.md)\<[`SolidContainer`](SolidContainer.md)\>

  ↳ **`ContainerBatchedRequester`**

## Constructors

### constructor

• **new ContainerBatchedRequester**(`resource`, `context`): [`ContainerBatchedRequester`](ContainerBatchedRequester.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidContainer`](SolidContainer.md) | - |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> | ConnectedContext of the parent dataset |

#### Returns

[`ContainerBatchedRequester`](ContainerBatchedRequester.md)

#### Overrides

[BatchedRequester](BatchedRequester.md).[constructor](BatchedRequester.md#constructor)

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:31](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L31)

## Properties

### context

• `Protected` **context**: `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\>

ConnectedContext for the parent Dataset

#### Inherited from

[BatchedRequester](BatchedRequester.md).[context](BatchedRequester.md#context)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:49](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L49)

___

### requestBatcher

• `Protected` `Readonly` **requestBatcher**: [`RequestBatcher`](RequestBatcher.md)

A request batcher to maintain state for ongoing requests

#### Inherited from

[BatchedRequester](BatchedRequester.md).[requestBatcher](BatchedRequester.md#requestbatcher)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:38](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L38)

___

### resource

• `Readonly` **resource**: [`SolidContainer`](SolidContainer.md)

The URI of the container

#### Overrides

[BatchedRequester](BatchedRequester.md).[resource](BatchedRequester.md#resource)

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:25](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L25)

## Methods

### createDataResource

▸ **createDataResource**(`overwrite`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

Creates the container

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `overwrite` | ``true`` | If true, this will orverwrite the resource if it already exists |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

#### Overrides

[BatchedRequester](BatchedRequester.md).[createDataResource](BatchedRequester.md#createdataresource)

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:52](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L52)

▸ **createDataResource**(`overwrite?`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `overwrite?` | ``false`` |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

#### Overrides

[BatchedRequester](BatchedRequester.md).[createDataResource](BatchedRequester.md#createdataresource)

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:55](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L55)

▸ **createDataResource**(`overwrite?`): `Promise`\<[`ContainerReadSuccess`](ContainerReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidContainer`](SolidContainer.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `overwrite?` | `boolean` |

#### Returns

`Promise`\<[`ContainerReadSuccess`](ContainerReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidContainer`](SolidContainer.md)\>\>

#### Overrides

[BatchedRequester](BatchedRequester.md).[createDataResource](BatchedRequester.md#createdataresource)

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:56](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L56)

___

### delete

▸ **delete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md)\>\>

Delete this resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md)\>\>

A DeleteResult

#### Inherited from

[BatchedRequester](BatchedRequester.md).[delete](BatchedRequester.md#delete)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:118](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L118)

___

### isCreating

▸ **isCreating**(): `boolean`

Checks if the resource is currently executing a create request

#### Returns

`boolean`

true if the resource is currently executing a create request

#### Inherited from

[BatchedRequester](BatchedRequester.md).[isCreating](BatchedRequester.md#iscreating)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:70](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L70)

___

### isDeletinng

▸ **isDeletinng**(): `boolean`

Checks if the resource is currently executing a delete request

#### Returns

`boolean`

true if the resource is currently executing a delete request

#### Inherited from

[BatchedRequester](BatchedRequester.md).[isDeletinng](BatchedRequester.md#isdeletinng)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:86](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L86)

___

### isLoading

▸ **isLoading**(): `boolean`

Checks if the resource is currently making any request

#### Returns

`boolean`

true if the resource is making any requests

#### Inherited from

[BatchedRequester](BatchedRequester.md).[isLoading](BatchedRequester.md#isloading)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:62](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L62)

___

### isReading

▸ **isReading**(): `boolean`

Checks if the resource is currently executing a read request

#### Returns

`boolean`

true if the resource is currently executing a read request

#### Inherited from

[BatchedRequester](BatchedRequester.md).[isReading](BatchedRequester.md#isreading)

#### Defined in

[packages/connected-solid/src/requester/BatchedRequester.ts:78](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/BatchedRequester.ts#L78)

___

### isRootContainer

▸ **isRootContainer**(): `Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

Checks to see if this container is a root container

#### Returns

`Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

A CheckRootResult

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:73](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L73)

___

### read

▸ **read**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

Reads the container

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

A ReadContainerResult

#### Overrides

[BatchedRequester](BatchedRequester.md).[read](BatchedRequester.md#read)

#### Defined in

[packages/connected-solid/src/requester/ContainerBatchedRequester.ts:43](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/ContainerBatchedRequester.ts#L43)
