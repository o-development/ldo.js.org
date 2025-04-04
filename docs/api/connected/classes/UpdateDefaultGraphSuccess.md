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

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### type

• **type**: ``"updateDefaultGraphSuccess"``

#### Overrides

[SuccessResult](SuccessResult.md).[type](SuccessResult.md#type)

#### Defined in

[packages/connected/src/results/success/UpdateSuccess.ts:18](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/UpdateSuccess.ts#L18)
