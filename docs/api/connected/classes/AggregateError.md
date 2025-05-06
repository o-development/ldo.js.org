# Class: AggregateError\<ErrorType\>

An error that aggregates many errors

## Type parameters

| Name | Type |
| :------ | :------ |
| `ErrorType` | extends [`ErrorResult`](ErrorResult.md) |

## Hierarchy

- [`ErrorResult`](ErrorResult.md)

  ↳ **`AggregateError`**

## Constructors

### constructor

• **new AggregateError**\<`ErrorType`\>(`errors`, `message?`): [`AggregateError`](AggregateError.md)\<`ErrorType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ErrorType` | extends [`ErrorResult`](ErrorResult.md) |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `errors` | (`ErrorType` \| [`AggregateError`](AggregateError.md)\<`ErrorType`\>)[] | List of all errors returned |
| `message?` | `string` | A custom message for the error |

#### Returns

[`AggregateError`](AggregateError.md)\<`ErrorType`\>

#### Overrides

[ErrorResult](ErrorResult.md).[constructor](ErrorResult.md#constructor)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:68](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L68)

## Properties

### errors

• `Readonly` **errors**: `ErrorType`[]

A list of all errors returned

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:62](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L62)

___

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

### stack

• `Optional` **stack**: `string`

#### Inherited from

[ErrorResult](ErrorResult.md).[stack](ErrorResult.md#stack)

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1078

___

### type

• `Readonly` **type**: ``"aggregateError"``

Indicates the specific type of error

#### Overrides

[ErrorResult](ErrorResult.md).[type](ErrorResult.md#type)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:57](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/error/ErrorResult.ts#L57)

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
