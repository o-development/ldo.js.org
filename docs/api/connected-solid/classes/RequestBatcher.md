# Class: RequestBatcher

A utility for batching a request

## Constructors

### constructor

• **new RequestBatcher**(`options?`): [`RequestBatcher`](RequestBatcher.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Partial`\<\{ `batchMillis`: `number`  }\> | options, including the value for batchMillis |

#### Returns

[`RequestBatcher`](RequestBatcher.md)

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:83](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L83)

## Properties

### batchMillis

• **batchMillis**: `number`

The amount of time (in milliseconds) between requests of the same key

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:78](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L78)

___

### currentlyProcessing

• `Private` **currentlyProcessing**: `undefined` \| [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\> = `undefined`

A pointer to the current process the batcher is working on

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:67](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L67)

___

### lastRequestTimestampMap

• `Private` **lastRequestTimestampMap**: `Record`\<`string`, `number`\> = `{}`

A mapping between a process key and the last time in UTC a process of that
key was executed.

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:62](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L62)

___

### processQueue

• `Private` **processQueue**: [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>[] = `[]`

A queue of upcoming processes

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:73](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L73)

## Methods

### isLoading

▸ **isLoading**(`key`): `boolean`

Check if the request batcher is currently working on a process

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `key` | `string` | the key of the process to check |

#### Returns

`boolean`

true if the batcher is currently working on the provided process

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:96](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L96)

___

### queueProcess

▸ **queueProcess**\<`Args`, `ReturnType`\>(`options`): `Promise`\<`ReturnType`\>

Adds a process to the queue and waits for the process to be complete

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Args` | extends `any`[] |
| `ReturnType` | `ReturnType` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options` | [`WaitingProcessOptions`](../interfaces/WaitingProcessOptions.md)\<`Args`, `ReturnType`\> | WaitingProcessOptions |

#### Returns

`Promise`\<`ReturnType`\>

A promise that resolves when the process resolves

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:161](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L161)

___

### triggerOrWaitProcess

▸ **triggerOrWaitProcess**(): `void`

Triggers the next process in the queue or triggers a timeout to wait to
execute the next process in the queue if not enough time has passed since
the last process was triggered.

#### Returns

`void`

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:106](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L106)
