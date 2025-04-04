# Class: SolidResource

## Hierarchy

- `TypedEventEmitter`\<\{ `notification`: () => `void` ; `update`: () => `void`  }, `this`\>

  ↳ **`SolidResource`**

  ↳↳ [`SolidContainer`](SolidContainer.md)

  ↳↳ [`SolidLeaf`](SolidLeaf.md)

## Implements

- `Resource`\<[`SolidLeafUri`](../types/SolidLeafUri.md) \| [`SolidContainerUri`](../types/SolidContainerUri.md)\>

## Constructors

### constructor

• **new SolidResource**(`context`): [`SolidResource`](SolidResource.md)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `context` | `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\> | SolidLdoDatasetContext for the parent dataset |

#### Returns

[`SolidResource`](SolidResource.md)

#### Overrides

(EventEmitter as new () &#x3D;\&gt; ResourceEventEmitter).constructor

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:135](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L135)

## Properties

### absent

• `Protected` **absent**: `undefined` \| `boolean`

True if this resource has been fetched but does not exist

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:104](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L104)

___

### context

• `Protected` `Readonly` **context**: `ConnectedContext`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md)[]\>

The ConnectedContext from the Parent Dataset

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:69](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L69)

___

### didInitialFetch

• `Protected` **didInitialFetch**: `boolean` = `false`

True if this resource has been fetched at least once

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:98](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L98)

___

### isError

• `Readonly` **isError**: ``false``

Indicates that resources are not errors

#### Implementation of

Resource.isError

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:130](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L130)

___

### notificationSubscription

• `Protected` **notificationSubscription**: `NotificationSubscription`\<[`SolidConnectedPlugin`](../interfaces/SolidConnectedPlugin.md), [`SolidNotificationMessage`](../interfaces/SolidNotificationMessage.md)\>

Handles notification subscriptions

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:122](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L122)

___

### requester

• `Protected` `Readonly` `Abstract` **requester**: [`BatchedRequester`](BatchedRequester.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>

Batched Requester for the Resource

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:90](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L90)

___

### status

• `Abstract` **status**: `ConnectedResult`

The status of the last request made for this resource

#### Implementation of

Resource.status

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:84](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L84)

___

### type

• `Readonly` `Abstract` **type**: ``"SolidContainer"`` \| ``"SolidLeaf"``

The type of resource (leaf or container)

#### Implementation of

Resource.type

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:79](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L79)

___

### uri

• `Readonly` `Abstract` **uri**: [`SolidContainerUri`](../types/SolidContainerUri.md) \| [`SolidLeafUri`](../types/SolidLeafUri.md)

The uri of the resource

#### Implementation of

Resource.uri

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:74](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L74)

___

### wacRule

• `Protected` `Optional` **wacRule**: [`WacRule`](../interfaces/WacRule.md)

If a wac rule was fetched, it is cached here

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:116](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L116)

___

### wacUri

• `Protected` `Optional` **wacUri**: [`SolidLeafUri`](../types/SolidLeafUri.md)

If a wac uri is fetched, it is cached here

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:110](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L110)

## Methods

### createAndOverwrite

▸ **createAndOverwrite**(): `Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

Creates a resource at this URI and overwrites any that already exists

#### Returns

`Promise`\<[`ContainerCreateAndOverwriteResult`](../types/ContainerCreateAndOverwriteResult.md) \| [`LeafCreateAndOverwriteResult`](../types/LeafCreateAndOverwriteResult.md)\>

CreateAndOverwriteResult

**`Example`**

```typescript
const result = await resource.createAndOverwrite();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:493](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L493)

___

### createIfAbsent

▸ **createIfAbsent**(): `Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

Creates a resource at this URI if the resource doesn't already exist

#### Returns

`Promise`\<[`ContainerCreateIfAbsentResult`](../types/ContainerCreateIfAbsentResult.md) \| [`LeafCreateIfAbsentResult`](../types/LeafCreateIfAbsentResult.md)\>

CreateIfAbsentResult

**`Example`**

```typescript
const result = await leaf.createIfAbsent();
if (!result.isError) {
  // Do something
}
```

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:526](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L526)

___

### emitThisAndParent

▸ **emitThisAndParent**(): `void`

Emits an update event for both this resource and the parent

#### Returns

`void`

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:367](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L367)

___

### getParentContainer

▸ **getParentContainer**(): `Promise`\<`undefined` \| [`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

#### Returns

`Promise`\<`undefined` \| [`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md)\>

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:585](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L585)

___

### getRootContainer

▸ **getRootContainer**(): `Promise`\<[`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`NoRootContainerError`](NoRootContainerError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

Gets the root container for this resource.

#### Returns

`Promise`\<[`SolidContainer`](SolidContainer.md) \| [`CheckRootResultError`](../types/CheckRootResultError.md) \| [`NoRootContainerError`](NoRootContainerError.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

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

[packages/connected-solid/src/resources/SolidResource.ts:579](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L579)

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

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:536](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L536)

___

### handleDelete

▸ **handleDelete**(): `Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

Helper method that handles the core functions for deleting a resource

#### Returns

`Promise`\<[`DeleteResult`](../types/DeleteResult.md)\<[`SolidContainer`](SolidContainer.md) \| [`SolidLeaf`](SolidLeaf.md)\>\>

DeleteResult

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:452](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L452)

___

### handleRead

▸ **handleRead**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

A helper method that handles the core functions for reading

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

ReadResult

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

#### Implementation of

Resource.isAbsent

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

#### Implementation of

Resource.isDoingInitialFetch

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

#### Implementation of

Resource.isFetched

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

#### Implementation of

Resource.isLoading

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

#### Implementation of

Resource.isPresent

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

#### Implementation of

Resource.isSubscribedToNotifications

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

#### Implementation of

Resource.isUnfetched

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

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:799](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L799)

___

### read

▸ **read**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

Reads the resource

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

#### Implementation of

Resource.read

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:416](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L416)

___

### readIfUnfetched

▸ **readIfUnfetched**(): `Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

Reads the resource if it isn't fetched yet

#### Returns

`Promise`\<[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)\>

a ReadResult

#### Implementation of

Resource.readIfUnfetched

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:422](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L422)

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

#### Implementation of

Resource.subscribeToNotifications

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:787](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L787)

___

### toReadResult

▸ **toReadResult**(): [`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)

Converts the current state of this resource to a readResult

#### Returns

[`ReadContainerResult`](../types/ReadContainerResult.md) \| [`ReadLeafResult`](../types/ReadLeafResult.md)

a ReadResult

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:411](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L411)

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

#### Implementation of

Resource.unsubscribeFromAllNotifications

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

#### Implementation of

Resource.unsubscribeFromNotifications

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:834](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L834)

___

### update

▸ **update**(`datasetChanges`): `Promise`\<`IgnoredInvalidUpdateSuccess`\<[`SolidContainer`](SolidContainer.md)\> \| [`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

UPDATE METHODS

#### Parameters

| Name | Type |
| :------ | :------ |
| `datasetChanges` | `DatasetChanges`\<`BaseQuad`\> |

#### Returns

`Promise`\<`IgnoredInvalidUpdateSuccess`\<[`SolidContainer`](SolidContainer.md)\> \| [`UpdateResult`](../types/UpdateResult.md)\<[`SolidLeaf`](SolidLeaf.md)\>\>

#### Implementation of

Resource.update

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:550](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L550)

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

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:442](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L442)

___

### updateWithReadSuccess

▸ **updateWithReadSuccess**(`result`): `void`

A helper method updates this resource's internal state upon read success

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `result` | `ReadSuccess`\<`Resource`\<`string`\>\> | the result of the read success |

#### Returns

`void`

#### Defined in

[packages/connected-solid/src/resources/SolidResource.ts:387](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/resources/SolidResource.ts#L387)
