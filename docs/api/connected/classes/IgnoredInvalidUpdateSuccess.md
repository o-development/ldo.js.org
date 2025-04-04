# Class: IgnoredInvalidUpdateSuccess\<ResourceType\>

Indicates that LDO ignored an invalid update (usually because a container
attempted an update)

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`ResourceSuccess`](ResourceSuccess.md)\<`ResourceType`\>

  ↳ **`IgnoredInvalidUpdateSuccess`**

## Constructors

### constructor

• **new IgnoredInvalidUpdateSuccess**\<`ResourceType`\>(`resource`): [`IgnoredInvalidUpdateSuccess`](IgnoredInvalidUpdateSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md)\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |

#### Returns

[`IgnoredInvalidUpdateSuccess`](IgnoredInvalidUpdateSuccess.md)\<`ResourceType`\>

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[constructor](ResourceSuccess.md#constructor)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:27](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L27)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[isError](ResourceSuccess.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### resource

• **resource**: `ResourceType`

The resource that was successful

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[resource](ResourceSuccess.md#resource)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:25](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L25)

___

### type

• **type**: ``"ignoredInvalidUpdateSuccess"``

#### Overrides

[ResourceSuccess](ResourceSuccess.md).[type](ResourceSuccess.md#type)

#### Defined in

[packages/connected/src/results/success/UpdateSuccess.ts:28](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/UpdateSuccess.ts#L28)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[uri](ResourceSuccess.md#uri)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:21](https://github.com/o-development/ldo/blob/0518c5c7483d8344bdec226a595a6c39a34f346f/packages/connected/src/results/success/SuccessResult.ts#L21)
