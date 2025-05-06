# Type alias: ExpandDeep\<T\>

Ƭ **ExpandDeep**\<`T`\>: `T` extends `LdSet`\<infer U\> ? `LdSet`\<[`ExpandDeep`](ExpandDeep.md)\<`U`\>\> : `T` extends `object` ? \{ [K in keyof T]: ExpandDeep\<T[K]\> } : `T`

#### Type parameters

| Name |
| :------ |
| `T` |

#### Defined in

[packages/connected/src/types/ILinkQuery.ts:76](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/types/ILinkQuery.ts#L76)
