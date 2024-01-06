# Class: Leaf

Represents the current status of a specific Leaf on a Pod as known by LDO.

**`Example`**

```typescript
const leaf = solidLdoDataset
  .getResource("https://example.com/container/resource.ttl");
```

## Hierarchy

- [`Resource`](Resource.md)

  ↳ **`Leaf`**

## Constructors

### constructor

• **new Leaf**(`uri`, `context`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`LeafUri`](../types/LeafUri.md) | The uri of the leaf |
| `context` | [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md) | SolidLdoDatasetContext for the parent dataset |

#### Returns

[`Leaf`](Leaf.md)

#### Overrides

[Resource](Resource.md).[constructor](Resource.md#constructor)

#### Defined in

[packages/solid/src/resource/Leaf.ts:78](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L78)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Inherited from

[Resource](Resource.md).[absent](Resource.md#absent)

#### Defined in

[packages/solid/src/resource/Resource.ts:80](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L80)

___

### binaryData

• `Protected` **binaryData**: `undefined` \| \{ `blob`: `Blob` ; `mimeType`: `string`  }

The raw binary data if this leaf is a Binary resource

#### Defined in

[packages/solid/src/resource/Leaf.ts:72](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L72)

___

### context

• `Protected` `Readonly` **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

The SolidLdoDatasetContext from the Parent Dataset

#### Inherited from

[Resource](Resource.md).[context](Resource.md#context)

#### Defined in

[packages/solid/src/resource/Resource.ts:47](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L47)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Inherited from

[Resource](Resource.md).[didInitialFetch](Resource.md#didinitialfetch)

#### Defined in

[packages/solid/src/resource/Resource.ts:74](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L74)

___

### isError

• `Readonly` **isError**: ``false``

Indicates that this resource is not an error

#### Defined in

[packages/solid/src/resource/Leaf.ts:56](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L56)

___

### requester

• `Protected` **requester**: `LeafBatchedRequester`

Batched Requester for the Leaf

#### Overrides

[Resource](Resource.md).[requester](Resource.md#requester)

#### Defined in

[packages/solid/src/resource/Leaf.ts:46](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L46)

___

### status

• **status**: `UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UpdateSuccess` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `AbsentReadSuccess` \| `DeleteSuccess` \| `Unfetched`

The status of the last request made for this leaf

#### Overrides

[Resource](Resource.md).[status](Resource.md#status)

#### Defined in

[packages/solid/src/resource/Leaf.ts:61](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L61)

___

### type

• `Readonly` **type**: ``"leaf"``

Indicates that this resource is a leaf resource

#### Overrides

[Resource](Resource.md).[type](Resource.md#type)

#### Defined in

[packages/solid/src/resource/Leaf.ts:51](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L51)

___

### uri

• `Readonly` **uri**: [`LeafUri`](../types/LeafUri.md)

The URI of the leaf

#### Overrides

[Resource](Resource.md).[uri](Resource.md#uri)

#### Defined in

[packages/solid/src/resource/Leaf.ts:40](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L40)

## Methods

### addListener

▸ **addListener**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[addListener](Resource.md#addlistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:22

___

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

Creates a leaf at this URI and overwrites any that already exists

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

LeafCreateAndOverwriteResult

**`Example`**

```typescript
const result = await leaf.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[Resource](Resource.md).[createAndOverwrite](Resource.md#createandoverwrite)

#### Defined in

[packages/solid/src/resource/Leaf.ts:402](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L402)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

Creates a leaf at this URI if the leaf doesn't already exist

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

LeafCreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[Resource](Resource.md).[createIfAbsent](Resource.md#createifabsent)

#### Defined in

[packages/solid/src/resource/Leaf.ts:423](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L423)

___

### delete

▸ **delete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

Deletes this leaf and all its contents

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

A Delete result for this leaf

```typescript
const result = await container.leaf();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Leaf.ts:372](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L372)

___

### emit

▸ **emit**\<`E`\>(`event`, `...args`): `boolean`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `...args` | `Parameters`\<\{ `update`: () => `void`  }[`E`]\> |

#### Returns

`boolean`

#### Inherited from

[Resource](Resource.md).[emit](Resource.md#emit)

#### Defined in

node_modules/typed-emitter/index.d.ts:32

___

### emitThisAndParent

▸ **emitThisAndParent**(): `void`

Emits an update event for both this resource and the parent

#### Returns

`void`

#### Inherited from

[Resource](Resource.md).[emitThisAndParent](Resource.md#emitthisandparent)

#### Defined in

[packages/solid/src/resource/Resource.ts:297](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L297)

___

### eventNames

▸ **eventNames**(): (`string` \| `symbol`)[]

#### Returns

(`string` \| `symbol`)[]

#### Inherited from

[Resource](Resource.md).[eventNames](Resource.md#eventnames)

#### Defined in

node_modules/typed-emitter/index.d.ts:34

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

[packages/solid/src/resource/Leaf.ts:153](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L153)

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Inherited from

[Resource](Resource.md).[getMaxListeners](Resource.md#getmaxlisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:39

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

[packages/solid/src/resource/Leaf.ts:138](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L138)

___

### getParentContainer

▸ **getParentContainer**(): [`Container`](Container.md)

Gets the parent container for this leaf by making a request

#### Returns

[`Container`](Container.md)

The parent container

**`Example`**

```typescript
const leaf = solidLdoDataset
  .getResource("https://example.com/container/resource.ttl");
const leafParent = leaf.getParentContainer();
if (!leafParent.isError) {
  // Logs "https://example.com/container/"
  console.log(leafParent.uri);
}
```

#### Defined in

[packages/solid/src/resource/Leaf.ts:319](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L319)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

Gets the root container for this leaf.

#### Returns

`Promise`\<[`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

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

[Resource](Resource.md).[getRootContainer](Resource.md#getrootcontainer)

#### Defined in

[packages/solid/src/resource/Leaf.ts:341](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L341)

___

### handleCreateAndOverwrite

▸ **handleCreateAndOverwrite**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`\>

Helper method that handles the core functions for creating and overwriting
a resource

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`\>

DeleteResult

#### Inherited from

[Resource](Resource.md).[handleCreateAndOverwrite](Resource.md#handlecreateandoverwrite)

#### Defined in

[packages/solid/src/resource/Resource.ts:441](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L441)

___

### handleCreateIfAbsent

▸ **handleCreateIfAbsent**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`\>

Helper method that handles the core functions for creating a resource if
 absent

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`\>

DeleteResult

#### Inherited from

[Resource](Resource.md).[handleCreateIfAbsent](Resource.md#handlecreateifabsent)

#### Defined in

[packages/solid/src/resource/Resource.ts:477](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L477)

___

### handleDelete

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

Helper method that handles the core functions for deleting a resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

DeleteResult

#### Inherited from

[Resource](Resource.md).[handleDelete](Resource.md#handledelete)

#### Defined in

[packages/solid/src/resource/Resource.ts:389](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L389)

___

### handleRead

▸ **handleRead**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

ReadResult

#### Inherited from

[Resource](Resource.md).[handleRead](Resource.md#handleread)

#### Defined in

[packages/solid/src/resource/Resource.ts:327](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L327)

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
const result = resource.read();
if (!result.isError) {
  // False if the resource exists, true if it does not
  console.log(resource.isAbsent());
}
```

#### Inherited from

[Resource](Resource.md).[isAbsent](Resource.md#isabsent)

#### Defined in

[packages/solid/src/resource/Resource.ts:264](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L264)

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

[packages/solid/src/resource/Leaf.ts:173](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L173)

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

[Resource](Resource.md).[isCreating](Resource.md#iscreating)

#### Defined in

[packages/solid/src/resource/Resource.ts:128](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L128)

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

[packages/solid/src/resource/Leaf.ts:196](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L196)

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

[Resource](Resource.md).[isDeleting](Resource.md#isdeleting)

#### Defined in

[packages/solid/src/resource/Resource.ts:164](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L164)

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

[Resource](Resource.md).[isDoingInitialFetch](Resource.md#isdoinginitialfetch)

#### Defined in

[packages/solid/src/resource/Resource.ts:182](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L182)

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

[Resource](Resource.md).[isFetched](Resource.md#isfetched)

#### Defined in

[packages/solid/src/resource/Resource.ts:226](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L226)

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

[Resource](Resource.md).[isLoading](Resource.md#isloading)

#### Defined in

[packages/solid/src/resource/Resource.ts:110](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L110)

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
const result = resource.read();
if (!result.isError) {
  // True if the resource exists, false if it does not
  console.log(resource.isPresent());
}
```

#### Inherited from

[Resource](Resource.md).[isPresent](Resource.md#ispresent)

#### Defined in

[packages/solid/src/resource/Resource.ts:283](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L283)

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

[Resource](Resource.md).[isReading](Resource.md#isreading)

#### Defined in

[packages/solid/src/resource/Resource.ts:146](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L146)

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

[Resource](Resource.md).[isReloading](Resource.md#isreloading)

#### Defined in

[packages/solid/src/resource/Resource.ts:201](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L201)

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

[Resource](Resource.md).[isUnfetched](Resource.md#isunfetched)

#### Defined in

[packages/solid/src/resource/Resource.ts:245](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L245)

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

[packages/solid/src/resource/Leaf.ts:123](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L123)

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

[packages/solid/src/resource/Leaf.ts:105](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L105)

___

### listenerCount

▸ **listenerCount**\<`E`\>(`event`): `number`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

`number`

#### Inherited from

[Resource](Resource.md).[listenerCount](Resource.md#listenercount)

#### Defined in

node_modules/typed-emitter/index.d.ts:37

___

### listeners

▸ **listeners**\<`E`\>(`event`): \{ `update`: () => `void`  }[`E`][]

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

\{ `update`: () => `void`  }[`E`][]

#### Inherited from

[Resource](Resource.md).[listeners](Resource.md#listeners)

#### Defined in

node_modules/typed-emitter/index.d.ts:36

___

### off

▸ **off**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[off](Resource.md#off)

#### Defined in

node_modules/typed-emitter/index.d.ts:28

___

### on

▸ **on**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[on](Resource.md#on)

#### Defined in

node_modules/typed-emitter/index.d.ts:23

___

### once

▸ **once**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[once](Resource.md#once)

#### Defined in

node_modules/typed-emitter/index.d.ts:24

___

### prependListener

▸ **prependListener**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[prependListener](Resource.md#prependlistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:25

___

### prependOnceListener

▸ **prependOnceListener**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[prependOnceListener](Resource.md#prependoncelistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:26

___

### rawListeners

▸ **rawListeners**\<`E`\>(`event`): \{ `update`: () => `void`  }[`E`][]

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

\{ `update`: () => `void`  }[`E`][]

#### Inherited from

[Resource](Resource.md).[rawListeners](Resource.md#rawlisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:35

___

### read

▸ **read**(): `Promise`\<`ResourceResult`\<[`ReadLeafResult`](../types/ReadLeafResult.md), [`Leaf`](Leaf.md)\>\>

Reads the leaf by making a request

#### Returns

`Promise`\<`ResourceResult`\<[`ReadLeafResult`](../types/ReadLeafResult.md), [`Leaf`](Leaf.md)\>\>

A read result

**`Example`**

```typescript
const result = await leaf.read();
if (result.isError) {
  // Do something
}
```

#### Overrides

[Resource](Resource.md).[read](Resource.md#read)

#### Defined in

[packages/solid/src/resource/Leaf.ts:237](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L237)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<`ResourceResult`\<[`ReadLeafResult`](../types/ReadLeafResult.md), [`Leaf`](Leaf.md)\>\>

Makes a request to read this leaf if it hasn't been fetched yet. If it has,
return the cached informtation

#### Returns

`Promise`\<`ResourceResult`\<[`ReadLeafResult`](../types/ReadLeafResult.md), [`Leaf`](Leaf.md)\>\>

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

[Resource](Resource.md).[readIfUnfetched](Resource.md#readifunfetched)

#### Defined in

[packages/solid/src/resource/Leaf.ts:292](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L292)

___

### removeAllListeners

▸ **removeAllListeners**\<`E`\>(`event?`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `E` |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[removeAllListeners](Resource.md#removealllisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:29

___

### removeListener

▸ **removeListener**\<`E`\>(`event`, `listener`): [`Leaf`](Leaf.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `update`: () => `void`  }[`E`] |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[removeListener](Resource.md#removelistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:30

___

### setAccessRules

▸ **setAccessRules**(`newAccessRules`): `Promise`\<`ResourceResult`\<[`SetAccessRulesResult`](../types/SetAccessRulesResult.md), [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `newAccessRules` | `AccessRule` |

#### Returns

`Promise`\<`ResourceResult`\<[`SetAccessRulesResult`](../types/SetAccessRulesResult.md), [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Inherited from

[Resource](Resource.md).[setAccessRules](Resource.md#setaccessrules)

#### Defined in

[packages/solid/src/resource/Resource.ts:518](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L518)

___

### setMaxListeners

▸ **setMaxListeners**(`maxListeners`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `maxListeners` | `number` |

#### Returns

[`Leaf`](Leaf.md)

#### Inherited from

[Resource](Resource.md).[setMaxListeners](Resource.md#setmaxlisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:40

___

### toReadResult

▸ **toReadResult**(): `ResourceResult`\<[`ReadLeafResult`](../types/ReadLeafResult.md), [`Leaf`](Leaf.md)\>

Converts the current state of this leaf to a readResult

#### Returns

`ResourceResult`\<[`ReadLeafResult`](../types/ReadLeafResult.md), [`Leaf`](Leaf.md)\>

a ReadLeafResult

#### Overrides

[Resource](Resource.md).[toReadResult](Resource.md#toreadresult)

#### Defined in

[packages/solid/src/resource/Leaf.ts:248](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L248)

___

### update

▸ **update**(`changes`): `Promise`\<`ResourceResult`\<[`UpdateResult`](../types/UpdateResult.md), [`Leaf`](Leaf.md)\>\>

Updates a data resource with the changes provided

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `changes` | `DatasetChanges`\<`Quad`\> | Dataset changes that will be applied to the resoruce |

#### Returns

`Promise`\<`ResourceResult`\<[`UpdateResult`](../types/UpdateResult.md), [`Leaf`](Leaf.md)\>\>

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

#### Defined in

[packages/solid/src/resource/Leaf.ts:539](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L539)

___

### updateWithCreateSuccess

▸ **updateWithCreateSuccess**(`_result`): `void`

A helper method updates this leaf's internal state upon create success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `_result` | `ResourceSuccess` | the result of the create success |

#### Returns

`void`

#### Overrides

[Resource](Resource.md).[updateWithCreateSuccess](Resource.md#updatewithcreatesuccess)

#### Defined in

[packages/solid/src/resource/Leaf.ts:386](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L386)

___

### updateWithDeleteSuccess

▸ **updateWithDeleteSuccess**(`_result`): `void`

A helper method updates this leaf's internal state upon delete success

#### Parameters

| Name | Type |
| :------ | :------ |
| `_result` | `DeleteSuccess` |

#### Returns

`void`

#### Overrides

[Resource](Resource.md).[updateWithDeleteSuccess](Resource.md#updatewithdeletesuccess)

#### Defined in

[packages/solid/src/resource/Leaf.ts:357](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L357)

___

### updateWithReadSuccess

▸ **updateWithReadSuccess**(`result`): `void`

A helper method updates this leaf's internal state upon read success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | `BinaryReadSuccess` \| `DataReadSuccess` \| `AbsentReadSuccess` | the result of the read success |

#### Returns

`void`

#### Overrides

[Resource](Resource.md).[updateWithReadSuccess](Resource.md#updatewithreadsuccess)

#### Defined in

[packages/solid/src/resource/Leaf.ts:214](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L214)

___

### uploadAndOverwrite

▸ **uploadAndOverwrite**(`blob`, `mimeType`): `Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

Uploads a binary resource to this URI. If there is already a resource
present at this URI, it will be overwritten

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `blob` | `Blob` | the Blob of the binary |
| `mimeType` | `string` | the MimeType of the binary |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

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

[packages/solid/src/resource/Leaf.ts:457](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L457)

___

### uploadIfAbsent

▸ **uploadIfAbsent**(`blob`, `mimeType`): `Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

Uploads a binary resource to this URI tf there not is already a resource
present at this URI.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `blob` | `Blob` | the Blob of the binary |
| `mimeType` | `string` | the MimeType of the binary |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

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

[packages/solid/src/resource/Leaf.ts:489](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Leaf.ts#L489)
