# Class: Container

Represents the current status of a specific container on a Pod as known by
LDO.

**`Example`**

```typescript
const container = solidLdoDataset
  .getResource("https://example.com/container/");
```

## Hierarchy

- [`Resource`](Resource.md)

  ↳ **`Container`**

## Constructors

### constructor

• **new Container**(`uri`, `context`): [`Container`](Container.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`ContainerUri`](../types/ContainerUri.md) | The uri of the container |
| `context` | [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md) | SolidLdoDatasetContext for the parent dataset |

#### Returns

[`Container`](Container.md)

#### Overrides

[Resource](Resource.md).[constructor](Resource.md#constructor)

#### Defined in

[packages/solid/src/resource/Container.ts:87](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L87)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Inherited from

[Resource](Resource.md).[absent](Resource.md#absent)

#### Defined in

[packages/solid/src/resource/Resource.ts:80](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L80)

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

[packages/solid/src/resource/Container.ts:71](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L71)

___

### requester

• `Protected` **requester**: `ContainerBatchedRequester`

Batched Requester for the Container

#### Overrides

[Resource](Resource.md).[requester](Resource.md#requester)

#### Defined in

[packages/solid/src/resource/Container.ts:55](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L55)

___

### rootContainer

• `Protected` **rootContainer**: `undefined` \| `boolean`

True if this is the root container, false if not, undefined if unknown

#### Defined in

[packages/solid/src/resource/Container.ts:61](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L61)

___

### status

• **status**: `UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess` \| `DeleteSuccess` \| `CheckRootContainerSuccess` \| `Unfetched`

The status of the last request made for this container

#### Overrides

[Resource](Resource.md).[status](Resource.md#status)

#### Defined in

[packages/solid/src/resource/Container.ts:76](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L76)

___

### type

• `Readonly` **type**: ``"container"``

Indicates that this resource is a container resource

#### Overrides

[Resource](Resource.md).[type](Resource.md#type)

#### Defined in

[packages/solid/src/resource/Container.ts:66](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L66)

___

### uri

• `Readonly` **uri**: [`ContainerUri`](../types/ContainerUri.md)

The URI of the container

#### Overrides

[Resource](Resource.md).[uri](Resource.md#uri)

#### Defined in

[packages/solid/src/resource/Container.ts:49](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L49)

## Methods

### addListener

▸ **addListener**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[addListener](Resource.md#addlistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:22

___

### checkIfIsRootContainer

▸ **checkIfIsRootContainer**(): `Promise`\<`ResourceResult`\<[`CheckRootResult`](../types/CheckRootResult.md), [`Container`](Container.md)\>\>

Checks if this container is a root container by making a request

#### Returns

`Promise`\<`ResourceResult`\<[`CheckRootResult`](../types/CheckRootResult.md), [`Container`](Container.md)\>\>

CheckRootResult

#### Defined in

[packages/solid/src/resource/Container.ts:211](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L211)

___

### child

▸ **child**(`slug`): [`Container`](Container.md)

Returns a child resource with a given name (slug)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`ContainerUri`](../types/ContainerUri.md) | the given name for that child resource |

#### Returns

[`Container`](Container.md)

the child resource (either a Leaf or Container depending on the
name)

**`Example`**

```typescript
const root = solidLdoDataset.getResource("https://example.com/");
const container = solidLdoDataset.child("container/");
// Logs "https://example.com/container/"
console.log(container.uri);
const resource = container.child("resource.ttl");
// Logs "https://example.com/container/resource.ttl"
console.log(resource.uri);
```

#### Defined in

[packages/solid/src/resource/Container.ts:331](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L331)

▸ **child**(`slug`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

[`Leaf`](Leaf.md)

#### Defined in

[packages/solid/src/resource/Container.ts:332](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L332)

▸ **child**(`slug`): [`Leaf`](Leaf.md) \| [`Container`](Container.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

[`Leaf`](Leaf.md) \| [`Container`](Container.md)

#### Defined in

[packages/solid/src/resource/Container.ts:333](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L333)

___

### children

▸ **children**(): ([`Leaf`](Leaf.md) \| [`Container`](Container.md))[]

Lists the currently cached children of this container (no request is made)

#### Returns

([`Leaf`](Leaf.md) \| [`Container`](Container.md))[]

An array of children

```typescript
const result = await container.read();
if (!result.isError) {
  const children = container.children();
  children.forEach((child) => {
    console.log(child.uri);
  });
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:302](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L302)

___

### clear

▸ **clear**(): `Promise`\<`ResourceResult`\<`AggregateSuccess`\<`ResourceSuccess`\<`DeleteSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\> \| `AggregateError`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError`\>, [`Container`](Container.md)\>\>

Deletes all contents in this container

#### Returns

`Promise`\<`ResourceResult`\<`AggregateSuccess`\<`ResourceSuccess`\<`DeleteSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\> \| `AggregateError`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError`\>, [`Container`](Container.md)\>\>

An AggregateSuccess or Aggregate error corresponding with all the
deleted resources

**`Example`**

```typescript
const result = container.clear();
if (!result.isError) {
  console.log("All deleted resources:");
  result.results.forEach((result) => console.log(result.uri));
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:500](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L500)

___

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<`ResourceResult`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md), [`Container`](Container.md)\>\>

Creates a container at this URI and overwrites any that already exists

#### Returns

`Promise`\<`ResourceResult`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md), [`Container`](Container.md)\>\>

ContainerCreateAndOverwriteResult

**`Example`**

```typescript
const result = await container.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[Resource](Resource.md).[createAndOverwrite](Resource.md#createandoverwrite)

#### Defined in

[packages/solid/src/resource/Container.ts:570](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L570)

___

### createChildAndOverwrite

▸ **createChildAndOverwrite**(`slug`): `Promise`\<`ResourceResult`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md), [`Container`](Container.md)\>\>

Creates a resource and overwrites any existing resource that existed at the
URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`ContainerUri`](../types/ContainerUri.md) | the name of the resource |

#### Returns

`Promise`\<`ResourceResult`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md), [`Container`](Container.md)\>\>

the result of creating that resource

**`Example`**

```typescript
const container = solidLdoDataset
  .getResource("https://example.com/container/");
cosnt result = await container.createChildAndOverwrite("resource.ttl");
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:361](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L361)

▸ **createChildAndOverwrite**(`slug`): `Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:364](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L364)

▸ **createChildAndOverwrite**(`slug`): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:367](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L367)

___

### createChildIfAbsent

▸ **createChildIfAbsent**(`slug`): `Promise`\<`ResourceResult`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md), [`Container`](Container.md)\>\>

Creates a resource only if that resource doesn't already exist on the Solid
Pod

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`ContainerUri`](../types/ContainerUri.md) | the name of the resource |

#### Returns

`Promise`\<`ResourceResult`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md), [`Container`](Container.md)\>\>

the result of creating that resource

**`Example`**

```typescript
const container = solidLdoDataset
  .getResource("https://example.com/container/");
cosnt result = await container.createChildIfAbsent("resource.ttl");
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:403](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L403)

▸ **createChildIfAbsent**(`slug`): `Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:406](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L406)

▸ **createChildIfAbsent**(`slug`): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:409](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L409)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<`ResourceResult`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md), [`Container`](Container.md)\>\>

Creates a container at this URI if the container doesn't already exist

#### Returns

`Promise`\<`ResourceResult`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md), [`Container`](Container.md)\>\>

ContainerCreateIfAbsentResult

**`Example`**

```typescript
const result = await container.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[Resource](Resource.md).[createIfAbsent](Resource.md#createifabsent)

#### Defined in

[packages/solid/src/resource/Container.ts:591](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L591)

___

### delete

▸ **delete**(): `Promise`\<`ResourceResult`\<[`DeleteResult`](../types/DeleteResult.md) \| `AggregateError`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError`\>, [`Container`](Container.md)\>\>

Deletes this container and all its contents

#### Returns

`Promise`\<`ResourceResult`\<[`DeleteResult`](../types/DeleteResult.md) \| `AggregateError`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError`\>, [`Container`](Container.md)\>\>

A Delete result for this container

```typescript
const result = await container.delete();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:545](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L545)

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

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Inherited from

[Resource](Resource.md).[getMaxListeners](Resource.md#getmaxlisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:39

___

### getParentContainer

▸ **getParentContainer**(): `Promise`\<`undefined` \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

Gets the parent container for this container by making a request

#### Returns

`Promise`\<`undefined` \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

The parent container or undefined if there is no parent container
because this container is the root container

**`Example`**

Suppose the root container is at `https://example.com/`

```typescript
const root = solidLdoDataset.getResource("https://example.com/");
const container = solidLdoDataset
  .getResource("https://example.com/container");
const rootParent = await root.getParentContainer();
console.log(rootParent); // Logs "undefined"
const containerParent = await container.getParentContainer();
if (!containerParent.isError) {
  // Logs "https://example.com/"
  console.log(containerParent.uri);
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:270](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L270)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

Gets the root container of this container. If this container is the root
container, this function returns itself.

#### Returns

`Promise`\<[`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

The root container for this container

**`Example`**

Suppose the root container is at `https://example.com/`

```typescript
const container = ldoSolidDataset
  .getResource("https://example.com/container/");
const rootContainer = await container.getRootContainer();
if (!rootContainer.isError) {
  // logs "https://example.com/"
  console.log(rootContainer.uri);
}
```

#### Overrides

[Resource](Resource.md).[getRootContainer](Resource.md#getrootcontainer)

#### Defined in

[packages/solid/src/resource/Container.ts:240](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L240)

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

### isRootContainer

▸ **isRootContainer**(): `undefined` \| `boolean`

Checks if this container is a root container

#### Returns

`undefined` \| `boolean`

true if this container is a root container, false if not, and
undefined if this is unknown at the moment.

**`Example`**

```typescript
// Returns "undefined" when the container is unfetched
console.log(container.isRootContainer());
const result = await container.read();
if (!result.isError) {
  // Returns true or false
  console.log(container.isRootContainer());
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:110](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L110)

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

▸ **off**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[off](Resource.md#off)

#### Defined in

node_modules/typed-emitter/index.d.ts:28

___

### on

▸ **on**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[on](Resource.md#on)

#### Defined in

node_modules/typed-emitter/index.d.ts:23

___

### once

▸ **once**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[once](Resource.md#once)

#### Defined in

node_modules/typed-emitter/index.d.ts:24

___

### prependListener

▸ **prependListener**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[prependListener](Resource.md#prependlistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:25

___

### prependOnceListener

▸ **prependOnceListener**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

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

▸ **read**(): `Promise`\<`ResourceResult`\<[`ReadContainerResult`](../types/ReadContainerResult.md), [`Container`](Container.md)\>\>

Reads the container

#### Returns

`Promise`\<`ResourceResult`\<[`ReadContainerResult`](../types/ReadContainerResult.md), [`Container`](Container.md)\>\>

A read result

**`Example`**

```typescript
const result = await container.read();
if (result.isError) {
  // Do something
}
```

#### Overrides

[Resource](Resource.md).[read](Resource.md#read)

#### Defined in

[packages/solid/src/resource/Container.ts:146](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L146)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<`ResourceResult`\<[`ReadContainerResult`](../types/ReadContainerResult.md), [`Container`](Container.md)\>\>

Makes a request to read this container if it hasn't been fetched yet. If it
has, return the cached informtation

#### Returns

`Promise`\<`ResourceResult`\<[`ReadContainerResult`](../types/ReadContainerResult.md), [`Container`](Container.md)\>\>

a ReadContainerResult

**`Example`**

```typescript
const result = await container.read();
if (!result.isError) {
  // Will execute without making a request
  const result2 = await container.readIfUnfetched();
}
```

#### Overrides

[Resource](Resource.md).[readIfUnfetched](Resource.md#readifunfetched)

#### Defined in

[packages/solid/src/resource/Container.ts:192](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L192)

___

### removeAllListeners

▸ **removeAllListeners**\<`E`\>(`event?`): [`Container`](Container.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `E` |

#### Returns

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[removeAllListeners](Resource.md#removealllisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:29

___

### removeListener

▸ **removeListener**\<`E`\>(`event`, `listener`): [`Container`](Container.md)

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

[`Container`](Container.md)

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

▸ **setMaxListeners**(`maxListeners`): [`Container`](Container.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `maxListeners` | `number` |

#### Returns

[`Container`](Container.md)

#### Inherited from

[Resource](Resource.md).[setMaxListeners](Resource.md#setmaxlisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:40

___

### toReadResult

▸ **toReadResult**(): `ResourceResult`\<[`ReadContainerResult`](../types/ReadContainerResult.md), [`Container`](Container.md)\>

Converts the current state of this container to a readResult

#### Returns

`ResourceResult`\<[`ReadContainerResult`](../types/ReadContainerResult.md), [`Container`](Container.md)\>

a ReadContainerResult

#### Overrides

[Resource](Resource.md).[toReadResult](Resource.md#toreadresult)

#### Defined in

[packages/solid/src/resource/Container.ts:157](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L157)

___

### updateWithCreateSuccess

▸ **updateWithCreateSuccess**(`result`): `void`

A helper method updates this resource's internal state upon create success

#### Parameters

| Name | Type |
| :------ | :------ |
| `result` | `ResourceSuccess` |

#### Returns

`void`

#### Inherited from

[Resource](Resource.md).[updateWithCreateSuccess](Resource.md#updatewithcreatesuccess)

#### Defined in

[packages/solid/src/resource/Resource.ts:408](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L408)

___

### updateWithDeleteSuccess

▸ **updateWithDeleteSuccess**(`_result`): `void`

A helper method updates this resource's internal state upon delete success

#### Parameters

| Name | Type |
| :------ | :------ |
| `_result` | `DeleteSuccess` |

#### Returns

`void`

#### Inherited from

[Resource](Resource.md).[updateWithDeleteSuccess](Resource.md#updatewithdeletesuccess)

#### Defined in

[packages/solid/src/resource/Resource.ts:379](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L379)

___

### updateWithReadSuccess

▸ **updateWithReadSuccess**(`result`): `void`

A helper method updates this container's internal state upon read success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | `ContainerReadSuccess` \| `AbsentReadSuccess` | the result of the read success |

#### Returns

`void`

#### Overrides

[Resource](Resource.md).[updateWithReadSuccess](Resource.md#updatewithreadsuccess)

#### Defined in

[packages/solid/src/resource/Container.ts:125](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L125)

___

### uploadChildAndOverwrite

▸ **uploadChildAndOverwrite**(`slug`, `blob`, `mimeType`): `Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

Creates a new binary resource and overwrites any existing resource that
existed at the URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) | the name of the resource |
| `blob` | `Blob` | - |
| `mimeType` | `string` | - |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

the result of creating that resource

**`Example`**

```typescript
const container = solidLdoDataset
  .getResource("https://example.com/container/");
cosnt result = await container.uploadChildAndOverwrite(
  "resource.txt",
  new Blob("some text."),
  "text/txt",
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:449](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L449)

___

### uploadChildIfAbsent

▸ **uploadChildIfAbsent**(`slug`, `blob`, `mimeType`): `Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

Creates a new binary resource and overwrites any existing resource that
existed at the URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) | the name of the resource |
| `blob` | `Blob` | - |
| `mimeType` | `string` | - |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

the result of creating that resource

**`Example`**

```typescript
const container = solidLdoDataset
  .getResource("https://example.com/container/");
cosnt result = await container.uploadChildIfAbsent(
  "resource.txt",
  new Blob("some text."),
  "text/txt",
);
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:478](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Container.ts#L478)
