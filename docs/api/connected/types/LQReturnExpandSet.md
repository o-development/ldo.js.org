# Type alias: LQReturnExpandSet\<Type, Input\>

Ƭ **LQReturnExpandSet**\<`Type`, `Input`\>: `NonNullable`\<`Type`\> extends `LdSet`\<infer SetSubType\> ? `LdSet`\<[`LQReturnSubSet`](LQReturnSubSet.md)\<`SetSubType`, `Input`\>\> : [`LQReturnSubSet`](LQReturnSubSet.md)\<`Type`, `Input`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | `Type` |
| `Input` | extends [`LQInputFlattenSet`](LQInputFlattenSet.md)\<`Type`\> |

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:69](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L69)
