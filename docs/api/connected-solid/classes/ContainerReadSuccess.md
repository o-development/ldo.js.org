# Class: ContainerReadSuccess

Indicates that the read request was successful and that the resource
retrieved was a container resource.

## Hierarchy

- `ReadSuccess`\<[`SolidContainer`](SolidContainer.md)\>

  ↳ **`ContainerReadSuccess`**

## Constructors

### constructor

• **new ContainerReadSuccess**(`resource`, `recalledFromMemory`, `isRootContainer`): [`ContainerReadSuccess`](ContainerReadSuccess.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidContainer`](SolidContainer.md) |
| `recalledFromMemory` | `boolean` |
| `isRootContainer` | `boolean` |

#### Returns

[`ContainerReadSuccess`](ContainerReadSuccess.md)

#### Overrides

ReadSuccess\&lt;SolidContainer\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:52](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L52)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

ReadSuccess.isError

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:5

___

### isRootContainer

• **isRootContainer**: `boolean`

True if this container is a root container

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:50](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L50)

___

### recalledFromMemory

• **recalledFromMemory**: `boolean`

#### Inherited from

ReadSuccess.recalledFromMemory

#### Defined in

packages/connected/dist/results/success/ReadSuccess.d.ts:4

___

### resource

• **resource**: [`SolidContainer`](SolidContainer.md)

#### Inherited from

ReadSuccess.resource

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:9

___

### type

• **type**: ``"containerReadSuccess"``

#### Overrides

ReadSuccess.type

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:46](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L46)

___

### uri

• **uri**: [`SolidContainerUri`](../types/SolidContainerUri.md)

#### Inherited from

ReadSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
