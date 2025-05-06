# Class: InvalidUriError\<ResourceType\>

An InvalidUriError is returned when a URI was provided that is not a valid
URI.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`ResourceError`](ResourceError.md)\<`ResourceType`\>

  ↳ **`InvalidUriError`**

## Constructors

### constructor

• **new InvalidUriError**\<`ResourceType`\>(`resource`, `message?`): [`InvalidUriError`](InvalidUriError.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md)\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |
| `message?` | `string` |

#### Returns

[`InvalidUriError`](InvalidUriError.md)\<`ResourceType`\>

#### Overrides

[ResourceError](ResourceError.md).[constructor](ResourceError.md#constructor)

#### Defined in

[packages/connected/src/results/error/InvalidUriError.ts:13](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/InvalidUriError.ts#L13)

## Properties

### isError

• `Readonly` **isError**: ``true``

Always true

#### Inherited from

[ResourceError](ResourceError.md).[isError](ResourceError.md#iserror)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:16](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L16)

___

### message

• **message**: `string`

#### Inherited from

[ResourceError](ResourceError.md).[message](ResourceError.md#message)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1077

___

### name

• **name**: `string`

#### Inherited from

[ResourceError](ResourceError.md).[name](ResourceError.md#name)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1076

___

### resource

• `Readonly` **resource**: `ResourceType`

The resource that failed

#### Inherited from

[ResourceError](ResourceError.md).[resource](ResourceError.md#resource)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:40](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L40)

___

### stack

• `Optional` **stack**: `string`

#### Inherited from

[ResourceError](ResourceError.md).[stack](ResourceError.md#stack)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1078

___

### type

• `Readonly` **type**: ``"invalidUriError"``

Indicates the specific type of error

#### Overrides

[ResourceError](ResourceError.md).[type](ResourceError.md#type)

#### Defined in

[packages/connected/src/results/error/InvalidUriError.ts:11](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/InvalidUriError.ts#L11)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Inherited from

[ResourceError](ResourceError.md).[uri](ResourceError.md#uri)

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

[ResourceError](ResourceError.md).[prepareStackTrace](ResourceError.md#preparestacktrace)

#### Defined in

node_modules/@types/node/globals.d.ts:98

___

### stackTraceLimit

▪ `Static` **stackTraceLimit**: `number`

#### Inherited from

[ResourceError](ResourceError.md).[stackTraceLimit](ResourceError.md#stacktracelimit)

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

[ResourceError](ResourceError.md).[captureStackTrace](ResourceError.md#capturestacktrace)

#### Defined in

node_modules/@types/node/globals.d.ts:91
