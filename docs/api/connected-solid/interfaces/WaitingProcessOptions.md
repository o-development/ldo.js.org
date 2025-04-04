# Interface: WaitingProcessOptions\<Args, Return\>

Options for processes that are waiting to execute

## Type parameters

| Name | Type |
| :------ | :------ |
| `Args` | extends `any`[] |
| `Return` | `Return` |

## Properties

### after

• `Optional` **after**: (`result`: `Return`) => `void`

#### Type declaration

▸ (`result`): `void`

##### Parameters

| Name | Type |
| :------ | :------ |
| `result` | `Return` |

##### Returns

`void`

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:50](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L50)

___

### args

• **args**: `Args`

The arguements supplied to the process

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:29](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L29)

___

### modifyQueue

• **modifyQueue**: (`processQueue`: [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\>[], `currentlyProcessing`: `undefined` \| [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\>, `args`: `Args`) => `undefined` \| [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\>

A custom function to modify the queue based on the current state of the
queue

#### Type declaration

▸ (`processQueue`, `currentlyProcessing`, `args`): `undefined` \| [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\>

##### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `processQueue` | [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\>[] | The current process queue |
| `currentlyProcessing` | `undefined` \| [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\> | The Process that is currently executing |
| `args` | `Args` | provided args |

##### Returns

`undefined` \| [`WaitingProcess`](WaitingProcess.md)\<`any`[], `any`\>

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:45](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L45)

___

### name

• **name**: `string`

The name of the process like "read" or "delete"

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:25](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L25)

___

### perform

• **perform**: (...`args`: `Args`) => `Promise`\<`Return`\>

A function that will be triggered when it's time to execute this process

#### Type declaration

▸ (`...args`): `Promise`\<`Return`\>

##### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `...args` | `Args` | arguments supplied to the process |

##### Returns

`Promise`\<`Return`\>

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:35](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L35)
