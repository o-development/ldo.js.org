# Interface: SolidConnectedPlugin

## Hierarchy

- `ConnectedPlugin`\<``"solid"``, [`SolidUri`](../types/SolidUri.md), [`SolidLeaf`](../classes/SolidLeaf.md) \| [`SolidContainer`](../classes/SolidContainer.md), [`SolidConnectedContext`](SolidConnectedContext.md), `undefined`\>

  ↳ **`SolidConnectedPlugin`**

## Properties

### getResource

• **getResource**: (`uri`: [`SolidLeafUri`](../types/SolidLeafUri.md), `context`: `ConnectedContext`\<[`SolidConnectedPlugin`](SolidConnectedPlugin.md)[]\>) => [`SolidLeaf`](../classes/SolidLeaf.md) \| (`uri`: [`SolidContainerUri`](../types/SolidContainerUri.md), `context`: `ConnectedContext`\<[`SolidConnectedPlugin`](SolidConnectedPlugin.md)[]\>) => [`SolidContainer`](../classes/SolidContainer.md)

#### Overrides

ConnectedPlugin.getResource

#### Defined in

[packages/connected-solid/src/SolidConnectedPlugin.ts:22](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/SolidConnectedPlugin.ts#L22)

___

### initialContext

• **initialContext**: [`SolidConnectedContext`](SolidConnectedContext.md)

#### Inherited from

ConnectedPlugin.initialContext

#### Defined in

packages/connected/dist/ConnectedPlugin.d.ts:10

___

### name

• **name**: ``"solid"``

#### Overrides

ConnectedPlugin.name

#### Defined in

[packages/connected-solid/src/SolidConnectedPlugin.ts:21](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/SolidConnectedPlugin.ts#L21)

___

### normalizeUri

• `Optional` **normalizeUri**: (`uri`: [`SolidUri`](../types/SolidUri.md)) => [`SolidUri`](../types/SolidUri.md)

#### Type declaration

▸ (`uri`): [`SolidUri`](../types/SolidUri.md)

##### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | [`SolidUri`](../types/SolidUri.md) |

##### Returns

[`SolidUri`](../types/SolidUri.md)

#### Inherited from

ConnectedPlugin.normalizeUri

#### Defined in

packages/connected/dist/ConnectedPlugin.d.ts:9

___

### types

• **types**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `context` | [`SolidConnectedContext`](SolidConnectedContext.md) |
| `createResourceOptions` | `undefined` |
| `resource` | [`SolidContainer`](../classes/SolidContainer.md) \| [`SolidLeaf`](../classes/SolidLeaf.md) |
| `uri` | [`SolidUri`](../types/SolidUri.md) |

#### Inherited from

ConnectedPlugin.types

#### Defined in

packages/connected/dist/ConnectedPlugin.d.ts:11

## Methods

### createResource

▸ **createResource**(`context`): `Promise`\<[`SolidLeaf`](../classes/SolidLeaf.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](SolidConnectedPlugin.md)[]\> |

#### Returns

`Promise`\<[`SolidLeaf`](../classes/SolidLeaf.md)\>

#### Overrides

ConnectedPlugin.createResource

#### Defined in

[packages/connected-solid/src/SolidConnectedPlugin.ts:28](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/SolidConnectedPlugin.ts#L28)

___

### isUriValid

▸ **isUriValid**(`uri`): uri is SolidUri

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |

#### Returns

uri is SolidUri

#### Inherited from

ConnectedPlugin.isUriValid

#### Defined in

packages/connected/dist/ConnectedPlugin.d.ts:8
