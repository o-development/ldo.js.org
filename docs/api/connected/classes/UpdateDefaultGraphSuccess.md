# Class: UpdateDefaultGraphSuccess

Indicates that an update request to the default graph was successful. This
data was not written to a Pod. It was only written locally.

## Hierarchy

- [`SuccessResult`](SuccessResult.md)

  ↳ **`UpdateDefaultGraphSuccess`**

## Constructors

### constructor

• **new UpdateDefaultGraphSuccess**(): [`UpdateDefaultGraphSuccess`](UpdateDefaultGraphSuccess.md)

#### Returns

[`UpdateDefaultGraphSuccess`](UpdateDefaultGraphSuccess.md)

#### Inherited from

[SuccessResult](SuccessResult.md).[constructor](SuccessResult.md#constructor)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[SuccessResult](SuccessResult.md).[isError](SuccessResult.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### type

• **type**: ``"updateDefaultGraphSuccess"``

#### Overrides

[SuccessResult](SuccessResult.md).[type](SuccessResult.md#type)

#### Defined in

[packages/connected/src/results/success/UpdateSuccess.ts:18](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/UpdateSuccess.ts#L18)
