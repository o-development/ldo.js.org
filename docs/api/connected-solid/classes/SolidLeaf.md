# Class: SolidLeaf

Represents the current status of a specific Leaf on a Pod as known by LDO.

**`Example`**

```typescript
const leaf = solidLdoDataset
  .getResource("https://example.com/container/resource.ttl");
```

## Hierarchy

- [`SolidResource`](SolidResource.md)

  ↳ **`SolidLeaf`**

## Constructors

### constructor

• **new SolidLeaf**(`uri`, `context`): [`SolidLeaf`](SolidLeaf.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`SolidLeafUri`](../types/SolidLeafUri.md) | The uri of the leaf |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> | SolidLdoDatasetContext for the parent dataset |

#### Returns

[`SolidLeaf`](SolidLeaf.md)

#### Overrides

[SolidResource](SolidResource.md).[constructor](SolidResource.md#constructor)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:80](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L80)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Inherited from

[SolidResource](SolidResource.md).[absent](SolidResource.md#absent)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:104](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L104)

___

### binaryData

• `Protected` **binaryData**: `undefined` \| \{ `blob`: `Blob` ; `mimeType`: `string`  }

The raw binary data if this leaf is a Binary resource

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:74](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L74)

___

### context

• `Protected` `Readonly` **context**: `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\>

The ConnectedContext from the Parent Dataset

#### Inherited from

[SolidResource](SolidResource.md).[context](SolidResource.md#context)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:69](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L69)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Inherited from

[SolidResource](SolidResource.md).[didInitialFetch](SolidResource.md#didinitialfetch)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:98](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L98)

___

### isError

• `Readonly` **isError**: ``false``

Indicates that this resource is not an error

#### Overrides

[SolidResource](SolidResource.md).[isError](SolidResource.md#iserror)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:58](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L58)

___

### notificationSubscription

• `Protected` **notificationSubscription**: `NotificationSubscription`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md), [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)\>

Handles notification subscriptions

#### Inherited from

[SolidResource](SolidResource.md).[notificationSubscription](SolidResource.md#notificationsubscription)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:122](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L122)

___

### requester

• `Protected` **requester**: [`LeafBatchedRequester`](LeafBatchedRequester.md)

Batched Requester for the Leaf

#### Overrides

[SolidResource](SolidResource.md).[requester](SolidResource.md#requester)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:48](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L48)

___

### status

• **status**: [`BinaryReadSuccess`](BinaryReadSuccess.md) \| `Unfetched`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DeleteSuccess`](DeleteSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| [`DataReadSuccess`](DataReadSuccess.md) \| `AbsentReadSuccess`\<[`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidLeaf`](SolidLeaf.md)\> \| `UpdateSuccess`\<[`SolidLeaf`](SolidLeaf.md)\>

The status of the last request made for this leaf

#### Overrides

[SolidResource](SolidResource.md).[status](SolidResource.md#status)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:63](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L63)

___

### type

• `Readonly` **type**: ``"SolidLeaf"``

Indicates that this resource is a leaf resource

#### Overrides

[SolidResource](SolidResource.md).[type](SolidResource.md#type)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:53](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L53)

___

### uri

• `Readonly` **uri**: [`SolidLeafUri`](../types/SolidLeafUri.md)

The URI of the leaf

#### Overrides

[SolidResource](SolidResource.md).[uri](SolidResource.md#uri)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:42](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L42)

___

### wacRule

• `Protected` `Optional` **wacRule**: [`WacRule`](../interfaces/WacRule.md)

If a wac rule was fetched, it is cached here

#### Inherited from

[SolidResource](SolidResource.md).[wacRule](SolidResource.md#wacrule)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:116](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L116)

___

### wacUri

• `Protected` `Optional` **wacUri**: [`SolidLeafUri`](../types/SolidLeafUri.md)

If a wac uri is fetched, it is cached here

#### Inherited from

[SolidResource](SolidResource.md).[wacUri](SolidResource.md#wacuri)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:110](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L110)

## Methods

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Creates a leaf at this URI and overwrites any that already exists

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

LeafCreateAndOverwriteResult

**`Example`**

```typescript
const result = await leaf.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[SolidResource](SolidResource.md).[createAndOverwrite](SolidResource.md#createandoverwrite)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:405](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L405)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

Creates a leaf at this URI if the leaf doesn't already exist

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

LeafCreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[SolidResource](SolidResource.md).[createIfAbsent](SolidResource.md#createifabsent)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:424](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L424)

___

### delete

▸ **delete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

Deletes this leaf and all its contents

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

A Delete result for this leaf

```typescript
const result = await container.leaf();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:368](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L368)

___

### emitThisAndParent

▸ **emitThisAndParent**(): `void`

Emits an update event for both this resource and the parent

#### Returns

`void`

#### Inherited from

[SolidResource](SolidResource.md).[emitThisAndParent](SolidResource.md#emitthisandparent)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:367](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L367)

___

### getBlob

▸ **getBlob**(): `undefined` \| `Blob`

If this resource is a binary resource, returns the Blob

#### Returns

`undefined` \| `Blob`

The Blob  if this resource is a binary resource, undefined
otherwise

**`Example`**

```typescript
// Logs "some text."
console.log(leaf.getBlob()?.toString());
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:160](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L160)

___

### getMimeType

▸ **getMimeType**(): `undefined` \| `string`

If this resource is a binary resource, returns the mime type

#### Returns

`undefined` \| `string`

The mime type if this resource is a binary resource, undefined
otherwise

**`Example`**

```typescript
// Logs "text/txt"
console.log(leaf.getMimeType());
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:145](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L145)

___

### getParentContainer

▸ **getParentContainer**(): `Promise`\<[`SolidContainer`](SolidContainer.md)\>

Gets the parent container for this leaf by making a request

#### Returns

`Promise`\<[`SolidContainer`](SolidContainer.md)\>

The parent container

**`Example`**

```typescript
const leaf = solidLdoDataset
  .getResource("https://example.com/container/resource.ttl");
const leafParent = await leaf.getParentContainer();
if (!leafParent.isError) {
  // Logs "https://example.com/container/"
  console.log(leafParent.uri);
}
```

#### Overrides

[SolidResource](SolidResource.md).[getParentContainer](SolidResource.md#getparentcontainer)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:309](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L309)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`NoRootContainerError`](NoRootContainerError.md)\<[`SolidContainer`](SolidContainer.md)\>\>

Gets the root container for this leaf.

#### Returns

`Promise`\<[`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`NoRootContainerError`](NoRootContainerError.md)\<[`SolidContainer`](SolidContainer.md)\>\>

The root container for this leaf

**`Example`**

Suppose the root container is at `https://example.com/`

```typescript
const leaf = ldoSolidDataset
  .getResource("https://example.com/container/resource.ttl");
const rootContainer = await leaf.getRootContainer();
if (!rootContainer.isError) {
  // logs "https://example.com/"
  console.log(rootContainer.uri);
}
```

#### Overrides

[SolidResource](SolidResource.md).[getRootContainer](SolidResource.md#getrootcontainer)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:331](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L331)

___

### getWac

▸ **getWac**(`options?`): `Promise`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NotFoundHttpError`](NotFoundHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`GetWacRuleSuccess`](GetWacRuleSuccess.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`WacRuleAbsent`](WacRuleAbsent.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

Retrieves web access control (WAC) rules for this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Object` | set the "ignoreCache" field to true to ignore any cached information on WAC rules. |
| `options.ignoreCache` | `boolean` | - |

#### Returns

`Promise`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NotFoundHttpError`](NotFoundHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`GetWacRuleSuccess`](GetWacRuleSuccess.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`WacRuleAbsent`](WacRuleAbsent.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

WAC Rules results

**`Example`**

```typescript
const resource = ldoSolidDataset
  .getResource("https://example.com/container/resource.ttl");
const wacRulesResult = await resource.getWac();
if (!wacRulesResult.isError) {
  const wacRules = wacRulesResult.wacRule;
  // True if the resource is publicly readable
  console.log(wacRules.public.read);
  // True if authenticated agents can write to the resource
  console.log(wacRules.authenticated.write);
  // True if the given WebId has append access
  console.log(
    wacRules.agent[https://example.com/person1/profile/card#me].append
  );
  // True if the given WebId has control access
  console.log(
    wacRules.agent[https://example.com/person1/profile/card#me].control
  );
}
```

#### Inherited from

[SolidResource](SolidResource.md).[getWac](SolidResource.md#getwac)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:648](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L648)

___

### getWacUri

▸ **getWacUri**(`options?`): `Promise`\<[`GetWacUriResult`](../types/GetWacUriResult.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

Retrieves the URI for the web access control (WAC) rules for this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Object` | set the "ignoreCache" field to true to ignore any cached information on WAC rules. |
| `options.ignoreCache` | `boolean` | - |

#### Returns

`Promise`\<[`GetWacUriResult`](../types/GetWacUriResult.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

WAC Rules results

#### Inherited from

[SolidResource](SolidResource.md).[getWacUri](SolidResource.md#getwacuri)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:601](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L601)

___

### handleCreateAndOverwrite

▸ **handleCreateAndOverwrite**(): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Helper method that handles the core functions for creating and overwriting
a resource

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

DeleteResult

#### Inherited from

[SolidResource](SolidResource.md).[handleCreateAndOverwrite](SolidResource.md#handlecreateandoverwrite)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:503](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L503)

___

### handleCreateIfAbsent

▸ **handleCreateIfAbsent**(): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

Helper method that handles the core functions for creating a resource if
 absent

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

DeleteResult

#### Inherited from

[SolidResource](SolidResource.md).[handleCreateIfAbsent](SolidResource.md#handlecreateifabsent)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:536](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L536)

___

### handleDelete

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Overrides

[SolidResource](SolidResource.md).[handleDelete](SolidResource.md#handledelete)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:375](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L375)

___

### handleRead

▸ **handleRead**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

ReadResult

#### Inherited from

[SolidResource](SolidResource.md).[handleRead](SolidResource.md#handleread)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:397](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L397)

___

### isAbsent

▸ **isAbsent**(): `undefined` \| `boolean`

Is this resource currently absent (it does not exist)

#### Returns

`undefined` \| `boolean`

true if the resource is absent, false if not, undefined if unknown

**`Example`**

```typescript
// Logs "undefined"
console.log(resource.isAbsent());
const result = await resource.read();
if (!result.isError) {
  // False if the resource exists, true if it does not
  console.log(resource.isAbsent());
}
```

#### Inherited from

[SolidResource](SolidResource.md).[isAbsent](SolidResource.md#isabsent)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:319](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L319)

___

### isBinary

▸ **isBinary**(): `undefined` \| `boolean`

Check if this resource is a binary resource

#### Returns

`undefined` \| `boolean`

True if this resource is a binary resource, false if not,
undefined if unknown

**`Example`**

```typescript
// Logs "undefined"
console.log(leaf.isBinary());
const result = await leaf.read();
if (!result.isError) {
  // Logs "true"
  console.log(leaf.isBinary());
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:180](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L180)

___

### isCreating

▸ **isCreating**(): `boolean`

Checks to see if this resource is being created

#### Returns

`boolean`

true if the resource is currently being created

**`Example`**

```typescript
resource.read().then(() => {
  // Logs "false"
  console.log(resource.isCreating())
});
// Logs "true"
console.log(resource.isCreating());
```

#### Inherited from

[SolidResource](SolidResource.md).[isCreating](SolidResource.md#iscreating)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:183](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L183)

___

### isDataResource

▸ **isDataResource**(): `undefined` \| `boolean`

Check if this resource is a data (RDF) resource

#### Returns

`undefined` \| `boolean`

True if this resource is a data resource, false if not, undefined
if unknown

**`Example`**

```typescript
// Logs "undefined"
console.log(leaf.isDataResource());
const result = await leaf.read();
if (!result.isError) {
  // Logs "true"
  console.log(leaf.isDataResource());
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:203](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L203)

___

### isDeleting

▸ **isDeleting**(): `boolean`

Checks to see if this resource is being deleted

#### Returns

`boolean`

true if the resource is currently being deleted

**`Example`**

```typescript
resource.read().then(() => {
  // Logs "false"
  console.log(resource.isDeleting())
});
// Logs "true"
console.log(resource.isDeleting());
```

#### Inherited from

[SolidResource](SolidResource.md).[isDeleting](SolidResource.md#isdeleting)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:219](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L219)

___

### isDoingInitialFetch

▸ **isDoingInitialFetch**(): `boolean`

Checks to see if this resource is being read for the first time

#### Returns

`boolean`

true if the resource is currently being read for the first time

**`Example`**

```typescript
resource.read().then(() => {
  // Logs "false"
  console.log(resource.isDoingInitialFetch())
});
// Logs "true"
console.log(resource.isDoingInitialFetch());
```

#### Inherited from

[SolidResource](SolidResource.md).[isDoingInitialFetch](SolidResource.md#isdoinginitialfetch)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:237](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L237)

___

### isFetched

▸ **isFetched**(): `boolean`

Check to see if this resource has been fetched

#### Returns

`boolean`

true if this resource has been fetched before

**`Example`**

```typescript
// Logs "false"
console.log(resource.isFetched());
const result = await resource.read();
if (!result.isError) {
  // Logs "true"
  console.log(resource.isFetched());
}
```

#### Inherited from

[SolidResource](SolidResource.md).[isFetched](SolidResource.md#isfetched)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:281](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L281)

___

### isLoading

▸ **isLoading**(): `boolean`

Checks to see if this resource is loading in any way

#### Returns

`boolean`

true if the resource is currently loading

**`Example`**

```typescript
resource.read().then(() => {
  // Logs "false"
  console.log(resource.isLoading())
});
// Logs "true"
console.log(resource.isLoading());
```

#### Inherited from

[SolidResource](SolidResource.md).[isLoading](SolidResource.md#isloading)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:165](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L165)

___

### isPresent

▸ **isPresent**(): `undefined` \| `boolean`

Is this resource currently present on the Pod

#### Returns

`undefined` \| `boolean`

false if the resource is absent, true if not, undefined if unknown

**`Example`**

```typescript
// Logs "undefined"
console.log(resource.isPresent());
const result = await resource.read();
if (!result.isError) {
  // True if the resource exists, false if it does not
  console.log(resource.isPresent());
}
```

#### Inherited from

[SolidResource](SolidResource.md).[isPresent](SolidResource.md#ispresent)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:338](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L338)

___

### isReading

▸ **isReading**(): `boolean`

Checks to see if this resource is being read

#### Returns

`boolean`

true if the resource is currently being read

**`Example`**

```typescript
resource.read().then(() => {
  // Logs "false"
  console.log(resource.isReading())
});
// Logs "true"
console.log(resource.isReading());
```

#### Inherited from

[SolidResource](SolidResource.md).[isReading](SolidResource.md#isreading)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:201](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L201)

___

### isReloading

▸ **isReloading**(): `boolean`

Checks to see if this resource is being read for a subsequent time

#### Returns

`boolean`

true if the resource is currently being read for a subsequent time

**`Example`**

```typescript
await resource.read();
resource.read().then(() => {
  // Logs "false"
  console.log(resource.isCreating())
});
// Logs "true"
console.log(resource.isCreating());
```

#### Inherited from

[SolidResource](SolidResource.md).[isReloading](SolidResource.md#isreloading)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:256](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L256)

___

### isSubscribedToNotifications

▸ **isSubscribedToNotifications**(): `boolean`

Is this resource currently listening to notifications from this document

#### Returns

`boolean`

true if the resource is subscribed to notifications, false if not

**`Example`**

```typescript
await resource.subscribeToNotifications();
// Logs "true"
console.log(resource.isSubscribedToNotifications());
```

#### Inherited from

[SolidResource](SolidResource.md).[isSubscribedToNotifications](SolidResource.md#issubscribedtonotifications)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:353](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L353)

___

### isUnfetched

▸ **isUnfetched**(): `boolean`

Check to see if this resource is currently unfetched

#### Returns

`boolean`

true if the resource is currently unfetched

**`Example`**

```typescript
// Logs "true"
console.log(resource.isUnetched());
const result = await resource.read();
if (!result.isError) {
  // Logs "false"
  console.log(resource.isUnfetched());
}
```

#### Inherited from

[SolidResource](SolidResource.md).[isUnfetched](SolidResource.md#isunfetched)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:300](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L300)

___

### isUpdating

▸ **isUpdating**(): `boolean`

Checks to see if the resource is currently updating data

#### Returns

`boolean`

true if the current resource is updating

**`Example`**

```typescript
leaf.update(datasetChanges).then(() => {
  // Logs "false"
  console.log(leaf.isUpdating())
});
// Logs "true"
console.log(leaf.isUpdating());
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:130](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L130)

___

### isUploading

▸ **isUploading**(): `boolean`

Checks to see if the resource is currently uploading data

#### Returns

`boolean`

true if the current resource is uploading

**`Example`**

```typescript
leaf.uploadAndOverwrite(new Blob("some text"), "text/txt").then(() => {
  // Logs "false"
  console.log(leaf.isUploading())
});
// Logs "true"
console.log(leaf.isUploading());
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:112](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L112)

___

### onNotification

▸ **onNotification**(`message`): `Promise`\<`void`\>

Function that triggers whenever a notification is recieved.

#### Parameters

| Name | Type |
| :------ | :------ |
| `message` | [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md) |

#### Returns

`Promise`\<`void`\>

#### Inherited from

[SolidResource](SolidResource.md).[onNotification](SolidResource.md#onnotification)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:799](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L799)

___

### read

▸ **read**(): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

Reads the leaf by making a request

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

A read result

**`Example`**

```typescript
const result = await leaf.read();
if (result.isError) {
  // Do something
}
```

#### Overrides

[SolidResource](SolidResource.md).[read](SolidResource.md#read)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:244](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L244)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

Makes a request to read this leaf if it hasn't been fetched yet. If it has,
return the cached informtation

#### Returns

`Promise`\<[`ReadLeafResult`](../types/ReadLeafResult.md)\>

a ReadLeafResult

**`Example`**

```typescript
const result = await leaf.read();
if (!result.isError) {
  // Will execute without making a request
  const result2 = await leaf.readIfUnfetched();
}
```

#### Overrides

[SolidResource](SolidResource.md).[readIfUnfetched](SolidResource.md#readifunfetched)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:284](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L284)

___

### setWac

▸ **setWac**(`wacRule`): `Promise`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NotFoundHttpError`](NotFoundHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`SetWacRuleSuccess`](SetWacRuleSuccess.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

Sets access rules for a specific resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `wacRule` | [`WacRule`](../interfaces/WacRule.md) | the access rules to set |

#### Returns

`Promise`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NotFoundHttpError`](NotFoundHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`SetWacRuleSuccess`](SetWacRuleSuccess.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

SetWacRuleResult

**`Example`**

```typescript
const resource = ldoSolidDataset
  .getResource("https://example.com/container/resource.ttl");
const wacRulesResult = await resource.setWac({
  public: {
    read: true,
    write: false,
    append: false,
    control: false
  },
  authenticated: {
    read: true,
    write: false,
    append: true,
    control: false
  },
  agent: {
    "https://example.com/person1/profile/card#me": {
      read: true,
      write: true,
      append: true,
      control: true
    }
  }
});
```

#### Inherited from

[SolidResource](SolidResource.md).[setWac](SolidResource.md#setwac)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:724](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L724)

___

### subscribeToNotifications

▸ **subscribeToNotifications**(`callbacks?`): `Promise`\<`string`\>

Activates Websocket subscriptions on this resource. Updates, deletions,
and creations on this resource will be tracked and all changes will be
relected in LDO's resources and graph.

#### Parameters

| Name | Type |
| :------ | :------ |
| `callbacks?` | `SubscriptionCallbacks`\<[`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)\> |

#### Returns

`Promise`\<`string`\>

SubscriptionId: A string to use to unsubscribe

**`Example`**

```typescript
const resource = solidLdoDataset
  .getResource("https://example.com/spiderman");
// A listener for if anything about spiderman in the global dataset is
// changed. Note that this will also listen for any local changes as well
// as changes to remote resources to which you have notification
// subscriptions enabled.
solidLdoDataset.addListener(
  [namedNode("https://example.com/spiderman#spiderman"), null, null, null],
  () => {
    // Triggers when the file changes on the Pod or locally
    console.log("Something changed about SpiderMan");
  },
);

// Subscribe
const subscriptionId = await testContainer.subscribeToNotifications({
  // These are optional callbacks. A subscription will automatically keep
  // the dataset in sync. Use these callbacks for additional functionality.
  onNotification: (message) => console.log(message),
  onNotificationError: (err) => console.log(err.message)
});
// ... From there you can wait for a file to be changed on the Pod.

#### Inherited from

[SolidResource](SolidResource.md).[subscribeToNotifications](SolidResource.md#subscribetonotifications)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:787](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L787)

___

### toReadResult

▸ **toReadResult**(): [`ReadLeafResult`](../types/ReadLeafResult.md)

Converts the current state of this leaf to a readResult

#### Returns

[`ReadLeafResult`](../types/ReadLeafResult.md)

a ReadLeafResult

#### Overrides

[SolidResource](SolidResource.md).[toReadResult](SolidResource.md#toreadresult)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:255](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L255)

___

### unsubscribeFromAllNotifications

▸ **unsubscribeFromAllNotifications**(): `Promise`\<`void`\>

Unsubscribes from all notifications on this resource

#### Returns

`Promise`\<`void`\>

UnsubscribeResult[]

**`Example`**

```typescript
const subscriptionResult = await testContainer.subscribeToNotifications();
await testContainer.unsubscribeFromAllNotifications();
```

#### Inherited from

[SolidResource](SolidResource.md).[unsubscribeFromAllNotifications](SolidResource.md#unsubscribefromallnotifications)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:851](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L851)

___

### unsubscribeFromNotifications

▸ **unsubscribeFromNotifications**(`subscriptionId`): `Promise`\<`void`\>

Unsubscribes from changes made to this resource on the Pod

#### Parameters

| Name | Type |
| :------ | :------ |
| `subscriptionId` | `string` |

#### Returns

`Promise`\<`void`\>

UnsubscribeResult

**`Example`**

```typescript
const subscriptionId = await testContainer.subscribeToNotifications();
await testContainer.unsubscribeFromNotifications(subscriptionId);
```

#### Inherited from

[SolidResource](SolidResource.md).[unsubscribeFromNotifications](SolidResource.md#unsubscribefromnotifications)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:834](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L834)

___

### update

▸ **update**(`changes`): `Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

Updates a data resource with the changes provided

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> | Dataset changes that will be applied to the resoruce |

#### Returns

`Promise`\<[`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

An UpdateResult

**`Example`**

```typescript
import {
  updateDataResource,
  transactionChanges,
  changeData,
  createSolidLdoDataset,
} from "@ldo/solid";

//...

// Get a Linked Data Object
const profile = solidLdoDataset
  .usingType(ProfileShapeType)
  .fromSubject("https://example.com/profile#me");
cosnt resource = solidLdoDataset
  .getResource("https://example.com/profile");
// Create a transaction to change data
const cProfile = changeData(profile, resource);
cProfile.name = "John Doe";
// Get data in "DatasetChanges" form
const datasetChanges = transactionChanges(someLinkedDataObject);
// Use "update" to apply the changes
cosnt result = resource.update(datasetChanges);
```

#### Overrides

[SolidResource](SolidResource.md).[update](SolidResource.md#update)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:538](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L538)

___

### updateWithCreateSuccess

▸ **updateWithCreateSuccess**(`_result`): `void`

A helper method updates this leaf's internal state upon create success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `_result` | `ResourceSuccess`\<[`SolidLeaf`](SolidLeaf.md)\> | the result of the create success |

#### Returns

`void`

#### Overrides

[SolidResource](SolidResource.md).[updateWithCreateSuccess](SolidResource.md#updatewithcreatesuccess)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:389](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L389)

___

### updateWithDeleteSuccess

▸ **updateWithDeleteSuccess**(`result`): `void`

A helper method updates this leaf's internal state upon delete success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | [`DeleteSuccess`](DeleteSuccess.md)\<[`SolidLeaf`](SolidLeaf.md)\> | the result of the delete success |

#### Returns

`void`

#### Overrides

[SolidResource](SolidResource.md).[updateWithDeleteSuccess](SolidResource.md#updatewithdeletesuccess)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:352](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L352)

___

### updateWithReadSuccess

▸ **updateWithReadSuccess**(`result`): `void`

A helper method updates this leaf's internal state upon read success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | [`BinaryReadSuccess`](BinaryReadSuccess.md) \| [`DataReadSuccess`](DataReadSuccess.md) \| `AbsentReadSuccess`\<[`SolidLeaf`](SolidLeaf.md)\> | the result of the read success |

#### Returns

`void`

#### Overrides

[SolidResource](SolidResource.md).[updateWithReadSuccess](SolidResource.md#updatewithreadsuccess)

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:221](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L221)

___

### uploadAndOverwrite

▸ **uploadAndOverwrite**(`blob`, `mimeType`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Uploads a binary resource to this URI. If there is already a resource
present at this URI, it will be overwritten

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `blob` | `Blob` | the Blob of the binary |
| `mimeType` | `string` | the MimeType of the binary |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

A LeafCreateAndOverwriteResult

**`Example`**

```typescript
const result = await leaf.uploadAndOverwrite(
  new Blob("some text."),
  "text/txt",
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:456](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L456)

___

### uploadIfAbsent

▸ **uploadIfAbsent**(`blob`, `mimeType`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

Uploads a binary resource to this URI tf there not is already a resource
present at this URI.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `blob` | `Blob` | the Blob of the binary |
| `mimeType` | `string` | the MimeType of the binary |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

A LeafCreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.uploadIfAbsent(
  new Blob("some text."),
  "text/txt",
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidLeaf.ts:488](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidLeaf.ts#L488)
