# Class: Resource

Represents the current status of a specific Resource on a Pod as known by LDO.

## Hierarchy

- `TypedEventEmitter`\<\{ `notification`: () => `void` ; `update`: () => `void`  }, `this`\>

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
  notification: () &#x3D;\&gt; void;
}\&gt;).constructor

#### Defined in

[packages/solid/src/resource/Resource.ts:118](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L118)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Defined in

[packages/solid/src/resource/Resource.ts:95](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L95)

___

### context

• `Protected` `Readonly` **context**: [`SolidLdoDatasetContext`](../interfaces/SolidLdoDatasetContext.md)

The SolidLdoDatasetContext from the Parent Dataset

#### Defined in

[packages/solid/src/resource/Resource.ts:62](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L62)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Defined in

[packages/solid/src/resource/Resource.ts:89](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L89)

___

### notificationSubscription

• `Protected` **notificationSubscription**: `NotificationSubscription`

Handles notification subscriptions

#### Defined in

[packages/solid/src/resource/Resource.ts:113](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L113)

___

### requester

• `Protected` `Readonly` `Abstract` **requester**: `BatchedRequester`

Batched Requester for the Resource

#### Defined in

[packages/solid/src/resource/Resource.ts:83](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L83)

___

### status

• `Abstract` **status**: `RequesterResult`

The status of the last request made for this resource

#### Defined in

[packages/solid/src/resource/Resource.ts:77](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L77)

___

### type

• `Readonly` `Abstract` **type**: `string`

The type of resource (leaf or container)

#### Defined in

[packages/solid/src/resource/Resource.ts:72](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L72)

___

### uri

• `Readonly` `Abstract` **uri**: `string`

The uri of the resource

#### Defined in

[packages/solid/src/resource/Resource.ts:67](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L67)

___

### wacRule

• `Protected` `Optional` **wacRule**: [`WacRule`](../interfaces/WacRule.md)

If a wac rule was fetched, it is cached here

#### Defined in

[packages/solid/src/resource/Resource.ts:107](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L107)

___

### wacUri

• `Protected` `Optional` **wacUri**: [`LeafUri`](../types/LeafUri.md)

If a wac uri is fetched, it is cached here

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).addListener

#### Defined in

node_modules/typed-emitter/index.d.ts:22

___

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

Creates a resource at this URI and overwrites any that already exists

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

CreateAndOverwriteResult

**`Example`**

```typescript
const result = await resource.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:481](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L481)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

Creates a resource at this URI if the resource doesn't already exist

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `CreateSuccess` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

CreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/solid/src/resource/Resource.ts:517](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L517)

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
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

[packages/solid/src/resource/Resource.ts:350](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L350)

___

### eventNames

▸ **eventNames**(): (`string` \| `symbol`)[]

#### Returns

(`string` \| `symbol`)[]

#### Inherited from

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
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
  notification: () =\> void;
}\>).getMaxListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:39

___

### getParentContainer

▸ **getParentContainer**(): `Promise`\<`undefined` \| [`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

#### Returns

`Promise`\<`undefined` \| [`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

#### Defined in

[packages/solid/src/resource/Resource.ts:568](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L568)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| `NoRootContainerError`\>

Gets the root container for this resource.

#### Returns

`Promise`\<[`Container`](Container.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| `NoRootContainerError`\>

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

[packages/solid/src/resource/Resource.ts:564](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L564)

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

#### Defined in

[packages/solid/src/resource/Resource.ts:530](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L530)

___

### handleDelete

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

Helper method that handles the core functions for deleting a resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\>

DeleteResult

#### Defined in

[packages/solid/src/resource/Resource.ts:442](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L442)

___

### handleRead

▸ **handleRead**(): `Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`\>

ReadResult

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

#### Defined in

[packages/solid/src/resource/Resource.ts:239](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L239)

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).listenerCount

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).listeners

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).off

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).on

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).once

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).prependListener

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).prependOnceListener

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).rawListeners

#### Defined in

node_modules/typed-emitter/index.d.ts:35

___

### read

▸ **read**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

Reads the resource

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

#### Defined in

[packages/solid/src/resource/Resource.ts:402](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L402)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

Reads the resource if it isn't fetched yet

#### Returns

`Promise`\<`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>\>

a ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:410](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L410)

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
}\>).removeAllListeners

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

(EventEmitter as new () =\> TypedEmitter\<\{
  update: () =\> void;
  notification: () =\> void;
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
  notification: () =\> void;
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

#### Defined in

[packages/solid/src/resource/Resource.ts:765](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L765)

___

### toReadResult

▸ **toReadResult**(): `ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>

Converts the current state of this resource to a readResult

#### Returns

`ResourceResult`\<`UnexpectedResourceError` \| `NoncompliantPodError` \| `ServerHttpError` \| `UnexpectedHttpError` \| `UnauthenticatedHttpError` \| `UnauthorizedHttpError` \| `BinaryReadSuccess` \| `DataReadSuccess` \| `ContainerReadSuccess` \| `AbsentReadSuccess`, [`Container`](Container.md) \| [`Leaf`](Leaf.md)\>

a ReadResult

#### Defined in

[packages/solid/src/resource/Resource.ts:394](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L394)

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

#### Defined in

[packages/solid/src/resource/Resource.ts:432](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L432)

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

[packages/solid/src/resource/Resource.ts:370](https://github.com/o-development/ldo/blob/c70613a/packages/solid/src/resource/Resource.ts#L370)
