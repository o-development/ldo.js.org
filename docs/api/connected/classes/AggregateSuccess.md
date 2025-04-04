# Class: AggregateSuccess\<SuccessType\>

A grouping of multiple successes as a result of an action

## Type parameters

| Name | Type |
| :------ | :------ |
| `SuccessType` | extends [`SuccessResult`](SuccessResult.md) |

## Hierarchy

- [`SuccessResult`](SuccessResult.md)

  ↳ **`AggregateSuccess`**

## Constructors

### constructor

• **new AggregateSuccess**\<`SuccessType`\>(`results`): [`AggregateSuccess`](AggregateSuccess.md)\<`SuccessType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `SuccessType` | extends [`SuccessResult`](SuccessResult.md) |

#### Parameters

| Name | Type |
| :------ | :------ |
| `results` | `SuccessType`[] |

#### Returns

[`AggregateSuccess`](AggregateSuccess.md)\<`SuccessType`\>

#### Overrides

[SuccessResult](SuccessResult.md).[constructor](SuccessResult.md#constructor)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:47](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L47)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[SuccessResult](SuccessResult.md).[isError](SuccessResult.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### results

• **results**: `SuccessType`[]

An array of all successesses

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:45](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L45)

___

### type

• **type**: ``"aggregateSuccess"``

#### Overrides

[SuccessResult](SuccessResult.md).[type](SuccessResult.md#type)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:40](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L40)
