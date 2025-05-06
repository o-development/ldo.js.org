# Class: ReadSuccess\<ResourceType\>

Indicates that the request to read a resource was a success

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends [`Resource`](../interfaces/Resource.md) |

## Hierarchy

- [`ResourceSuccess`](ResourceSuccess.md)\<`ResourceType`\>

  ↳ **`ReadSuccess`**

  ↳↳ [`AbsentReadSuccess`](AbsentReadSuccess.md)

## Constructors

### constructor

• **new ReadSuccess**\<`ResourceType`\>(`resource`, `recalledFromMemory`): [`ReadSuccess`](ReadSuccess.md)\<`ResourceType`\>

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

[`ReadSuccess`](ReadSuccess.md)\<`ResourceType`\>

#### Overrides

[ResourceSuccess](ResourceSuccess.md).[constructor](ResourceSuccess.md#constructor)

#### Defined in

[packages/connected/src/results/success/ReadSuccess.ts:16](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/ReadSuccess.ts#L16)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[isError](ResourceSuccess.md#iserror)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:9](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L9)

___

### recalledFromMemory

• **recalledFromMemory**: `boolean`

True if the resource was recalled from local memory rather than a recent
request

#### Defined in

[packages/connected/src/results/success/ReadSuccess.ts:14](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/ReadSuccess.ts#L14)

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

• `Readonly` `Abstract` **type**: `string`

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[type](ResourceSuccess.md#type)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:8](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L8)

___

### uri

• **uri**: `ResourceType`[``"uri"``]

The URI of the resource

#### Inherited from

[ResourceSuccess](ResourceSuccess.md).[uri](ResourceSuccess.md#uri)

#### Defined in

[packages/connected/src/results/success/SuccessResult.ts:21](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/results/success/SuccessResult.ts#L21)
