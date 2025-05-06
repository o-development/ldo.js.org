# Function: createTrackingProxyBuilder

▸ **createTrackingProxyBuilder**\<`Type`\>(`dataset`, `shapeType`, `onUpdate`): `LdoBuilder`\<`Type`\>

Creates a Linked Data Object builder that when creating linked data objects
it tracks when something that was read from it is updated and triggers some
action based on that.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `dataset` | `LdoDataset` |
| `shapeType` | `ShapeType`\<`Type`\> |
| `onUpdate` | `nodeEventListener`\<`Quad`\> |

#### Returns

`LdoBuilder`\<`Type`\>

#### Defined in

[packages/connected/src/trackingProxy/createTrackingProxy.ts:18](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/createTrackingProxy.ts#L18)
