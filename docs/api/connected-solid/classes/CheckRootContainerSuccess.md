# Class: CheckRootContainerSuccess

Indicates that the request to check if a resource is the root container was
a success.

## Hierarchy

- `ResourceSuccess`\<[`SolidContainer`](SolidContainer.md)\>

  ↳ **`CheckRootContainerSuccess`**

## Constructors

### constructor

• **new CheckRootContainerSuccess**(`resource`, `isRootContainer`): [`CheckRootContainerSuccess`](CheckRootContainerSuccess.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](SolidContainer.md) |
| `isRootContainer` | `boolean` |

#### Returns

[`CheckRootContainerSuccess`](CheckRootContainerSuccess.md)

#### Overrides

ResourceSuccess\&lt;SolidContainer\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts:15](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts#L15)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

ResourceSuccess.isError

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:5

___

### isRootContainer

• **isRootContainer**: `boolean`

True if this resoure is the root container

#### Defined in

[packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts:13](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts#L13)

___

### resource

• **resource**: [`SolidContainer`](SolidContainer.md)

#### Inherited from

ResourceSuccess.resource

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:9

___

### type

• **type**: ``"checkRootContainerSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts:9](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts#L9)

___

### uri

• **uri**: [`SolidContainerUri`](../types/SolidContainerUri.md)

#### Inherited from

ResourceSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
