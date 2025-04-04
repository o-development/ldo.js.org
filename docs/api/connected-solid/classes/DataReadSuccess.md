# Class: DataReadSuccess

Indicates that the read request was successful and that the resource
retrieved was a data (RDF) resource.

## Hierarchy

- `ReadSuccess`\<[`SolidLeaf`](SolidLeaf.md)\>

  ↳ **`DataReadSuccess`**

## Constructors

### constructor

• **new DataReadSuccess**(`resource`, `recalledFromMemory`): [`DataReadSuccess`](DataReadSuccess.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidLeaf`](SolidLeaf.md) |
| `recalledFromMemory` | `boolean` |

#### Returns

[`DataReadSuccess`](DataReadSuccess.md)

#### Inherited from

ReadSuccess\<SolidLeaf\>.constructor

#### Defined in

packages/connected/dist/results/success/ReadSuccess.d.ts:5

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

ReadSuccess.isError

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:5

___

### recalledFromMemory

• **recalledFromMemory**: `boolean`

#### Inherited from

ReadSuccess.recalledFromMemory

#### Defined in

packages/connected/dist/results/success/ReadSuccess.d.ts:4

___

### resource

• **resource**: [`SolidLeaf`](SolidLeaf.md)

#### Inherited from

ReadSuccess.resource

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:9

___

### type

• **type**: ``"dataReadSuccess"``

#### Overrides

ReadSuccess.type

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:38](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L38)

___

### uri

• **uri**: [`SolidLeafUri`](../types/SolidLeafUri.md)

#### Inherited from

ReadSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
