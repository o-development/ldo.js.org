# Type alias: LQReturnObject\<Type, Input\>

Ƭ **LQReturnObject**\<`Type`, `Input`\>: \{ [key in Exclude\<keyof Required\<Type\>, "@context"\> as undefined extends Input[key] ? never : key]: Input[key] extends LQInputFlattenSet\<Type[key]\> ? undefined extends Type[key] ? LQReturnExpandSet\<Type[key], Input[key]\> \| undefined : LQReturnExpandSet\<Type[key], Input[key]\> : never }

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | `Type` |
| `Input` | extends [`LQInputObject`](LQInputObject.md)\<`Type`\> |

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:48](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L48)
