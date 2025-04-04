# Class: AbsentReadSuccess\<ResourceType\>

Indicates that the read request was successful, but no resource exists at
the provided URI.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`ReadSuccess`](ReadSuccess.md)\<`ResourceType`\>

  ↳ **`AbsentReadSuccess`**

## Constructors

### constructor

• **new AbsentReadSuccess**\<`ResourceType`\>(`resource`, `recalledFromMemory`): [`AbsentReadSuccess`](AbsentReadSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md)\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |
| `recalledFromMemory` | `boolean` |

#### Returns

[`AbsentReadSuccess`](AbsentReadSuccess.md)\<`ResourceType`\>

#### Inherited from

[ReadSuccess](ReadSuccess.md).[constructor](ReadSuccess.md#constructor)

#### Defined in

[packages/connected/src/results/success/ReadSuccess.ts:16](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/ReadSuccess.ts#L16)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[ReadSuccess](ReadSuccess.md).[isError](ReadSuccess.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### recalledFromMemory

• **recalledFromMemory**: `boolean`

True if the resource was recalled from local memory rather than a recent
request

#### Inherited from

[ReadSuccess](ReadSuccess.md).[recalledFromMemory](ReadSuccess.md#recalledfrommemory)

#### Defined in

[packages/connected/src/results/success/ReadSuccess.ts:14](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/ReadSuccess.ts#L14)

___

### resource

• **resource**: `ResourceType`

The resource that was successful

#### Inherited from

[ReadSuccess](ReadSuccess.md).[resource](ReadSuccess.md#resource)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:25](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L25)

___

### type

• **type**: ``"absentReadSuccess"``

#### Overrides

[ReadSuccess](ReadSuccess.md).[type](ReadSuccess.md#type)

#### Defined in

[packages/connected/src/results/success/ReadSuccess.ts:29](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/ReadSuccess.ts#L29)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Inherited from

[ReadSuccess](ReadSuccess.md).[uri](ReadSuccess.md#uri)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:21](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L21)
