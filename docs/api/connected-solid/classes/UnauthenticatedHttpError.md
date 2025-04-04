# Class: UnauthenticatedHttpError\<ResourceType\>

An UnauthenticatedHttpError triggers when a Solid server returns a 401 status
indicating that the request is not authenticated.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- [`HttpErrorResult`](HttpErrorResult.md)\<`ResourceType`\>

  ↳ **`UnauthenticatedHttpError`**

## Constructors

### constructor

• **new UnauthenticatedHttpError**\<`ResourceType`\>(`resource`, `response`, `message?`): [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | `ResourceType` | the resource |
| `response` | `Response` | The response returned by the HTTP requests |
| `message?` | `string` | A custom message for the error |

#### Returns

[`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<`ResourceType`\>

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[constructor](HttpErrorResult.md#constructor)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:39](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L39)

## Properties

### headers

• `Readonly` **headers**: `Headers`

Headers returned by the HTTP request

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[headers](HttpErrorResult.md#headers)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:27](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L27)

___

### isError

• `Readonly` **isError**: ``true``

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[isError](HttpErrorResult.md#iserror)

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:5

___

### resource

• `Readonly` **resource**: `ResourceType`

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[resource](HttpErrorResult.md#resource)

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:10

___

### response

• `Readonly` **response**: `Response`

Response returned by the HTTP request

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[response](HttpErrorResult.md#response)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:32](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L32)

___

### status

• `Readonly` **status**: `number`

The status of the HTTP request

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[status](HttpErrorResult.md#status)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:22](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L22)

___

### type

• `Readonly` **type**: ``"unauthenticatedError"``

#### Overrides

[HttpErrorResult](HttpErrorResult.md).[type](HttpErrorResult.md#type)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:107](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L107)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[uri](HttpErrorResult.md#uri)

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:9

## Methods

### checkResponse

▸ **checkResponse**\<`ResourceType`\>(`resource`, `response`): `undefined` \| [`HttpErrorResultType`](../types/HttpErrorResultType.md)\<`ResourceType`\>

Checks a given response to see if it is a ServerHttpError, an
UnauthenticatedHttpError or a some unexpected error.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | `ResourceType` | - |
| `response` | `Response` | The response of the request |

#### Returns

`undefined` \| [`HttpErrorResultType`](../types/HttpErrorResultType.md)\<`ResourceType`\>

An error if the response calls for it. Undefined if not.

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[checkResponse](HttpErrorResult.md#checkresponse)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:70](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L70)

___

### is

▸ **is**(`response`): `boolean`

Indicates if a specific response constitutes an UnauthenticatedHttpError

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `response` | `Response` | The request response |

#### Returns

`boolean`

true if this response constitutes an UnauthenticatedHttpError

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:114](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L114)

___

### isnt

▸ **isnt**(`response`): `boolean`

Checks to see if a given response does not constitute an HTTP Error

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `response` | `Response` | The response of the request |

#### Returns

`boolean`

true if the response does not constitute an HTTP Error

#### Inherited from

[HttpErrorResult](HttpErrorResult.md).[isnt](HttpErrorResult.md#isnt)

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:55](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L55)
