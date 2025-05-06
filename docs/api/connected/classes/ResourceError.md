# Class: ResourceError\<ResourceType\>

An error for a specific resource

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`ErrorResult`](ErrorResult.md)

  ↳ **`ResourceError`**

  ↳↳ [`UnexpectedResourceError`](UnexpectedResourceError.md)

  ↳↳ [`InvalidUriError`](InvalidUriError.md)

  ↳↳ [`UnsupportedNotificationError`](UnsupportedNotificationError.md)

  ↳↳ [`DisconnectedAttemptingReconnectError`](DisconnectedAttemptingReconnectError.md)

  ↳↳ [`DisconnectedNotAttemptingReconnectError`](DisconnectedNotAttemptingReconnectError.md)

## Constructors

### constructor

• **new ResourceError**\<`ResourceType`\>(`resource`, `message?`): [`ResourceError`](ResourceError.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md)\<`string`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | `ResourceType` | - |
| `message?` | `string` | A custom message for the error |

#### Returns

[`ResourceError`](ResourceError.md)\<`ResourceType`\>

#### Overrides

[ErrorResult](ErrorResult.md).[constructor](ErrorResult.md#constructor)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:46](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L46)

## Properties

### isError

• `Readonly` **isError**: ``true``

Always true

#### Inherited from

[ErrorResult](ErrorResult.md).[isError](ErrorResult.md#iserror)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:16](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L16)

___

### message

• **message**: `string`

#### Inherited from

[ErrorResult](ErrorResult.md).[message](ErrorResult.md#message)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1077

___

### name

• **name**: `string`

#### Inherited from

[ErrorResult](ErrorResult.md).[name](ErrorResult.md#name)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1076

___

### resource

• `Readonly` **resource**: `ResourceType`

The resource that failed

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:40](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L40)

___

### stack

• `Optional` **stack**: `string`

#### Inherited from

[ErrorResult](ErrorResult.md).[stack](ErrorResult.md#stack)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1078

___

### type

• `Readonly` `Abstract` **type**: `string`

Indicates the specific type of error

#### Inherited from

[ErrorResult](ErrorResult.md).[type](ErrorResult.md#type)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:11](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L11)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:35](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L35)

___

### prepareStackTrace

▪ `Static` `Optional` **prepareStackTrace**: (`err`: `Error`, `stackTraces`: `CallSite`[]) => `any`

Optional override for formatting stack traces

**`See`**

https://v8.dev/docs/stack-trace-api#customizing-stack-traces

#### Type declaration

▸ (`err`, `stackTraces`): `any`

##### Parameters

| Name | Type |
| :------ | :------ |
| `err` | `Error` |
| `stackTraces` | `CallSite`[] |

##### Returns

`any`

#### Inherited from

[ErrorResult](ErrorResult.md).[prepareStackTrace](ErrorResult.md#preparestacktrace)

#### Defined in

node_modules/@types/node/globals.d.ts:98

___

### stackTraceLimit

▪ `Static` **stackTraceLimit**: `number`

#### Inherited from

[ErrorResult](ErrorResult.md).[stackTraceLimit](ErrorResult.md#stacktracelimit)

#### Defined in

node_modules/@types/node/globals.d.ts:100

## Methods

### captureStackTrace

▸ **captureStackTrace**(`targetObject`, `constructorOpt?`): `void`

Create .stack property on a target object

#### Parameters

| Name | Type |
| :------ | :------ |
| `targetObject` | `object` |
| `constructorOpt?` | `Function` |

#### Returns

`void`

#### Inherited from

[ErrorResult](ErrorResult.md).[captureStackTrace](ErrorResult.md#capturestacktrace)

#### Defined in

node_modules/@types/node/globals.d.ts:91
