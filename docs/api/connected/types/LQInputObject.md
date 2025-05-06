# Type alias: LQInputObject\<Type\>

Ƭ **LQInputObject**\<`Type`\>: `Partial`\<\{ [key in Exclude\<keyof Type, "@context"\>]: LQInputFlattenSet\<Type[key]\> }\>

#### Type parameters

| Name |
| :------ |
| `Type` |

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:15](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L15)
