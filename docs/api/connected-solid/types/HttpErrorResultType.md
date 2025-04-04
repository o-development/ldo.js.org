# Type alias: HttpErrorResultType\<ResourceType\>

Ƭ **HttpErrorResultType**\<`ResourceType`\>: [`ServerHttpError`](../classes/ServerHttpError.md)\<`ResourceType`\> \| [`UnexpectedHttpError`](../classes/UnexpectedHttpError.md)\<`ResourceType`\> \| [`UnauthenticatedHttpError`](../classes/UnauthenticatedHttpError.md)\<`ResourceType`\> \| [`UnauthorizedHttpError`](../classes/UnauthorizedHttpError.md)\<`ResourceType`\>

A set of standard errors that can be returned as a result of an HTTP request

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:7](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L7)
