# Class: ResourceSuccess\<ResourceType\>

Indicates that a request to a resource was aa success

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`SuccessResult`](SuccessResult.md)

  ↳ **`ResourceSuccess`**

  ↳↳ [`Unfetched`](Unfetched.md)

  ↳↳ [`ReadSuccess`](ReadSuccess.md)

  ↳↳ [`UpdateSuccess`](UpdateSuccess.md)

  ↳↳ [`IgnoredInvalidUpdateSuccess`](IgnoredInvalidUpdateSuccess.md)

## Constructors

### constructor

• **new ResourceSuccess**\<`ResourceType`\>(`resource`): [`ResourceSuccess`](ResourceSuccess.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md)\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |

#### Returns

[`ResourceSuccess`](ResourceSuccess.md)\<`ResourceType`\>

#### Overrides

[SuccessResult](SuccessResult.md).[constructor](SuccessResult.md#constructor)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:27](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L27)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[SuccessResult](SuccessResult.md).[isError](SuccessResult.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### resource

• **resource**: `ResourceType`

The resource that was successful

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:25](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L25)

___

### type

• `Readonly` `Abstract` **type**: `string`

#### Inherited from

[SuccessResult](SuccessResult.md).[type](SuccessResult.md#type)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:8](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L8)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:21](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L21)
