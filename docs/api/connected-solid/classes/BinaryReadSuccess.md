# Class: BinaryReadSuccess

Indicates that the read request was successful and that the resource
retrieved was a binary resource.

## Hierarchy

- `ReadSuccess`\<[`SolidLeaf`](SolidLeaf.md)\>

  ↳ **`BinaryReadSuccess`**

## Constructors

### constructor

• **new BinaryReadSuccess**(`resource`, `recalledFromMemory`, `blob`, `mimeType`): [`BinaryReadSuccess`](BinaryReadSuccess.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `resource` | [`SolidLeaf`](SolidLeaf.md) |
| `recalledFromMemory` | `boolean` |
| `blob` | `Blob` |
| `mimeType` | `string` |

#### Returns

[`BinaryReadSuccess`](BinaryReadSuccess.md)

#### Overrides

ReadSuccess\&lt;SolidLeaf\&gt;.constructor

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:21](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L21)

## Properties

### blob

• **blob**: `Blob`

The raw data for the binary resource

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:15](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L15)

___

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

ReadSuccess.isError

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:5

___

### mimeType

• **mimeType**: `string`

The mime type of the binary resource

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:19](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L19)

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

• **type**: ``"binaryReadSuccess"``

#### Overrides

ReadSuccess.type

#### Defined in

[packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts:11](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/SolidReadSuccess.ts#L11)

___

### uri

• **uri**: [`SolidLeafUri`](../types/SolidLeafUri.md)

#### Inherited from

ReadSuccess.uri

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:8
