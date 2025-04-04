# Class: LeafBatchedRequester

A singleton to handle batched requests for leafs

## Hierarchy

- [`BatchedRequester`](BatchedRequester.md)\<[`SolidLeaf`](SolidLeaf.md)\>

  ↳ **`LeafBatchedRequester`**

## Constructors

### constructor

• **new LeafBatchedRequester**(`resource`, `context`): [`LeafBatchedRequester`](LeafBatchedRequester.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | [`SolidLeaf`](SolidLeaf.md) | - |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> | SolidLdoDatasetContext of the parent dataset |

#### Returns

[`LeafBatchedRequester`](LeafBatchedRequester.md)

#### Overrides

[BatchedRequester](BatchedRequester.md).[constructor](BatchedRequester.md#constructor)

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:35](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L35)

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

• `Readonly` **resource**: [`SolidLeaf`](SolidLeaf.md)

The URI of the leaf

#### Overrides

[BatchedRequester](BatchedRequester.md).[resource](BatchedRequester.md#resource)

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:29](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L29)

## Methods

### createDataResource

▸ **createDataResource**(`overwrite`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Creates the leaf as a data resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `overwrite` | ``true`` | If true, this will orverwrite the resource if it already exists |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Overrides

[BatchedRequester](BatchedRequester.md).[createDataResource](BatchedRequester.md#createdataresource)

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:72](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L72)

▸ **createDataResource**(`overwrite?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `overwrite?` | ``false`` |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Overrides

[BatchedRequester](BatchedRequester.md).[createDataResource](BatchedRequester.md#createdataresource)

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:73](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L73)

▸ **createDataResource**(`overwrite?`): `Promise`\<[`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `overwrite?` | `boolean` |

#### Returns

`Promise`\<[`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Overrides

[BatchedRequester](BatchedRequester.md).[createDataResource](BatchedRequester.md#createdataresource)

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:74](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L74)

___

### delete

▸ **delete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

Delete this resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

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

### isUpdating

▸ **isUpdating**(): `boolean`

Checks if the resource is currently executing an update request

#### Returns

`boolean`

true if the resource is currently executing an update request

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:47](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L47)

___

### isUploading

▸ **isUploading**(): `boolean`

Checks if the resource is currently executing an upload request

#### Returns

`boolean`

true if the resource is currently executing an upload request

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:55](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L55)

___

### read

▸ **read**(): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

Reads the leaf

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

A ReadLeafResult

#### Overrides

[BatchedRequester](BatchedRequester.md).[read](BatchedRequester.md#read)

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:63](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L63)

___

### updateDataResource

▸ **updateDataResource**(`changes`): `Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

Update the data on this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> | DatasetChanges that should be applied to the Pod |

#### Returns

`Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:89](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L89)

___

### upload

▸ **upload**(`blob`, `mimeType`, `overwrite`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Upload a binary at this resource's URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `blob` | `Blob` | A binary blob |
| `mimeType` | `string` | the mime type of the blob |
| `overwrite` | ``true`` | - |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:122](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L122)

▸ **upload**(`blob`, `mimeType`, `overwrite?`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | ``false`` |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:127](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L127)

▸ **upload**(`blob`, `mimeType`, `overwrite?`): `Promise`\<[`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | `boolean` |

#### Returns

`Promise`\<[`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Defined in

[packages/connected-solid/src/requester/LeafBatchedRequester.ts:132](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/LeafBatchedRequester.ts#L132)
