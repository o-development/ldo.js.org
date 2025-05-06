# Type alias: LQReturnSubSet\<Type, Input\>

Ƭ **LQReturnSubSet**\<`Type`, `Input`\>: `Input` extends [`LQInputSubSet`](LQInputSubSet.md)\<`Type`\> ? `Input` extends [`LQInputObject`](LQInputObject.md)\<`Type`\> ? `Input` extends ``true`` ? `Type` : [`LQReturnObject`](LQReturnObject.md)\<`Type`, `Input`\> : `Type` : `never`

#### Type parameters

| Name |
| :------ |
| `Type` |
| `Input` |

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:61](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L61)
