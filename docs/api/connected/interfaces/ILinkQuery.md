# Interface: ILinkQuery\<Type, Input\>

## Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `Input` | extends [`LQInput`](../types/LQInput.md)\<`Type`\> |

## Implemented by

- [`ResourceLinkQuery`](../classes/ResourceLinkQuery.md)

## Methods

### fromSubject

▸ **fromSubject**(): [`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `Input`\>\>

#### Returns

[`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `Input`\>\>

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:96](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L96)

___

### run

▸ **run**(`options?`): `Promise`\<[`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `Input`\>\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `options?` | [`LinkQueryRunOptions`](LinkQueryRunOptions.md) |

#### Returns

`Promise`\<[`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `Input`\>\>\>

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:90](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L90)

___

### subscribe

▸ **subscribe**(): `Promise`\<`string`\>

#### Returns

`Promise`\<`string`\>

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:93](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L93)

___

### unsubscribe

▸ **unsubscribe**(`subscriptionId`): `Promise`\<`void`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `subscriptionId` | `string` |

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:94](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L94)

___

### unsubscribeAll

▸ **unsubscribeAll**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:95](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L95)
