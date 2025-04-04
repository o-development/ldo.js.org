# Class: HttpErrorResult\<ResourceType\>

An error caused by an HTTP request

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceError`\<`ResourceType`\>

  ↳ **`HttpErrorResult`**

  ↳↳ [`UnexpectedHttpError`](UnexpectedHttpError.md)

  ↳↳ [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)

  ↳↳ [`UnauthorizedHttpError`](UnauthorizedHttpError.md)

  ↳↳ [`NotFoundHttpError`](NotFoundHttpError.md)

  ↳↳ [`ServerHttpError`](ServerHttpError.md)

## Constructors

### constructor

• **new HttpErrorResult**\<`ResourceType`\>(`resource`, `response`, `message?`): [`HttpErrorResult`](HttpErrorResult.md)\<`ResourceType`\>

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

[`HttpErrorResult`](HttpErrorResult.md)\<`ResourceType`\>

#### Overrides

ResourceError\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:39](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L39)

## Properties

### headers

• `Readonly` **headers**: `Headers`

Headers returned by the HTTP request

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:27](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L27)

___

### isError

• `Readonly` **isError**: ``true``

#### Inherited from

ResourceError.isError

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:5

___

### resource

• `Readonly` **resource**: `ResourceType`

#### Inherited from

ResourceError.resource

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:10

___

### response

• `Readonly` **response**: `Response`

Response returned by the HTTP request

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:32](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L32)

___

### status

• `Readonly` **status**: `number`

The status of the HTTP request

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:22](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L22)

___

### type

• `Readonly` `Abstract` **type**: `string`

#### Inherited from

ResourceError.type

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:4

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceError.uri

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

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:70](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L70)

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

#### Defined in

[packages/connected-solid/src/requester/results/error/HttpErrorResult.ts:55](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/HttpErrorResult.ts#L55)
