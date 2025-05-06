# Function: exploreLinks

▸ **exploreLinks**\<`Type`, `Plugins`\>(`dataset`, `shapeType`, `startingResource`, `startingSubject`, `queryInput`, `options?`): `Promise`\<`void`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type |
| :------ | :------ |
| `dataset` | [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\> |
| `shapeType` | `ShapeType`\<`Type`\> |
| `startingResource` | `Plugins`[`number`][``"types"``][``"resource"``] |
| `startingSubject` | `string` \| `SubjectNode` |
| `queryInput` | `Partial`\<\{ [key in string \| number \| symbol]: LQInputFlattenSet\<Type[key]\> }\> |
| `options?` | `ExploreLinksOptions`\<`Plugins`\> |

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/linkTraversal/exploreLinks.ts:25](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/exploreLinks.ts#L25)
