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

[packages/solid/src/resource/Resource.ts:101](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L101)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Defined in

[packages/solid/src/resource/Resource.ts:84](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L84)

___

### context

• `Protected` `Readonly` **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

The SolidLdoDatasetContext from the Parent Dataset

#### Defined in

[packages/solid/src/resource/Resource.ts:51](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L51)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Defined in

[packages/solid/src/resource/Resource.ts:78](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L78)

___

### requester

• `Protected` `Readonly` `Abstract` **requester**: `BatchedRequester`

Batched Requester for the Resource

#### Defined in

[packages/solid/src/resource/Resource.ts:72](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L72)

___

### status

• `Abstract` **status**: `RequesterResult`

The status of the last request made for this resource

#### Defined in

[packages/solid/src/resource/Resource.ts:66](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L66)

___

### type

• `Readonly` `Abstract` **type**: `string`

The type of resource (leaf or container)

#### Defined in

[packages/solid/src/resource/Resource.ts:61](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L61)

___

### uri

• `Readonly` `Abstract` **uri**: `string`

The uri of the resource

#### Defined in

[packages/solid/src/resource/Resource.ts:56](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L56)

___

### wacRule

• `Protected` `Optional` **wacRule**: [`WacRule`](../interfaces/WacRule.md)

If a wac rule was fetched, it is cached here

#### Defined in

[packages/solid/src/resource/Resource.ts:96](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L96)

___

### wacUri

• `Protected` `Optional` **wacUri**: [`LeafUri`](../types/LeafUri.md)

If a wac uri is fetched, it is cached here

#### Defined in

[packages/solid/src/resource/Resource.ts:90](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L90)

## Methods

### addListener

▸ **addListener**\<`E`\>(`event`, `listener`): `this`

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

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).addListener

#### Defined in

node_modules/typed-emitter/index.d.ts:22

___

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Creates a resource at this URI and overwrites any that already exists

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

CreateAndOverwriteResult

**`Example`**

```typescript
const result = await resource.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:444](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L444)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Creates a resource at this URI if the resource doesn't already exist

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

CreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:480](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L480)

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

[packages/solid/src/resource/Resource.ts:313](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L313)

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

### getParentContainer

▸ **getParentContainer**(): `Promise`\<`undefined` \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

#### Returns

`Promise`\<`undefined` \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`Container`](Container.md)\>

#### Defined in

[packages/solid/src/resource/Resource.ts:529](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L529)

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

[packages/solid/src/resource/Resource.ts:527](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L527)

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

#### Defined in

[packages/solid/src/resource/Resource.ts:596](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L596)

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

#### Defined in

[packages/solid/src/resource/Resource.ts:545](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L545)

___

### handleCreateAndOverwrite

▸ **handleCreateAndOverwrite**(): `Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`\>

Helper method that handles the core functions for creating and overwriting
a resource

#### Returns

`Promise`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`\>

DeleteResult

#### Defined in

[packages/solid/src/resource/Resource.ts:457](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L457)

___

### handleCreateIfAbsent

▸ **handleCreateIfAbsent**(): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`\>

Helper method that handles the core functions for creating a resource if
 absent

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`\>

DeleteResult

#### Defined in

[packages/solid/src/resource/Resource.ts:493](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L493)

___

### handleDelete

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

Helper method that handles the core functions for deleting a resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

DeleteResult

#### Defined in

[packages/solid/src/resource/Resource.ts:405](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L405)

___

### handleRead

▸ **handleRead**(): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:343](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L343)

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

[packages/solid/src/resource/Resource.ts:280](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L280)

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

[packages/solid/src/resource/Resource.ts:144](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L144)

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

[packages/solid/src/resource/Resource.ts:180](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L180)

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

[packages/solid/src/resource/Resource.ts:198](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L198)

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

[packages/solid/src/resource/Resource.ts:242](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L242)

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

[packages/solid/src/resource/Resource.ts:126](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L126)

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

[packages/solid/src/resource/Resource.ts:299](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L299)

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

[packages/solid/src/resource/Resource.ts:162](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L162)

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

[packages/solid/src/resource/Resource.ts:217](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L217)

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

[packages/solid/src/resource/Resource.ts:261](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L261)

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

▸ **off**\<`E`\>(`event`, `listener`): `this`

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

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).off

#### Defined in

node_modules/typed-emitter/index.d.ts:28

___

### on

▸ **on**\<`E`\>(`event`, `listener`): `this`

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

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).on

#### Defined in

node_modules/typed-emitter/index.d.ts:23

___

### once

▸ **once**\<`E`\>(`event`, `listener`): `this`

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

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).once

#### Defined in

node_modules/typed-emitter/index.d.ts:24

___

### prependListener

▸ **prependListener**\<`E`\>(`event`, `listener`): `this`

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

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).prependListener

#### Defined in

node_modules/typed-emitter/index.d.ts:25

___

### prependOnceListener

▸ **prependOnceListener**\<`E`\>(`event`, `listener`): `this`

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

`this`

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

▸ **read**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Reads the resource

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

#### Defined in

[packages/solid/src/resource/Resource.ts:365](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L365)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

Reads the resource if it isn't fetched yet

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>\>

a ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:373](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L373)

___

### removeAllListeners

▸ **removeAllListeners**\<`E`\>(`event?`): `this`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `E` | extends ``"update"`` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `event?` | `E` |

#### Returns

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).removeAllListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:29

___

### removeListener

▸ **removeListener**\<`E`\>(`event`, `listener`): `this`

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

`this`

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).removeListener

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
}\>).setMaxListeners

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

#### Defined in

[packages/solid/src/resource/Resource.ts:669](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L669)

___

### toReadResult

▸ **toReadResult**(): `ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>

Converts the current state of this resource to a readResult

#### Returns

`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Leaf`](Leaf.md) \| [`Container`](Container.md)\>

a ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:357](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L357)

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

[packages/solid/src/resource/Resource.ts:424](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L424)

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

[packages/solid/src/resource/Resource.ts:395](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L395)

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

[packages/solid/src/resource/Resource.ts:333](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/Resource.ts#L333)
