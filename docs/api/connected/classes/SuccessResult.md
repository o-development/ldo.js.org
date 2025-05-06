# Class: SuccessResult

Indicates that some action taken by LDO was a success

## Hierarchy

- **`SuccessResult`**

  ↳ [`ResourceSuccess`](ResourceSuccess.md)

  ↳ [`AggregateSuccess`](AggregateSuccess.md)

  ↳ [`UpdateDefaultGraphSuccess`](UpdateDefaultGraphSuccess.md)

## Implements

- [`ConnectedResult`](../interfaces/ConnectedResult.md)

## Constructors

### constructor

• **new SuccessResult**(): [`SuccessResult`](SuccessResult.md)

#### Returns

[`SuccessResult`](SuccessResult.md)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Implementation of

[ConnectedResult](../interfaces/ConnectedResult.md).[isError](../interfaces/ConnectedResult.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### type

• `Readonly` `Abstract` **type**: `string`

#### Implementation of

[ConnectedResult](../interfaces/ConnectedResult.md).[type](../interfaces/ConnectedResult.md#type)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:8](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L8)
