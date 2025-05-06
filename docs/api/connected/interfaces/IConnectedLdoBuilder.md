# Interface: IConnectedLdoBuilder\<Type, Plugins\>

## Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `Plugins` | extends [`ConnectedPlugin`](ConnectedPlugin.md)[] |

## Hierarchy

- `LdoBuilder`\<`Type`\>

  ↳ **`IConnectedLdoBuilder`**

## Implemented by

- [`ConnectedLdoBuilder`](../classes/ConnectedLdoBuilder.md)

## Properties

### jsonldDatasetProxyBuilder

• `Protected` **jsonldDatasetProxyBuilder**: `JsonldDatasetProxyBuilder`

#### Inherited from

LdoBuilder.jsonldDatasetProxyBuilder

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:6

___

### shapeType

• `Protected` **shapeType**: `ShapeType`\<`Type`\>

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

#### Inherited from

LdoBuilder.setLanguagePreferences

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:14

___

### startLinkQuery

▸ **startLinkQuery**\<`Input`\>(`startingResource`, `startingSubject`, `linkQueryInput`): [`ILinkQuery`](ILinkQuery.md)\<`Type`, `Input`\>

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

[`ILinkQuery`](ILinkQuery.md)\<`Type`, `Input`\>

#### Defined in

[packages/connected/src/types/IConnectedLdoBuilder.ts:10](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/IConnectedLdoBuilder.ts#L10)

___

### write

▸ **write**(`...graphs`): `LdoBuilder`\<`Type`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `...graphs` | (`string` \| `GraphNode`)[] |

#### Returns

`LdoBuilder`\<`Type`\>

#### Inherited from

LdoBuilder.write

#### Defined in

packages/ldo/dist/LdoBuilder.d.ts:13
