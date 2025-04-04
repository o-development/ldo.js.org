# Function: guaranteeFetch

▸ **guaranteeFetch**(`fetchInput?`): typeof [`__type`](../interfaces/SolidConnectedContext.md#__type)

Guantees that some kind of fetch is available

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `fetchInput?` | (`input`: `RequestInfo` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\>(`input`: `string` \| `Request` \| `URL`, `init?`: `RequestInit`) => `Promise`\<`Response`\> | [MDN Reference](https://developer.mozilla.org/docs/Web/API/fetch) |

#### Returns

typeof [`__type`](../interfaces/SolidConnectedContext.md#__type)

a proper fetch object. Cross-fetch is default

#### Defined in

[packages/connected-solid/src/util/guaranteeFetch.ts:10](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/guaranteeFetch.ts#L10)
