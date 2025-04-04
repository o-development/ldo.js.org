# Class: NoRootContainerError\<ResourceType\>

A NoncompliantPodError is returned when the server responded in a way that is
not compliant with the Solid specification.

## Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource` |

## Hierarchy

- `ResourceError`\<`ResourceType`\>

  ↳ **`NoRootContainerError`**

## Constructors

### constructor

• **new NoRootContainerError**\<`ResourceType`\>(`resource`): [`NoRootContainerError`](NoRootContainerError.md)\<`ResourceType`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `ResourceType` | extends `Resource`\<`string`\> |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `resource` | `ResourceType` | the requested resource |

#### Returns

[`NoRootContainerError`](NoRootContainerError.md)\<`ResourceType`\>

#### Overrides

ResourceError\&lt;ResourceType\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/error/NoRootContainerError.ts:17](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/NoRootContainerError.ts#L17)

## Properties

### isError

• `Readonly` **isError**: ``true``

#### Inherited from

ResourceError.isError

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:5

___

### resource

• `Readonly` **resource**: `ResourceType`

#### Inherited from

ResourceError.resource

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:10

___

### type

• `Readonly` **type**: ``"noRootContainerError"``

#### Overrides

ResourceError.type

#### Defined in

[packages/connected-solid/src/requester/results/error/NoRootContainerError.ts:11](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/error/NoRootContainerError.ts#L11)

___

### uri

• `Readonly` **uri**: `ResourceType`[``"uri"``]

#### Inherited from

ResourceError.uri

#### Defined in

packages/connected/dist/results/error/ErrorResult.d.ts:9
