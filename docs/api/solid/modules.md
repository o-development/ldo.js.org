[@ldo/solid](README.md) / Exports

# @ldo/solid

## Table of contents

### Classes

- [Container](classes/Container.md)
- [Leaf](classes/Leaf.md)
- [Resource](classes/Resource.md)
- [SolidLdoDataset](classes/SolidLdoDataset.md)

### Interfaces

- [BasicRequestOptions](interfaces/BasicRequestOptions.md)
- [CreateSolidLdoDatasetOptions](interfaces/CreateSolidLdoDatasetOptions.md)
- [DatasetRequestOptions](interfaces/DatasetRequestOptions.md)
- [SolidLdoDatasetContext](interfaces/SolidLdoDatasetContext.md)

### Type Aliases

- [CheckRootResult](modules.md#checkrootresult)
- [CheckRootResultError](modules.md#checkrootresulterror)
- [ContainerCreateAndOverwriteResult](modules.md#containercreateandoverwriteresult)
- [ContainerCreateIfAbsentResult](modules.md#containercreateifabsentresult)
- [ContainerUri](modules.md#containeruri)
- [CreateAndOverwriteResultErrors](modules.md#createandoverwriteresulterrors)
- [CreateErrors](modules.md#createerrors)
- [CreateIfAbsentResultErrors](modules.md#createifabsentresulterrors)
- [DeleteResult](modules.md#deleteresult)
- [DeleteResultError](modules.md#deleteresulterror)
- [LeafCreateAndOverwriteResult](modules.md#leafcreateandoverwriteresult)
- [LeafCreateIfAbsentResult](modules.md#leafcreateifabsentresult)
- [LeafUri](modules.md#leafuri)
- [ReadContainerResult](modules.md#readcontainerresult)
- [ReadLeafResult](modules.md#readleafresult)
- [ReadResultError](modules.md#readresulterror)
- [SetAccessRulesResult](modules.md#setaccessrulesresult)
- [SetAccessRulesResultError](modules.md#setaccessrulesresulterror)
- [SharedStatuses](modules.md#sharedstatuses)
- [UpdateResult](modules.md#updateresult)
- [UpdateResultError](modules.md#updateresulterror)

### Functions

- [changeData](modules.md#changedata)
- [checkHeadersForRootContainer](modules.md#checkheadersforrootcontainer)
- [checkRootContainer](modules.md#checkrootcontainer)
- [commitData](modules.md#commitdata)
- [createDataResource](modules.md#createdataresource)
- [createSolidLdoDataset](modules.md#createsolidldodataset)
- [deleteResource](modules.md#deleteresource)
- [getAccessRules](modules.md#getaccessrules)
- [isContainerUri](modules.md#iscontaineruri)
- [isLeafUri](modules.md#isleafuri)
- [readResource](modules.md#readresource)
- [setAccessRules](modules.md#setaccessrules)
- [updateDataResource](modules.md#updatedataresource)
- [uploadResource](modules.md#uploadresource)

## Type Aliases

### CheckRootResult

Ƭ **CheckRootResult**: `CheckRootContainerSuccess` \| [`CheckRootResultError`](modules.md#checkrootresulterror)

#### Defined in

[packages/solid/src/requester/requests/checkRootContainer.ts:14](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/checkRootContainer.ts#L14)

___

### CheckRootResultError

Ƭ **CheckRootResultError**: `HttpErrorResultType` \| `NoncompliantPodError` \| `UnexpectedHttpError` \| `UnexpectedResourceError`

#### Defined in

[packages/solid/src/requester/requests/checkRootContainer.ts:15](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/checkRootContainer.ts#L15)

___

### ContainerCreateAndOverwriteResult

Ƭ **ContainerCreateAndOverwriteResult**: `CreateSuccess` \| [`CreateAndOverwriteResultErrors`](modules.md#createandoverwriteresulterrors)

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:24](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L24)

___

### ContainerCreateIfAbsentResult

Ƭ **ContainerCreateIfAbsentResult**: `CreateSuccess` \| `Exclude`\<[`ReadContainerResult`](modules.md#readcontainerresult), `AbsentReadSuccess`\> \| [`CreateIfAbsentResultErrors`](modules.md#createifabsentresulterrors)

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:30](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L30)

___

### ContainerUri

Ƭ **ContainerUri**: \`$\{string}/$\{NonPathnameEnding}\`

#### Defined in

[packages/solid/src/util/uriTypes.ts:1](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/util/uriTypes.ts#L1)

___

### CreateAndOverwriteResultErrors

Ƭ **CreateAndOverwriteResultErrors**: [`DeleteResultError`](modules.md#deleteresulterror) \| [`CreateErrors`](modules.md#createerrors)

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:39](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L39)

___

### CreateErrors

Ƭ **CreateErrors**: `HttpErrorResultType` \| `UnexpectedResourceError`

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:41](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L41)

___

### CreateIfAbsentResultErrors

Ƭ **CreateIfAbsentResultErrors**: [`ReadResultError`](modules.md#readresulterror) \| [`CreateErrors`](modules.md#createerrors)

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:40](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L40)

___

### DeleteResult

Ƭ **DeleteResult**: `DeleteSuccess` \| [`DeleteResultError`](modules.md#deleteresulterror)

#### Defined in

[packages/solid/src/requester/requests/deleteResource.ts:11](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/deleteResource.ts#L11)

___

### DeleteResultError

Ƭ **DeleteResultError**: `HttpErrorResultType` \| `UnexpectedResourceError`

#### Defined in

[packages/solid/src/requester/requests/deleteResource.ts:12](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/deleteResource.ts#L12)

___

### LeafCreateAndOverwriteResult

Ƭ **LeafCreateAndOverwriteResult**: `CreateSuccess` \| [`CreateAndOverwriteResultErrors`](modules.md#createandoverwriteresulterrors)

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:27](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L27)

___

### LeafCreateIfAbsentResult

Ƭ **LeafCreateIfAbsentResult**: `CreateSuccess` \| `Exclude`\<[`ReadLeafResult`](modules.md#readleafresult), `AbsentReadSuccess`\> \| [`CreateIfAbsentResultErrors`](modules.md#createifabsentresulterrors)

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:34](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L34)

___

### LeafUri

Ƭ **LeafUri**: \`$\{string}$\{EveryLegalPathnameCharacterOtherThanSlash}$\{NonPathnameEnding}\`

#### Defined in

[packages/solid/src/util/uriTypes.ts:2](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/util/uriTypes.ts#L2)

___

### ReadContainerResult

Ƭ **ReadContainerResult**: `ContainerReadSuccess` \| `AbsentReadSuccess` \| [`ReadResultError`](modules.md#readresulterror)

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:29](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/readResource.ts#L29)

___

### ReadLeafResult

Ƭ **ReadLeafResult**: `BinaryReadSuccess` \| `DataReadSuccess` \| `AbsentReadSuccess` \| [`ReadResultError`](modules.md#readresulterror)

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:24](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/readResource.ts#L24)

___

### ReadResultError

Ƭ **ReadResultError**: `HttpErrorResultType` \| `NoncompliantPodError` \| `UnexpectedHttpError` \| `UnexpectedResourceError`

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:33](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/readResource.ts#L33)

___

### SetAccessRulesResult

Ƭ **SetAccessRulesResult**: `SetAccessRuleSuccess` \| [`SetAccessRulesResultError`](modules.md#setaccessrulesresulterror)

#### Defined in

[packages/solid/src/requester/requests/setAccessRules.ts:22](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/setAccessRules.ts#L22)

___

### SetAccessRulesResultError

Ƭ **SetAccessRulesResultError**: `AccessRuleFetchError`

#### Defined in

[packages/solid/src/requester/requests/setAccessRules.ts:25](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/setAccessRules.ts#L25)

___

### SharedStatuses

Ƭ **SharedStatuses**: `Unfetched` \| [`DeleteResult`](modules.md#deleteresult) \| `CreateSuccess`

#### Defined in

[packages/solid/src/resource/Resource.ts:32](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/resource/Resource.ts#L32)

___

### UpdateResult

Ƭ **UpdateResult**: `UpdateSuccess` \| [`UpdateResultError`](modules.md#updateresulterror)

#### Defined in

[packages/solid/src/requester/requests/updateDataResource.ts:12](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/updateDataResource.ts#L12)

___

### UpdateResultError

Ƭ **UpdateResultError**: `HttpErrorResultType` \| `UnexpectedResourceError`

#### Defined in

[packages/solid/src/requester/requests/updateDataResource.ts:13](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/updateDataResource.ts#L13)

## Functions

### changeData

▸ **changeData**\<`Type`\>(`input`, `...resources`): `Type`

Begins tracking changes to eventually commit

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `Type` | A linked data object to track changes on |
| `...resources` | [`Resource`](classes/Resource.md)[] |  |

#### Returns

`Type`

#### Defined in

[packages/solid/src/methods.ts:18](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/methods.ts#L18)

___

### checkHeadersForRootContainer

▸ **checkHeadersForRootContainer**(`uri`, `headers`): `CheckRootContainerSuccess` \| `NoncompliantPodError`

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\` |
| `headers` | `Headers` |

#### Returns

`CheckRootContainerSuccess` \| `NoncompliantPodError`

#### Defined in

[packages/solid/src/requester/requests/checkRootContainer.ts:21](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/checkRootContainer.ts#L21)

___

### checkRootContainer

▸ **checkRootContainer**(`uri`, `options?`): `Promise`\<[`CheckRootResult`](modules.md#checkrootresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\` |
| `options?` | [`BasicRequestOptions`](interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`CheckRootResult`](modules.md#checkrootresult)\>

#### Defined in

[packages/solid/src/requester/requests/checkRootContainer.ts:42](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/checkRootContainer.ts#L42)

___

### commitData

▸ **commitData**(`input`): `ReturnType`\<[`SolidLdoDataset`](classes/SolidLdoDataset.md)[``"commitChangesToPod"``]\>

Commits the transaction to the global dataset, syncing all subscribing
components and Solid Pods

#### Parameters

| Name | Type |
| :------ | :------ |
| `input` | `LdoBase` |

#### Returns

`ReturnType`\<[`SolidLdoDataset`](classes/SolidLdoDataset.md)[``"commitChangesToPod"``]\>

#### Defined in

[packages/solid/src/methods.ts:36](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/methods.ts#L36)

___

### createDataResource

▸ **createDataResource**(`uri`, `overwrite`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\` |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:43](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L43)

▸ **createDataResource**(`uri`, `overwrite`, `options?`): `Promise`\<[`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:48](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L48)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateIfAbsentResult`](modules.md#containercreateifabsentresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](modules.md#containercreateifabsentresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:53](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L53)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:58](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L58)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateIfAbsentResult`](modules.md#containercreateifabsentresult) \| [`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\` |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](modules.md#containercreateifabsentresult) \| [`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:63](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L63)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:68](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L68)

▸ **createDataResource**(`uri`, `overwrite`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:73](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L73)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult) \| [`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult) \| [`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:78](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L78)

▸ **createDataResource**(`uri`, `overwrite?`, `options?`): `Promise`\<[`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult) \| [`ContainerCreateIfAbsentResult`](modules.md#containercreateifabsentresult) \| [`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](modules.md#containercreateandoverwriteresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult) \| [`ContainerCreateIfAbsentResult`](modules.md#containercreateifabsentresult) \| [`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Defined in

[packages/solid/src/requester/requests/createDataResource.ts:83](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/createDataResource.ts#L83)

___

### createSolidLdoDataset

▸ **createSolidLdoDataset**(`options?`): [`SolidLdoDataset`](classes/SolidLdoDataset.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `options?` | [`CreateSolidLdoDatasetOptions`](interfaces/CreateSolidLdoDatasetOptions.md) |

#### Returns

[`SolidLdoDataset`](classes/SolidLdoDataset.md)

#### Defined in

[packages/solid/src/createSolidLdoDataset.ts:15](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/createSolidLdoDataset.ts#L15)

___

### deleteResource

▸ **deleteResource**(`uri`, `options?`): `Promise`\<[`DeleteResult`](modules.md#deleteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`DeleteResult`](modules.md#deleteresult)\>

#### Defined in

[packages/solid/src/requester/requests/deleteResource.ts:14](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/deleteResource.ts#L14)

___

### getAccessRules

▸ **getAccessRules**(): `Promise`\<`undefined`\>

#### Returns

`Promise`\<`undefined`\>

#### Defined in

[packages/solid/src/requester/requests/getAccessRules.ts:1](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/getAccessRules.ts#L1)

___

### isContainerUri

▸ **isContainerUri**(`uri`): uri is \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\`

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |

#### Returns

uri is \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\`

#### Defined in

[packages/solid/src/util/uriTypes.ts:5](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/util/uriTypes.ts#L5)

___

### isLeafUri

▸ **isLeafUri**(`uri`): uri is \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\`

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |

#### Returns

uri is \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\`

#### Defined in

[packages/solid/src/util/uriTypes.ts:10](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/util/uriTypes.ts#L10)

___

### readResource

▸ **readResource**(`uri`, `options?`): `Promise`\<[`ReadLeafResult`](modules.md#readleafresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadLeafResult`](modules.md#readleafresult)\>

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:39](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/readResource.ts#L39)

▸ **readResource**(`uri`, `options?`): `Promise`\<[`ReadContainerResult`](modules.md#readcontainerresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}/\` \| \`$\{string}/?$\{string}\` \| \`$\{string}/#$\{string}\` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadContainerResult`](modules.md#readcontainerresult)\>

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:43](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/readResource.ts#L43)

▸ **readResource**(`uri`, `options?`): `Promise`\<[`ReadLeafResult`](modules.md#readleafresult) \| [`ReadContainerResult`](modules.md#readcontainerresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`ReadLeafResult`](modules.md#readleafresult) \| [`ReadContainerResult`](modules.md#readcontainerresult)\>

#### Defined in

[packages/solid/src/requester/requests/readResource.ts:47](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/readResource.ts#L47)

___

### setAccessRules

▸ **setAccessRules**(`uri`, `newAccessRules`, `options?`): `Promise`\<[`SetAccessRulesResult`](modules.md#setaccessrulesresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `string` |
| `newAccessRules` | `AccessRule` |
| `options?` | [`BasicRequestOptions`](interfaces/BasicRequestOptions.md) |

#### Returns

`Promise`\<[`SetAccessRulesResult`](modules.md#setaccessrulesresult)\>

#### Defined in

[packages/solid/src/requester/requests/setAccessRules.ts:27](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/setAccessRules.ts#L27)

___

### updateDataResource

▸ **updateDataResource**(`uri`, `datasetChanges`, `options?`): `Promise`\<[`UpdateResult`](modules.md#updateresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `datasetChanges` | `DatasetChanges`\<`Quad`\> |
| `options?` | [`BasicRequestOptions`](interfaces/BasicRequestOptions.md) & \{ `onRollback?`: () => `void`  } |

#### Returns

`Promise`\<[`UpdateResult`](modules.md#updateresult)\>

#### Defined in

[packages/solid/src/requester/requests/updateDataResource.ts:15](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/updateDataResource.ts#L15)

___

### uploadResource

▸ **uploadResource**(`uri`, `blob`, `mimeType`, `overwrite`, `options?`): `Promise`\<[`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite` | ``true`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/uploadResource.ts:18](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/uploadResource.ts#L18)

▸ **uploadResource**(`uri`, `blob`, `mimeType`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | ``false`` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult)\>

#### Defined in

[packages/solid/src/requester/requests/uploadResource.ts:25](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/uploadResource.ts#L25)

▸ **uploadResource**(`uri`, `blob`, `mimeType`, `overwrite?`, `options?`): `Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | \`$\{string}Q\` \| \`$\{string}Q?$\{string}\` \| \`$\{string}Q#$\{string}\` \| \`$\{string}a\` \| \`$\{string}a?$\{string}\` \| \`$\{string}a#$\{string}\` \| \`$\{string}b\` \| \`$\{string}b?$\{string}\` \| \`$\{string}b#$\{string}\` \| \`$\{string}i\` \| \`$\{string}i?$\{string}\` \| \`$\{string}i#$\{string}\` \| \`$\{string}p\` \| \`$\{string}p?$\{string}\` \| \`$\{string}p#$\{string}\` \| \`$\{string}q\` \| \`$\{string}q?$\{string}\` \| \`$\{string}q#$\{string}\` \| \`$\{string}s\` \| \`$\{string}s?$\{string}\` \| \`$\{string}s#$\{string}\` \| \`$\{string}u\` \| \`$\{string}u?$\{string}\` \| \`$\{string}u#$\{string}\` \| \`$\{string}g\` \| \`$\{string}g?$\{string}\` \| \`$\{string}g#$\{string}\` \| \`$\{string}0\` \| \`$\{string}0?$\{string}\` \| \`$\{string}0#$\{string}\` \| \`$\{string}1\` \| \`$\{string}1?$\{string}\` \| \`$\{string}1#$\{string}\` \| \`$\{string}2\` \| \`$\{string}2?$\{string}\` \| \`$\{string}2#$\{string}\` \| \`$\{string}3\` \| \`$\{string}3?$\{string}\` \| \`$\{string}3#$\{string}\` \| \`$\{string}4\` \| \`$\{string}4?$\{string}\` \| \`$\{string}4#$\{string}\` \| \`$\{string}5\` \| \`$\{string}5?$\{string}\` \| \`$\{string}5#$\{string}\` \| \`$\{string}6\` \| \`$\{string}6?$\{string}\` \| \`$\{string}6#$\{string}\` \| \`$\{string}7\` \| \`$\{string}7?$\{string}\` \| \`$\{string}7#$\{string}\` \| \`$\{string}8\` \| \`$\{string}8?$\{string}\` \| \`$\{string}8#$\{string}\` \| \`$\{string}9\` \| \`$\{string}9?$\{string}\` \| \`$\{string}9#$\{string}\` \| \`$\{string}x\` \| \`$\{string}x?$\{string}\` \| \`$\{string}x#$\{string}\` \| \`$\{string}y\` \| \`$\{string}y?$\{string}\` \| \`$\{string}y#$\{string}\` \| \`$\{string}d\` \| \`$\{string}d?$\{string}\` \| \`$\{string}d#$\{string}\` \| \`$\{string}k\` \| \`$\{string}k?$\{string}\` \| \`$\{string}k#$\{string}\` \| \`$\{string}r\` \| \`$\{string}r?$\{string}\` \| \`$\{string}r#$\{string}\` \| \`$\{string}z\` \| \`$\{string}z?$\{string}\` \| \`$\{string}z#$\{string}\` \| \`$\{string}A\` \| \`$\{string}A?$\{string}\` \| \`$\{string}A#$\{string}\` \| \`$\{string}I\` \| \`$\{string}I?$\{string}\` \| \`$\{string}I#$\{string}\` \| \`$\{string}e\` \| \`$\{string}e?$\{string}\` \| \`$\{string}e#$\{string}\` \| \`$\{string}n\` \| \`$\{string}n?$\{string}\` \| \`$\{string}n#$\{string}\` \| \`$\{string};\` \| \`$\{string};?$\{string}\` \| \`$\{string};#$\{string}\` \| \`$\{string}:\` \| \`$\{string}:?$\{string}\` \| \`$\{string}:#$\{string}\` \| \`$\{string}.\` \| \`$\{string}.?$\{string}\` \| \`$\{string}.#$\{string}\` \| \`$\{string}X\` \| \`$\{string}X?$\{string}\` \| \`$\{string}X#$\{string}\` \| \`$\{string},\` \| \`$\{string},?$\{string}\` \| \`$\{string},#$\{string}\` \| \`$\{string}'\` \| \`$\{string}'?$\{string}\` \| \`$\{string}'#$\{string}\` \| \`$\{string}*\` \| \`$\{string}*?$\{string}\` \| \`$\{string}*#$\{string}\` \| \`$\{string}c\` \| \`$\{string}c?$\{string}\` \| \`$\{string}c#$\{string}\` \| \`$\{string}B\` \| \`$\{string}B?$\{string}\` \| \`$\{string}B#$\{string}\` \| \`$\{string}C\` \| \`$\{string}C?$\{string}\` \| \`$\{string}C#$\{string}\` \| \`$\{string}D\` \| \`$\{string}D?$\{string}\` \| \`$\{string}D#$\{string}\` \| \`$\{string}E\` \| \`$\{string}E?$\{string}\` \| \`$\{string}E#$\{string}\` \| \`$\{string}F\` \| \`$\{string}F?$\{string}\` \| \`$\{string}F#$\{string}\` \| \`$\{string}G\` \| \`$\{string}G?$\{string}\` \| \`$\{string}G#$\{string}\` \| \`$\{string}H\` \| \`$\{string}H?$\{string}\` \| \`$\{string}H#$\{string}\` \| \`$\{string}J\` \| \`$\{string}J?$\{string}\` \| \`$\{string}J#$\{string}\` \| \`$\{string}K\` \| \`$\{string}K?$\{string}\` \| \`$\{string}K#$\{string}\` \| \`$\{string}L\` \| \`$\{string}L?$\{string}\` \| \`$\{string}L#$\{string}\` \| \`$\{string}M\` \| \`$\{string}M?$\{string}\` \| \`$\{string}M#$\{string}\` \| \`$\{string}N\` \| \`$\{string}N?$\{string}\` \| \`$\{string}N#$\{string}\` \| \`$\{string}O\` \| \`$\{string}O?$\{string}\` \| \`$\{string}O#$\{string}\` \| \`$\{string}P\` \| \`$\{string}P?$\{string}\` \| \`$\{string}P#$\{string}\` \| \`$\{string}R\` \| \`$\{string}R?$\{string}\` \| \`$\{string}R#$\{string}\` \| \`$\{string}S\` \| \`$\{string}S?$\{string}\` \| \`$\{string}S#$\{string}\` \| \`$\{string}T\` \| \`$\{string}T?$\{string}\` \| \`$\{string}T#$\{string}\` \| \`$\{string}U\` \| \`$\{string}U?$\{string}\` \| \`$\{string}U#$\{string}\` \| \`$\{string}V\` \| \`$\{string}V?$\{string}\` \| \`$\{string}V#$\{string}\` \| \`$\{string}W\` \| \`$\{string}W?$\{string}\` \| \`$\{string}W#$\{string}\` \| \`$\{string}Y\` \| \`$\{string}Y?$\{string}\` \| \`$\{string}Y#$\{string}\` \| \`$\{string}Z\` \| \`$\{string}Z?$\{string}\` \| \`$\{string}Z#$\{string}\` \| \`$\{string}f\` \| \`$\{string}f?$\{string}\` \| \`$\{string}f#$\{string}\` \| \`$\{string}h\` \| \`$\{string}h?$\{string}\` \| \`$\{string}h#$\{string}\` \| \`$\{string}j\` \| \`$\{string}j?$\{string}\` \| \`$\{string}j#$\{string}\` \| \`$\{string}l\` \| \`$\{string}l?$\{string}\` \| \`$\{string}l#$\{string}\` \| \`$\{string}m\` \| \`$\{string}m?$\{string}\` \| \`$\{string}m#$\{string}\` \| \`$\{string}o\` \| \`$\{string}o?$\{string}\` \| \`$\{string}o#$\{string}\` \| \`$\{string}t\` \| \`$\{string}t?$\{string}\` \| \`$\{string}t#$\{string}\` \| \`$\{string}v\` \| \`$\{string}v?$\{string}\` \| \`$\{string}v#$\{string}\` \| \`$\{string}w\` \| \`$\{string}w?$\{string}\` \| \`$\{string}w#$\{string}\` \| \`$\{string}-\` \| \`$\{string}-?$\{string}\` \| \`$\{string}-#$\{string}\` \| \`$\{string}\_\` \| \`$\{string}\_?$\{string}\` \| \`$\{string}\_#$\{string}\` \| \`$\{string}~\` \| \`$\{string}~?$\{string}\` \| \`$\{string}~#$\{string}\` \| \`$\{string}[\` \| \`$\{string}[?$\{string}\` \| \`$\{string}[#$\{string}\` \| \`$\{string}]\` \| \`$\{string}]?$\{string}\` \| \`$\{string}]#$\{string}\` \| \`$\{string}@\` \| \`$\{string}@?$\{string}\` \| \`$\{string}@#$\{string}\` \| \`$\{string}!\` \| \`$\{string}!?$\{string}\` \| \`$\{string}!#$\{string}\` \| \`$\{string}$\` \| \`$\{string}$?$\{string}\` \| \`$\{string}$#$\{string}\` \| \`$\{string}&\` \| \`$\{string}&?$\{string}\` \| \`$\{string}&#$\{string}\` \| \`$\{string}(\` \| \`$\{string}(?$\{string}\` \| \`$\{string}(#$\{string}\` \| \`$\{string})\` \| \`$\{string})?$\{string}\` \| \`$\{string})#$\{string}\` \| \`$\{string}+\` \| \`$\{string}+?$\{string}\` \| \`$\{string}+#$\{string}\` \| \`$\{string}=\` \| \`$\{string}=?$\{string}\` \| \`$\{string}=#$\{string}\` |
| `blob` | `Blob` |
| `mimeType` | `string` |
| `overwrite?` | `boolean` |
| `options?` | [`DatasetRequestOptions`](interfaces/DatasetRequestOptions.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](modules.md#leafcreateifabsentresult) \| [`LeafCreateAndOverwriteResult`](modules.md#leafcreateandoverwriteresult)\>

#### Defined in

[packages/solid/src/requester/requests/uploadResource.ts:32](https://github.com/o-development/ldo/blob/09706ef/packages/solid/src/requester/requests/uploadResource.ts#L32)
