# Class: Unfetched\<ResourceType\>

Indicates that a specific resource is unfetched

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`ResourceSuccess`](ResourceSuccess.md)\<`ResourceType`\>

  ↳ **`Unfetched`**

## Constructors

### constructor

• **new Unfetched**\<`ResourceType`\>(`resource`): [`Unfetched`](Unfetched.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md)\<`string`\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | `ResourceType` |

#### Returns

[`Unfetched`](Unfetched.md)\<`ResourceType`\>

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[constructor](ResourceSuccess.md#constructor)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:27](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L27)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[isError](ResourceSuccess.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### resource

• **resource**: `ResourceType`

The resource that was successful

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[resource](ResourceSuccess.md#resource)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:25](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L25)

___

### type

• `Readonly` **type**: ``"unfetched"``

#### Overrides

[ResourceSuccess](ResourceSuccess.md).[type](ResourceSuccess.md#type)

#### Defined in

[packages/connected/src/results/success/Unfetched.ts:10](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/Unfetched.ts#L10)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[uri](ResourceSuccess.md#uri)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:21](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L21)
