# Type alias: ReadResultError\<ResourceType\>

Ƭ **ReadResultError**\<`ResourceType`\>: [`HttpErrorResultType`](HttpErrorResultType.md)\<`ResourceType`\> \| [`NoncompliantPodError`](../classes/NoncompliantPodError.md)\<`ResourceType`\> \| [`UnexpectedHttpError`](../classes/UnexpectedHttpError.md)\<`ResourceType`\> \| `UnexpectedResourceError`\<`ResourceType`\>

All possible errors the readResource function can return

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

#### Defined in

[packages/connected-solid/src/requester/requests/readResource.ts:45](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/requests/readResource.ts#L45)
