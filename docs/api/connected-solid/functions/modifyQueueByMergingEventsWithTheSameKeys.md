# Function: modifyQueueByMergingEventsWithTheSameKeys

▸ **modifyQueueByMergingEventsWithTheSameKeys**(`key`): (`queue`: [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>[], `currentlyLoading`: `undefined` \| [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>) => `undefined` \| [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>

A helper function for a common way to modify the batch queue. This merges
the incoming request with the currently executing request or the last request
in the queue if its keys are the same.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `key` | `string` | the key of the incoming request |

#### Returns

`fn`

a modifyQueue function

▸ (`queue`, `currentlyLoading`): `undefined` \| [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `queue` | [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>[] |
| `currentlyLoading` | `undefined` \| [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\> |

##### Returns

`undefined` \| [`WaitingProcess`](../interfaces/WaitingProcess.md)\<`any`[], `any`\>

#### Defined in

[packages/connected-solid/src/requester/util/modifyQueueFuntions.ts:14](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/util/modifyQueueFuntions.ts#L14)
