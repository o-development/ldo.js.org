# Class: ConnectedLdoBuilder\<Type, Plugins\>

## Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)[] |

## Hierarchy

- `LdoBuilder`\<`Type`\>

  ↳ **`ConnectedLdoBuilder`**

## Implements

- [`IConnectedLdoBuilder`](../interfaces/IConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

## Constructors

### constructor

• **new ConnectedLdoBuilder**\<`Type`, `Plugins`\>(`parentDataset`, `jsonldDatasetProxyBuilder`, `shapeType`): [`ConnectedLdoBuilder`](ConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type |
| :------ | :------ |
| `parentDataset` | [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\> |
| `jsonldDatasetProxyBuilder` | `JsonldDatasetProxyBuilder` |
| `shapeType` | `ShapeType`\<`Type`\> |

#### Returns

[`ConnectedLdoBuilder`](ConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

#### Overrides

LdoBuilder\&lt;Type\&gt;.constructor

#### Defined in

[packages/connected/src/ConnectedLdoBuilder.ts:20](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoBuilder.ts#L20)

## Properties

### jsonldDatasetProxyBuilder

• `Protected` **jsonldDatasetProxyBuilder**: `JsonldDatasetProxyBuilder`

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[jsonldDatasetProxyBuilder](../interfaces/IConnectedLdoBuilder.md#jsonlddatasetproxybuilder)

#### Inherited from

LdoBuilder.jsonldDatasetProxyBuilder

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:6

___

### parentDataset

• `Protected` **parentDataset**: [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\>

#### Defined in

[packages/connected/src/ConnectedLdoBuilder.ts:18](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoBuilder.ts#L18)

___

### shapeType

• `Protected` **shapeType**: `ShapeType`\<`Type`\>

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[shapeType](../interfaces/IConnectedLdoBuilder.md#shapetype)

#### Inherited from

LdoBuilder.shapeType

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:7

## Methods

### fromJson

▸ **fromJson**(`inputData`): `Type`

#### Parameters

| Name | Type |
| :------ | :------ |
| `inputData` | `Type` |

#### Returns

`Type`

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[fromJson](../interfaces/IConnectedLdoBuilder.md#fromjson)

#### Inherited from

LdoBuilder.fromJson

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:12

___

### fromSubject

▸ **fromSubject**(`subject`): `Type`

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject` | `string` \| `SubjectNode` |

#### Returns

`Type`

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[fromSubject](../interfaces/IConnectedLdoBuilder.md#fromsubject)

#### Inherited from

LdoBuilder.fromSubject

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:9

___

### matchObject

▸ **matchObject**(`subject?`, `predicate?`, `graph?`): `LdSet`\<`Type`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `subject?` | ``null`` \| `string` \| `SubjectNode` |
| `predicate?` | ``null`` \| `string` \| `PredicateNode` |
| `graph?` | ``null`` \| `string` \| `GraphNode` |

#### Returns

`LdSet`\<`Type`\>

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[matchObject](../interfaces/IConnectedLdoBuilder.md#matchobject)

#### Inherited from

LdoBuilder.matchObject

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:11

___

### matchSubject

▸ **matchSubject**(`predicate`, `object?`, `graph?`): `LdSet`\<`Type`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `predicate` | `undefined` \| ``null`` \| `string` \| `PredicateNode` |
| `object?` | ``null`` \| `string` \| `ObjectNode` |
| `graph?` | ``null`` \| `string` \| `GraphNode` |

#### Returns

`LdSet`\<`Type`\>

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[matchSubject](../interfaces/IConnectedLdoBuilder.md#matchsubject)

#### Inherited from

LdoBuilder.matchSubject

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:10

___

### setLanguagePreferences

▸ **setLanguagePreferences**(`...languageOrdering`): `LdoBuilder`\<`Type`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `...languageOrdering` | `LanguageOrdering` |

#### Returns

`LdoBuilder`\<`Type`\>

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[setLanguagePreferences](../interfaces/IConnectedLdoBuilder.md#setlanguagepreferences)

#### Inherited from

LdoBuilder.setLanguagePreferences

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:14

___

### startLinkQuery

▸ **startLinkQuery**\<`Input`\>(`startingResource`, `startingSubject`, `linkQueryInput`): [`ResourceLinkQuery`](ResourceLinkQuery.md)\<`Type`, `Input`, `Plugins`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Input` | extends `Partial`\<\{ [key in string \| number \| symbol]: LQInputFlattenSet\<Type[key]\> }\> |

#### Parameters

| Name | Type |
| :------ | :------ |
| `startingResource` | `Plugins`[`number`][``"types"``][``"resource"``] |
| `startingSubject` | `string` \| `SubjectNode` |
| `linkQueryInput` | `Input` |

#### Returns

[`ResourceLinkQuery`](ResourceLinkQuery.md)\<`Type`, `Input`, `Plugins`\>

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[startLinkQuery](../interfaces/IConnectedLdoBuilder.md#startlinkquery)

#### Defined in

[packages/connected/src/ConnectedLdoBuilder.ts:29](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/ConnectedLdoBuilder.ts#L29)

___

### write

▸ **write**(`...graphs`): `LdoBuilder`\<`Type`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `...graphs` | (`string` \| `GraphNode`)[] |

#### Returns

`LdoBuilder`\<`Type`\>

#### Implementation of

[IConnectedLdoBuilder](../interfaces/IConnectedLdoBuilder.md).[write](../interfaces/IConnectedLdoBuilder.md#write)

#### Inherited from

LdoBuilder.write

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:13
