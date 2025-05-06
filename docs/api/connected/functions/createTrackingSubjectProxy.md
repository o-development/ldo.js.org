# Function: createTrackingSubjectProxy

▸ **createTrackingSubjectProxy**(`proxyContext`, `node`): `SubjectProxy`

Creates a tracking proxy for a single value, a proxy that tracks the fields
that have been accessed.

#### Parameters

| Name | Type |
| :------ | :------ |
| `proxyContext` | [`TrackingProxyContext`](../classes/TrackingProxyContext.md) |
| `node` | `BlankNode` \| `NamedNode`\<`string`\> |

#### Returns

`SubjectProxy`

#### Defined in

[packages/connected/src/trackingProxy/TrackingSubjectProxy.ts:16](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/trackingProxy/TrackingSubjectProxy.ts#L16)
