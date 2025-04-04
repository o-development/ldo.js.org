# Class: SolidContainer

Represents the current status of a specific container on a Pod as known by
LDO.

**`Example`**

```typescript
const container = solidLdoDataset
  .getResource("https://example.com/container/");
```

## Hierarchy

- [`SolidResource`](SolidResource.md)

  ↳ **`SolidContainer`**

## Constructors

### constructor

• **new SolidContainer**(`uri`, `context`): [`SolidContainer`](SolidContainer.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `uri` | [`SolidContainerUri`](../types/SolidContainerUri.md) | The uri of the container |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> | SolidLdoDatasetContext for the parent dataset |

#### Returns

[`SolidContainer`](SolidContainer.md)

#### Overrides

[SolidResource](SolidResource.md).[constructor](SolidResource.md#constructor)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:96](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L96)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Inherited from

[SolidResource](SolidResource.md).[absent](SolidResource.md#absent)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:104](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L104)

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

[packages/connected-solid/src/resources/SolidContainer.ts:80](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L80)

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

• `Protected` **requester**: [`ContainerBatchedRequester`](ContainerBatchedRequester.md)

Batched Requester for the Container

#### Overrides

[SolidResource](SolidResource.md).[requester](SolidResource.md#requester)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:64](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L64)

___

### rootContainer

• `Protected` **rootContainer**: `undefined` \| `boolean`

True if this is the root container, false if not, undefined if unknown

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:70](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L70)

___

### status

• **status**: [`CheckRootContainerSuccess`](CheckRootContainerSuccess.md) \| [`ContainerReadSuccess`](ContainerReadSuccess.md) \| `AbsentReadSuccess`\<[`SolidContainer`](SolidContainer.md)\> \| [`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md)\> \| [`CreateSuccess`](CreateSuccess.md)\<[`SolidContainer`](SolidContainer.md)\> \| `Unfetched`\<[`SolidContainer`](SolidContainer.md)\> \| [`DeleteSuccess`](DeleteSuccess.md)\<[`SolidContainer`](SolidContainer.md)\>

The status of the last request made for this container

#### Overrides

[SolidResource](SolidResource.md).[status](SolidResource.md#status)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:85](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L85)

___

### type

• `Readonly` **type**: ``"SolidContainer"``

Indicates that this resource is a container resource

#### Overrides

[SolidResource](SolidResource.md).[type](SolidResource.md#type)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:75](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L75)

___

### uri

• `Readonly` **uri**: [`SolidContainerUri`](../types/SolidContainerUri.md)

The URI of the container

#### Overrides

[SolidResource](SolidResource.md).[uri](SolidResource.md#uri)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:58](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L58)

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

### checkIfIsRootContainer

▸ **checkIfIsRootContainer**(): `Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

Checks if this container is a root container by making a request

#### Returns

`Promise`\<[`CheckRootResult`](../types/CheckRootResult.md)\>

CheckRootResult

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:219](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L219)

___

### child

▸ **child**(`slug`): [`SolidContainer`](SolidContainer.md)

Returns a child resource with a given name (slug)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`SolidContainerSlug`](../types/SolidContainerSlug.md) | the given name for that child resource |

#### Returns

[`SolidContainer`](SolidContainer.md)

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

[packages/connected-solid/src/resources/SolidContainer.ts:339](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L339)

▸ **child**(`slug`): [`SolidLeaf`](SolidLeaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`SolidLeafSlug`](../types/SolidLeafSlug.md) |

#### Returns

[`SolidLeaf`](SolidLeaf.md)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:340](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L340)

▸ **child**(`slug`): [`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:341](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L341)

___

### children

▸ **children**(): ([`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md))[]

Lists the currently cached children of this container (no request is made)

#### Returns

([`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md))[]

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

[packages/connected-solid/src/resources/SolidContainer.ts:308](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L308)

___

### clear

▸ **clear**(): `Promise`\<`AggregateSuccess`\<[`DeleteSuccess`](DeleteSuccess.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\> \| `AggregateError`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>\>

Deletes all contents in this container

#### Returns

`Promise`\<`AggregateSuccess`\<[`DeleteSuccess`](DeleteSuccess.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\> \| `AggregateError`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>\>

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

[packages/connected-solid/src/resources/SolidContainer.ts:488](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L488)

___

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

Creates a container at this URI and overwrites any that already exists

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

ContainerCreateAndOverwriteResult

**`Example`**

```typescript
const result = await container.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[SolidResource](SolidResource.md).[createAndOverwrite](SolidResource.md#createandoverwrite)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:556](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L556)

___

### createChildAndOverwrite

▸ **createChildAndOverwrite**(`slug`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

Creates a resource and overwrites any existing resource that existed at the
URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`SolidContainerSlug`](../types/SolidContainerSlug.md) | the name of the resource |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md)\>

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

[packages/connected-solid/src/resources/SolidContainer.ts:371](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L371)

▸ **createChildAndOverwrite**(`slug`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`SolidLeafSlug`](../types/SolidLeafSlug.md) |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:374](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L374)

▸ **createChildAndOverwrite**(`slug`): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:377](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L377)

___

### createChildIfAbsent

▸ **createChildIfAbsent**(`slug`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

Creates a resource only if that resource doesn't already exist on the Solid
Pod

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`SolidContainerSlug`](../types/SolidContainerSlug.md) | the name of the resource |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

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

[packages/connected-solid/src/resources/SolidContainer.ts:403](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L403)

▸ **createChildIfAbsent**(`slug`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | [`SolidLeafSlug`](../types/SolidLeafSlug.md) |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:406](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L406)

▸ **createChildIfAbsent**(`slug`): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `slug` | `string` |

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:407](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L407)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

Creates a container at this URI if the container doesn't already exist

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md)\>

ContainerCreateIfAbsentResult

**`Example`**

```typescript
const result = await container.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Overrides

[SolidResource](SolidResource.md).[createIfAbsent](SolidResource.md#createifabsent)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:575](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L575)

___

### delete

▸ **delete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md)\> \| `AggregateError`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>\>

Deletes this container and all its contents

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md)\> \| `AggregateError`\<[`ServerHttpError`](ServerHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnexpectedHttpError`](UnexpectedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthenticatedHttpError`](UnauthenticatedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`UnauthorizedHttpError`](UnauthorizedHttpError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| [`NoncompliantPodError`](NoncompliantPodError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\> \| `UnexpectedResourceError`\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>\>

A Delete result for this container

```typescript
const result = await container.delete();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:526](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L526)

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

### getParentContainer

▸ **getParentContainer**(): `Promise`\<`undefined` \| [`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

Gets the parent container for this container by making a request

#### Returns

`Promise`\<`undefined` \| [`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

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

[SolidResource](SolidResource.md).[getParentContainer](SolidResource.md#getparentcontainer)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:279](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L279)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`NoRootContainerError`](NoRootContainerError.md)\<[`SolidContainer`](SolidContainer.md)\>\>

Gets the root container of this container. If this container is the root
container, this function returns itself.

#### Returns

`Promise`\<[`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`NoRootContainerError`](NoRootContainerError.md)\<[`SolidContainer`](SolidContainer.md)\>\>

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

[SolidResource](SolidResource.md).[getRootContainer](SolidResource.md#getrootcontainer)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:247](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L247)

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

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md)\>\>

Helper method that handles the core functions for deleting a resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md)\>\>

DeleteResult

#### Overrides

[SolidResource](SolidResource.md).[handleDelete](SolidResource.md#handledelete)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:540](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L540)

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

[packages/connected-solid/src/resources/SolidContainer.ts:122](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L122)

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

▸ **read**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

Reads the container

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

A read result

**`Example`**

```typescript
const result = await container.read();
if (result.isError) {
  // Do something
}
```

#### Overrides

[SolidResource](SolidResource.md).[read](SolidResource.md#read)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:158](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L158)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

Makes a request to read this container if it hasn't been fetched yet. If it
has, return the cached informtation

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md)\>

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

[SolidResource](SolidResource.md).[readIfUnfetched](SolidResource.md#readifunfetched)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:204](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L204)

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

▸ **toReadResult**(): [`ReadContainerResult`](../types/ReadContainerResult.md)

Converts the current state of this container to a readResult

#### Returns

[`ReadContainerResult`](../types/ReadContainerResult.md)

a ReadContainerResult

#### Overrides

[SolidResource](SolidResource.md).[toReadResult](SolidResource.md#toreadresult)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:169](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L169)

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

▸ **update**(`_datasetChanges`): `Promise`\<`IgnoredInvalidUpdateSuccess`\<[`SolidContainer`](SolidContainer.md)\>\>

You cannot update a Container, so we return an IgnoredInvalidUpdateSuccess

#### Parameters

| Name | Type |
| :------ | :------ |
| `_datasetChanges` | `DatasetChanges`\<`BaseQuad`\> |

#### Returns

`Promise`\<`IgnoredInvalidUpdateSuccess`\<[`SolidContainer`](SolidContainer.md)\>\>

#### Overrides

[SolidResource](SolidResource.md).[update](SolidResource.md#update)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:585](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L585)

___

### updateWithCreateSuccess

▸ **updateWithCreateSuccess**(`result`): `void`

A helper method updates this resource's internal state upon create success

#### Parameters

| Name | Type |
| :------ | :------ |
| `result` | `ResourceSuccess`\<`Resource`\<`string`\>\> |

#### Returns

`void`

#### Inherited from

[SolidResource](SolidResource.md).[updateWithCreateSuccess](SolidResource.md#updatewithcreatesuccess)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:473](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L473)

___

### updateWithDeleteSuccess

▸ **updateWithDeleteSuccess**(`_result`): `void`

A helper method updates this resource's internal state upon delete success

#### Parameters

| Name | Type |
| :------ | :------ |
| `_result` | [`DeleteSuccess`](DeleteSuccess.md)\<[`SolidResource`](SolidResource.md)\> |

#### Returns

`void`

#### Inherited from

[SolidResource](SolidResource.md).[updateWithDeleteSuccess](SolidResource.md#updatewithdeletesuccess)

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:442](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L442)

___

### updateWithReadSuccess

▸ **updateWithReadSuccess**(`result`): `void`

A helper method updates this container's internal state upon read success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | [`ContainerReadSuccess`](ContainerReadSuccess.md) \| `ReadSuccess`\<[`SolidContainer`](SolidContainer.md)\> | the result of the read success |

#### Returns

`void`

#### Overrides

[SolidResource](SolidResource.md).[updateWithReadSuccess](SolidResource.md#updatewithreadsuccess)

#### Defined in

[packages/connected-solid/src/resources/SolidContainer.ts:137](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L137)

___

### uploadChildAndOverwrite

▸ **uploadChildAndOverwrite**(`slug`, `blob`, `mimeType`): `Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Creates a new binary resource and overwrites any existing resource that
existed at the URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`SolidLeafSlug`](../types/SolidLeafSlug.md) | the name of the resource |
| `blob` | `Blob` | - |
| `mimeType` | `string` | - |

#### Returns

`Promise`\<[`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

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

[packages/connected-solid/src/resources/SolidContainer.ts:437](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L437)

___

### uploadChildIfAbsent

▸ **uploadChildIfAbsent**(`slug`, `blob`, `mimeType`): `Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

Creates a new binary resource and overwrites any existing resource that
existed at the URI

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `slug` | [`SolidLeafSlug`](../types/SolidLeafSlug.md) | the name of the resource |
| `blob` | `Blob` | - |
| `mimeType` | `string` | - |

#### Returns

`Promise`\<[`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

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

[packages/connected-solid/src/resources/SolidContainer.ts:466](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidContainer.ts#L466)
