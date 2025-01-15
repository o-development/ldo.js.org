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

[packages/solid/src/resource/Container.ts:87](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L87)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Inherited from

[Resource](Resource.md).[absent](Resource.md#absent)

#### Defined in

[packages/solid/src/resource/Resource.ts:95](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L95)

___

### context

• `Protected` `Readonly` **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

The SolidLdoDatasetContext from the Parent Dataset

#### Inherited from

[Resource](Resource.md).[context](Resource.md#context)

#### Defined in

[packages/solid/src/resource/Resource.ts:62](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L62)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Inherited from

[Resource](Resource.md).[didInitialFetch](Resource.md#didinitialfetch)

#### Defined in

[packages/solid/src/resource/Resource.ts:89](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L89)

___

### isError

• `Readonly` **isError**: ``false``

Indicates that this resource is not an error

#### Defined in

[packages/solid/src/resource/Container.ts:71](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L71)

___

### notificationSubscription

• `Protected` **notificationSubscription**: `NotificationSubscription`

Handles notification subscriptions

#### Inherited from

[Resource](Resource.md).[notificationSubscription](Resource.md#notificationsubscription)

#### Defined in

[packages/solid/src/resource/Resource.ts:113](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L113)

___

### requester

• `Protected` **requester**: `ContainerBatchedRequester`

Batched Requester for the Container

#### Overrides

[Resource](Resource.md).[requester](Resource.md#requester)

#### Defined in

[packages/solid/src/resource/Container.ts:55](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L55)

___

### rootContainer

• `Protected` **rootContainer**: `undefined` \| `boolean`

True if this is the root container, false if not, undefined if unknown

#### Defined in

[packages/solid/src/resource/Container.ts:61](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L61)

___

### status

• **status**: `UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess` \| `DeleteSuccess` \| `CheckRootContainerSuccess` \| `Unfetched`

The status of the last request made for this container

#### Overrides

[Resource](Resource.md).[status](Resource.md#status)

#### Defined in

[packages/solid/src/resource/Container.ts:76](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L76)

___

### type

• `Readonly` **type**: ``"container"``

Indicates that this resource is a container resource

#### Overrides

[Resource](Resource.md).[type](Resource.md#type)

#### Defined in

[packages/solid/src/resource/Container.ts:66](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L66)

___

### uri

• `Readonly` **uri**: [`ContainerUri`](../types/ContainerUri.md)

The URI of the container

#### Overrides

[Resource](Resource.md).[uri](Resource.md#uri)

#### Defined in

[packages/solid/src/resource/Container.ts:49](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L49)

___

### wacRule

• `Protected` `Optional` **wacRule**: [`WacRule`](../interfaces/WacRule.md)

If a wac rule was fetched, it is cached here

#### Inherited from

[Resource](Resource.md).[wacRule](Resource.md#wacrule)

#### Defined in

[packages/solid/src/resource/Resource.ts:107](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L107)

___

### wacUri

• `Protected` `Optional` **wacUri**: [`LeafUri`](../types/LeafUri.md)

If a wac uri is fetched, it is cached here

#### Inherited from

[Resource](Resource.md).[wacUri](Resource.md#wacuri)

#### Defined in

[packages/solid/src/resource/Resource.ts:101](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L101)

## Methods

### addListener

▸ **addListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

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

[packages/solid/src/resource/Container.ts:211](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L211)

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

[packages/solid/src/resource/Container.ts:331](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L331)

▸ **child**(`slug`): [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

[`Leaf`](Leaf.md)

#### Defined in

[packages/solid/src/resource/Container.ts:332](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L332)

▸ **child**(`slug`): [`Container`](Container.md) \| [`Leaf`](Leaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

[`Container`](Container.md) \| [`Leaf`](Leaf.md)

#### Defined in

[packages/solid/src/resource/Container.ts:333](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L333)

___

### children

▸ **children**(): ([`Container`](Container.md) \| [`Leaf`](Leaf.md))[]

Lists the currently cached children of this container (no request is made)

#### Returns

([`Container`](Container.md) \| [`Leaf`](Leaf.md))[]

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

[packages/solid/src/resource/Container.ts:302](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L302)

___

### clear

▸ **clear**(): `Promise`\<`ResourceResult`\<`AggregateSuccess`\<`ResourceSuccess`\<`DeleteSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\> \| `AggregateError`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError`\>, [`Container`](Container.md)\>\>

Deletes all contents in this container

#### Returns

`Promise`\<`ResourceResult`\<`AggregateSuccess`\<`ResourceSuccess`\<`DeleteSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\> \| `AggregateError`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError`\>, [`Container`](Container.md)\>\>

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

[packages/solid/src/resource/Container.ts:500](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L500)

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

[packages/solid/src/resource/Container.ts:570](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L570)

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

[packages/solid/src/resource/Container.ts:361](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L361)

▸ **createChildAndOverwrite**(`slug`): `Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md), [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:364](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L364)

▸ **createChildAndOverwrite**(`slug`): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:367](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L367)

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

[packages/solid/src/resource/Container.ts:403](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L403)

▸ **createChildIfAbsent**(`slug`): `Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`LeafUri`](../types/LeafUri.md) |

#### Returns

`Promise`\<`ResourceResult`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md), [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:406](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L406)

▸ **createChildIfAbsent**(`slug`): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Container.ts:409](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L409)

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

[packages/solid/src/resource/Container.ts:591](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L591)

___

### delete

▸ **delete**(): `Promise`\<`ResourceResult`\<[`DeleteResult`](../types/DeleteResult.md) \| `AggregateError`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError`\>, [`Container`](Container.md)\>\>

Deletes this container and all its contents

#### Returns

`Promise`\<`ResourceResult`\<[`DeleteResult`](../types/DeleteResult.md) \| `AggregateError`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError`\>, [`Container`](Container.md)\>\>

A Delete result for this container

```typescript
const result = await container.delete();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Container.ts:545](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L545)

___

### emit

▸ **emit**\<`E`\>(`event`, `...args`): `boolean`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `...args` | `Parameters`\<\{ `notification`: () => `void` ; `update`: () => `void`  }[`E`]\> |

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

[packages/solid/src/resource/Resource.ts:350](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L350)

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

▸ **getParentContainer**(): `Promise`\<`undefined` \| [`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

Gets the parent container for this container by making a request

#### Returns

`Promise`\<`undefined` \| [`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

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

#### Overrides

[Resource](Resource.md).[getParentContainer](Resource.md#getparentcontainer)

#### Defined in

[packages/solid/src/resource/Container.ts:273](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L273)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| `NoRootContainerError`\>

Gets the root container of this container. If this container is the root
container, this function returns itself.

#### Returns

`Promise`\<[`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| `NoRootContainerError`\>

The root container for this container or undefined if there is no
root container.

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

[packages/solid/src/resource/Container.ts:241](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L241)

___

### getWac

▸ **getWac**(`options?`): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `NotFoundHttpError` \| [`GetWacRuleSuccess`](../interfaces/GetWacRuleSuccess.md) \| [`WacRuleAbsent`](../interfaces/WacRuleAbsent.md)\>

Retrieves web access control (WAC) rules for this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Object` | set the "ignoreCache" field to true to ignore any cached information on WAC rules. |
| `options.ignoreCache` | `boolean` | - |

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `NotFoundHttpError` \| [`GetWacRuleSuccess`](../interfaces/GetWacRuleSuccess.md) \| [`WacRuleAbsent`](../interfaces/WacRuleAbsent.md)\>

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

[Resource](Resource.md).[getWac](Resource.md#getwac)

#### Defined in

[packages/solid/src/resource/Resource.ts:635](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L635)

___

### getWacUri

▸ **getWacUri**(`options?`): `Promise`\<[`GetWacUriResult`](../types/GetWacUriResult.md)\>

Retrieves the URI for the web access control (WAC) rules for this resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Object` | set the "ignoreCache" field to true to ignore any cached information on WAC rules. |
| `options.ignoreCache` | `boolean` | - |

#### Returns

`Promise`\<[`GetWacUriResult`](../types/GetWacUriResult.md)\>

WAC Rules results

#### Inherited from

[Resource](Resource.md).[getWacUri](Resource.md#getwacuri)

#### Defined in

[packages/solid/src/resource/Resource.ts:584](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L584)

___

### handleCreateAndOverwrite

▸ **handleCreateAndOverwrite**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`\>

Helper method that handles the core functions for creating and overwriting
a resource

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`\>

DeleteResult

#### Inherited from

[Resource](Resource.md).[handleCreateAndOverwrite](Resource.md#handlecreateandoverwrite)

#### Defined in

[packages/solid/src/resource/Resource.ts:494](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L494)

___

### handleCreateIfAbsent

▸ **handleCreateIfAbsent**(): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`\>

Helper method that handles the core functions for creating a resource if
 absent

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`\>

DeleteResult

#### Inherited from

[Resource](Resource.md).[handleCreateIfAbsent](Resource.md#handlecreateifabsent)

#### Defined in

[packages/solid/src/resource/Resource.ts:530](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L530)

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

[packages/solid/src/resource/Resource.ts:442](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L442)

___

### handleRead

▸ **handleRead**(): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

ReadResult

#### Inherited from

[Resource](Resource.md).[handleRead](Resource.md#handleread)

#### Defined in

[packages/solid/src/resource/Resource.ts:380](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L380)

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

[Resource](Resource.md).[isAbsent](Resource.md#isabsent)

#### Defined in

[packages/solid/src/resource/Resource.ts:302](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L302)

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

[packages/solid/src/resource/Resource.ts:166](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L166)

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

[packages/solid/src/resource/Resource.ts:202](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L202)

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

[packages/solid/src/resource/Resource.ts:220](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L220)

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

[packages/solid/src/resource/Resource.ts:264](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L264)

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

[packages/solid/src/resource/Resource.ts:148](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L148)

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

[Resource](Resource.md).[isPresent](Resource.md#ispresent)

#### Defined in

[packages/solid/src/resource/Resource.ts:321](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L321)

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

[packages/solid/src/resource/Resource.ts:184](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L184)

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

[packages/solid/src/resource/Resource.ts:239](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L239)

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

[packages/solid/src/resource/Container.ts:110](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L110)

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

[Resource](Resource.md).[isSubscribedToNotifications](Resource.md#issubscribedtonotifications)

#### Defined in

[packages/solid/src/resource/Resource.ts:336](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L336)

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

[packages/solid/src/resource/Resource.ts:283](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L283)

___

### listenerCount

▸ **listenerCount**\<`E`\>(`event`): `number`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

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

▸ **listeners**\<`E`\>(`event`): \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

\{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Inherited from

[Resource](Resource.md).[listeners](Resource.md#listeners)

#### Defined in

node_modules/typed-emitter/index.d.ts:36

___

### off

▸ **off**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[off](Resource.md#off)

#### Defined in

node_modules/typed-emitter/index.d.ts:28

___

### on

▸ **on**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[on](Resource.md#on)

#### Defined in

node_modules/typed-emitter/index.d.ts:23

___

### onNotification

▸ **onNotification**(`message`): `Promise`\<`void`\>

Function that triggers whenever a notification is recieved.

#### Parameters

| Name | Type |
| :------ | :------ |
| `message` | `NotificationMessage` |

#### Returns

`Promise`\<`void`\>

#### Inherited from

[Resource](Resource.md).[onNotification](Resource.md#onnotification)

#### Defined in

[packages/solid/src/resource/Resource.ts:777](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L777)

___

### once

▸ **once**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[once](Resource.md#once)

#### Defined in

node_modules/typed-emitter/index.d.ts:24

___

### prependListener

▸ **prependListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[prependListener](Resource.md#prependlistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:25

___

### prependOnceListener

▸ **prependOnceListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[prependOnceListener](Resource.md#prependoncelistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:26

___

### rawListeners

▸ **rawListeners**\<`E`\>(`event`): \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |

#### Returns

\{ `notification`: () => `void` ; `update`: () => `void`  }[`E`][]

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

[packages/solid/src/resource/Container.ts:146](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L146)

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

[packages/solid/src/resource/Container.ts:192](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L192)

___

### removeAllListeners

▸ **removeAllListeners**\<`E`\>(`event?`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `E` |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[removeAllListeners](Resource.md#removealllisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:29

___

### removeListener

▸ **removeListener**\<`E`\>(`event`, `listener`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` \| ``"notification"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event` | `E` |
| `listener` | \{ `notification`: () => `void` ; `update`: () => `void`  }[`E`] |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[removeListener](Resource.md#removelistener)

#### Defined in

node_modules/typed-emitter/index.d.ts:30

___

### setMaxListeners

▸ **setMaxListeners**(`maxListeners`): `this`

#### Parameters

| Name | Type |
| :------ | :------ |
| `maxListeners` | `number` |

#### Returns

`this`

#### Inherited from

[Resource](Resource.md).[setMaxListeners](Resource.md#setmaxlisteners)

#### Defined in

node_modules/typed-emitter/index.d.ts:40

___

### setWac

▸ **setWac**(`wacRule`): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `NotFoundHttpError` \| [`SetWacRuleSuccess`](../interfaces/SetWacRuleSuccess.md)\>

Sets access rules for a specific resource

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `wacRule` | [`WacRule`](../interfaces/WacRule.md) | the access rules to set |

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `NotFoundHttpError` \| [`SetWacRuleSuccess`](../interfaces/SetWacRuleSuccess.md)\>

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

[Resource](Resource.md).[setWac](Resource.md#setwac)

#### Defined in

[packages/solid/src/resource/Resource.ts:708](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L708)

___

### subscribeToNotifications

▸ **subscribeToNotifications**(`callbacks?`): `Promise`\<`string`\>

Activates Websocket subscriptions on this resource. Updates, deletions,
and creations on this resource will be tracked and all changes will be
relected in LDO's resources and graph.

#### Parameters

| Name | Type |
| :------ | :------ |
| `callbacks?` | `SubscriptionCallbacks` |

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

[Resource](Resource.md).[subscribeToNotifications](Resource.md#subscribetonotifications)

#### Defined in

[packages/solid/src/resource/Resource.ts:765](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L765)

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

[packages/solid/src/resource/Container.ts:157](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L157)

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

[Resource](Resource.md).[unsubscribeFromAllNotifications](Resource.md#unsubscribefromallnotifications)

#### Defined in

[packages/solid/src/resource/Resource.ts:831](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L831)

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

[Resource](Resource.md).[unsubscribeFromNotifications](Resource.md#unsubscribefromnotifications)

#### Defined in

[packages/solid/src/resource/Resource.ts:814](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L814)

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

[packages/solid/src/resource/Resource.ts:461](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L461)

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

[packages/solid/src/resource/Resource.ts:432](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L432)

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

[packages/solid/src/resource/Container.ts:125](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L125)

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

[packages/solid/src/resource/Container.ts:449](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L449)

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

[packages/solid/src/resource/Container.ts:478](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Container.ts#L478)
