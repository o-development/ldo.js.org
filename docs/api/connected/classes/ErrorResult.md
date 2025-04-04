# Class: ErrorResult

A result indicating that the request failed in some kind of way

## Hierarchy

- `Error`

  ↳ **`ErrorResult`**

  ↳↳ [`ResourceError`](ResourceError.md)

  ↳↳ [`AggregateError`](AggregateError.md)

## Implements

- [`ConnectedResult`](../interfaces/ConnectedResult.md)

## Constructors

### constructor

• **new ErrorResult**(`message?`): [`ErrorResult`](ErrorResult.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `message?` | `string` | a custom message for the error |

#### Returns

[`ErrorResult`](ErrorResult.md)

#### Overrides

Error.constructor

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:21](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/error/ErrorResult.ts#L21)

## Properties

### isError

• `Readonly` **isError**: ``true``

Always true

#### Implementation of

[ConnectedResult](../interfaces/ConnectedResult.md).[isError](../interfaces/ConnectedResult.md#iserror)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:16](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/error/ErrorResult.ts#L16)

___

### message

• **message**: `string`

#### Inherited from

Error.message

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1077

___

### name

• **name**: `string`

#### Inherited from

Error.name

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1076

___

### stack

• `Optional` **stack**: `string`

#### Inherited from

Error.stack

#### Defined in

node_modules/typescript/lib/lib.es5.d.ts:1078

___

### type

• `Readonly` `Abstract` **type**: `string`

Indicates the specific type of error

#### Implementation of

[ConnectedResult](../interfaces/ConnectedResult.md).[type](../interfaces/ConnectedResult.md#type)

#### Defined in

[packages/connected/src/results/error/ErrorResult.ts:11](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/error/ErrorResult.ts#L11)

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

Error.prepareStackTrace

#### Defined in

node_modules/@types/node/globals.d.ts:98

___

### stackTraceLimit

▪ `Static` **stackTraceLimit**: `number`

#### Inherited from

Error.stackTraceLimit

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

Error.captureStackTrace

#### Defined in

node_modules/@types/node/globals.d.ts:91
