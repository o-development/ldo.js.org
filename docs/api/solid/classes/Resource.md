# Class: Resource

Represents the current status of a specific Resource on a Pod as known by LDO.

## Hierarchy

- `TypedEventEmitter`\<\{ `update`: () => `void`  }, `this`\>

  ↳ **`Resource`**

  ↳↳ [`Container`](Container.md)

  ↳↳ [`Leaf`](Leaf.md)

## Constructors

### constructor

• **new Resource**(`context`): [`Resource`](Resource.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md) | SolidLdoDatasetContext for the parent dataset |

#### Returns

[`Resource`](Resource.md)

#### Overrides

(EventEmitter as new () &#x3D;\&gt; TypedEmitter\&lt;\{
  update: () &#x3D;\&gt; void;
}\&gt;).constructor

#### Defined in

[packages/solid/src/resource/Resource.ts:85](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L85)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Defined in

[packages/solid/src/resource/Resource.ts:80](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L80)

___

### context

• `Protected` `Readonly` **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

The SolidLdoDatasetContext from the Parent Dataset

#### Defined in

[packages/solid/src/resource/Resource.ts:47](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L47)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Defined in

[packages/solid/src/resource/Resource.ts:74](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L74)

___

### requester

• `Protected` `Readonly` `Abstract` **requester**: `BatchedRequester`

Batched Requester for the Resource

#### Defined in

[packages/solid/src/resource/Resource.ts:68](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L68)

___

### status

• `Abstract` **status**: `RequesterResult`

The status of the last request made for this resource

#### Defined in

[packages/solid/src/resource/Resource.ts:62](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L62)

___

### type

• `Readonly` `Abstract` **type**: `string`

The type of resource (leaf or container)

#### Defined in

[packages/solid/src/resource/Resource.ts:57](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L57)

___

### uri

• `Readonly` `Abstract` **uri**: `string`

The uri of the resource

#### Defined in

[packages/solid/src/resource/Resource.ts:52](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L52)

## Methods

### addListener

▸ **addListener**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).addListener

#### Defined in

node_modules/typed-emitter/index.d.ts:22

___

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Creates a resource at this URI and overwrites any that already exists

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

CreateAndOverwriteResult

**`Example`**

```typescript
const result = await resource.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:428](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L428)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Creates a resource at this URI if the resource doesn't already exist

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

CreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:464](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L464)

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).emit

#### Defined in

node_modules/typed-emitter/index.d.ts:32

___

### emitThisAndParent

▸ **emitThisAndParent**(): `void`

Emits an update event for both this resource and the parent

#### Returns

`void`

#### Defined in

[packages/solid/src/resource/Resource.ts:297](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L297)

___

### eventNames

▸ **eventNames**(): (`string` \| `symbol`)[]

#### Returns

(`string` \| `symbol`)[]

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).eventNames

#### Defined in

node_modules/typed-emitter/index.d.ts:34

___

### getMaxListeners

▸ **getMaxListeners**(): `number`

#### Returns

`number`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).getMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:39

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

Gets the root container for this resource.

#### Returns

`Promise`\<[`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

The root container for this resource

**`Example`**

Suppose the root container is at `https://example.com/`

```typescript
const resource = ldoSolidDataset
  .getResource("https://example.com/container/resource.ttl");
const rootContainer = await resource.getRootContainer();
if (!rootContainer.isError) {
  // logs "https://example.com/"
  console.log(rootContainer.uri);
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:511](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L511)

___

### handleCreateAndOverwrite

▸ **handleCreateAndOverwrite**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`\>

Helper method that handles the core functions for creating and overwriting
a resource

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `CreateSuccess`\>

DeleteResult

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

#### Defined in

[packages/solid/src/resource/Resource.ts:477](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L477)

___

### handleDelete

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

Helper method that handles the core functions for deleting a resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

DeleteResult

#### Defined in

[packages/solid/src/resource/Resource.ts:389](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L389)

___

### handleRead

▸ **handleRead**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

ReadResult

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).listenerCount

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).listeners

#### Defined in

node_modules/typed-emitter/index.d.ts:36

___

### off

▸ **off**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).off

#### Defined in

node_modules/typed-emitter/index.d.ts:28

___

### on

▸ **on**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).on

#### Defined in

node_modules/typed-emitter/index.d.ts:23

___

### once

▸ **once**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).once

#### Defined in

node_modules/typed-emitter/index.d.ts:24

___

### prependListener

▸ **prependListener**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).prependListener

#### Defined in

node_modules/typed-emitter/index.d.ts:25

___

### prependOnceListener

▸ **prependOnceListener**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).prependOnceListener

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).rawListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:35

___

### read

▸ **read**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Reads the resource

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Defined in

[packages/solid/src/resource/Resource.ts:349](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L349)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Reads the resource if it isn't fetched yet

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

a ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:357](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L357)

___

### removeAllListeners

▸ **removeAllListeners**\<`E`\>(`event?`): [`Resource`](Resource.md)

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `E` |

#### Returns

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).removeAllListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:29

___

### removeListener

▸ **removeListener**\<`E`\>(`event`, `listener`): [`Resource`](Resource.md)

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

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).removeListener

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

#### Defined in

[packages/solid/src/resource/Resource.ts:518](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L518)

___

### setMaxListeners

▸ **setMaxListeners**(`maxListeners`): [`Resource`](Resource.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `maxListeners` | `number` |

#### Returns

[`Resource`](Resource.md)

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).setMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:40

___

### toReadResult

▸ **toReadResult**(): `ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>

Converts the current state of this resource to a readResult

#### Returns

`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `NoncompliantPodError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>

a ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:341](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L341)

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

#### Defined in

[packages/solid/src/resource/Resource.ts:379](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L379)

___

### updateWithReadSuccess

▸ **updateWithReadSuccess**(`result`): `void`

A helper method updates this resource's internal state upon read success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | `ReadSuccess` | the result of the read success |

#### Returns

`void`

#### Defined in

[packages/solid/src/resource/Resource.ts:317](https://github.com/o-development/ldo/blob/b955d3b/packages/solid/src/resource/Resource.ts#L317)
