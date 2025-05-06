# Class: ResourceLinkQuery\<Type, QueryInput, Plugins\>

Represents a query over multiple datasources and constituting muliple
resources.

**`Example`**

```typescript
import { ProfileShapeType } from "./.ldo/Profile.shapeType.ts";

// Create a link query
const linkQuery = ldoDataset
  .usingType(ProfileShapeType)
  .startLinkQuery(
    "http://example.com/profile/card",
    "http://example.com/profile/card#me",
    {
      name: true,
        knows: {
          name: true,
        },
      },
    }
  );
// Susbscribe to this link query, automaticically updating the dataset when
// something from the link query is changed.
await linkQuery.subscribe();
```

## Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `QueryInput` | extends [`LQInput`](../types/LQInput.md)\<`Type`\> |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)[] |

## Implements

- [`ILinkQuery`](../interfaces/ILinkQuery.md)\<`Type`, `QueryInput`\>

## Constructors

### constructor

• **new ResourceLinkQuery**\<`Type`, `QueryInput`, `Plugins`\>(`parentDataset`, `shapeType`, `ldoBuilder`, `startingResource`, `startingSubject`, `linkQueryInput`): [`ResourceLinkQuery`](ResourceLinkQuery.md)\<`Type`, `QueryInput`, `Plugins`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `Type` | extends `LdoBase` |
| `QueryInput` | extends `Partial`\<\{ [key in string \| number \| symbol]: LQInputFlattenSet\<Type[key]\> }\> |
| `Plugins` | extends [`ConnectedPlugin`](../interfaces/ConnectedPlugin.md)\<`any`, `any`, `any`, `any`, `any`\>[] |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `parentDataset` | [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\> | The dataset for which this link query is a part |
| `shapeType` | `ShapeType`\<`Type`\> | A ShapeType for the link query to follow |
| `ldoBuilder` | [`IConnectedLdoBuilder`](../interfaces/IConnectedLdoBuilder.md)\<`Type`, `Plugins`\> | An LdoBuilder associated with the dataset |
| `startingResource` | `Plugins`[`number`][``"types"``][``"resource"``] | The resource to explore first in the link query |
| `startingSubject` | `string` \| `SubjectNode` | The starting point of the link query |
| `linkQueryInput` | `QueryInput` | A definition of the link query |

#### Returns

[`ResourceLinkQuery`](ResourceLinkQuery.md)\<`Type`, `QueryInput`, `Plugins`\>

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:73](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L73)

## Properties

### activeResourceSubscriptions

• `Protected` **activeResourceSubscriptions**: `Record`\<`string`, `string`\> = `{}`

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:53](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L53)

___

### curOnDataChanged

• `Protected` **curOnDataChanged**: `undefined` \| `nodeEventListener`\<`Quad`\>

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:57](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L57)

___

### ldoBuilder

• `Protected` **ldoBuilder**: [`IConnectedLdoBuilder`](../interfaces/IConnectedLdoBuilder.md)\<`Type`, `Plugins`\>

An LdoBuilder associated with the dataset

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:76](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L76)

___

### linkQueryInput

• `Protected` **linkQueryInput**: `QueryInput`

A definition of the link query

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:79](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L79)

___

### parentDataset

• `Protected` **parentDataset**: [`IConnectedLdoDataset`](../interfaces/IConnectedLdoDataset.md)\<`Plugins`\>

The dataset for which this link query is a part

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:74](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L74)

___

### previousTransactionId

• `Protected` **previousTransactionId**: `string` = `"INIT"`

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:50](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L50)

___

### resourcesWithSubscriptionInProgress

• `Protected` **resourcesWithSubscriptionInProgress**: `Record`\<`string`, `undefined` \| `Promise`\<`void`\>\> = `{}`

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:59](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L59)

___

### shapeType

• `Protected` **shapeType**: `ShapeType`\<`Type`\>

A ShapeType for the link query to follow

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:75](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L75)

___

### startingResource

• `Protected` **startingResource**: `Plugins`[`number`][``"types"``][``"resource"``]

The resource to explore first in the link query

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:77](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L77)

___

### startingSubject

• `Protected` **startingSubject**: `string` \| `SubjectNode`

The starting point of the link query

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:78](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L78)

___

### thisUnsubscribeIds

• `Protected` **thisUnsubscribeIds**: `Set`\<`string`\>

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:55](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L55)

## Methods

### fromSubject

▸ **fromSubject**(): [`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `QueryInput`\>\>

#### Returns

[`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `QueryInput`\>\>

#### Implementation of

[ILinkQuery](../interfaces/ILinkQuery.md).[fromSubject](../interfaces/ILinkQuery.md#fromsubject)

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:276](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L276)

___

### fullUnsubscribe

▸ **fullUnsubscribe**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:252](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L252)

___

### getSubscribedResources

▸ **getSubscribedResources**(): `Plugins`[`number`][``"types"``][``"resource"``][]

#### Returns

`Plugins`[`number`][``"types"``][``"resource"``][]

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:282](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L282)

___

### run

▸ **run**(`options?`): `Promise`\<[`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `QueryInput`\>\>\>

Runs this link query, returning the result

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `options?` | `Object` | Options for how to run the link query |
| `options.reload?` | `boolean` | - |

#### Returns

`Promise`\<[`ExpandDeep`](../types/ExpandDeep.md)\<[`LQReturn`](../types/LQReturn.md)\<`Type`, `QueryInput`\>\>\>

A subset of the ShapeType as defined by the LinkQuery

**`Example`**

```
import { ProfileShapeType } from "./.ldo/Profile.shapeType.ts";

// Create a link query
const linkQuery = ldoDataset
  .usingType(ProfileShapeType)
  .startLinkQuery(
    "http://example.com/profile/card",
    "http://example.com/profile/card#me",
    {
      name: true,
        knows: {
          name: true,
        },
      },
    }
  );
// Susbscribe to this link query, automaticically updating the dataset when
// something from the link query is changed.
const result = await linkQuery.read();
console.log(result.name);
result.knows.forEach((person) => console.log(person.name));
// The following will type-error. Despite "phone" existing on a Profile,
// it was not covered by the link query.
console.log(result.phone);
```

#### Implementation of

[ILinkQuery](../interfaces/ILinkQuery.md).[run](../interfaces/ILinkQuery.md#run)

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:115](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L115)

___

### subscribe

▸ **subscribe**(): `Promise`\<`string`\>

Subscribes to the data defined by the link query, updating the dataset if
any changes are made.

#### Returns

`Promise`\<`string`\>

An unsubscribeId

**`Example`**

```
import { ProfileShapeType } from "./.ldo/Profile.shapeType.ts";

// Create a link query
const linkQuery = ldoDataset
  .usingType(ProfileShapeType)
  .startLinkQuery(
    "http://example.com/profile/card",
    "http://example.com/profile/card#me",
    {
      name: true,
        knows: {
          name: true,
        },
      },
    }
  );
// Susbscribe to this link query, automaticically updating the dataset when
// something from the link query is changed.
const unsubscribeId = await linkQuery.subscribe();

// Now, let's imagine the following triple was added to
"http://example.com/profile/card":
<http://example.com/profile/card#me> <http://xmlns.com/foaf/0.1/knows> <http://example2.com/profile/card#me>
Because you're subscribed, the dataset will automatically be updated.

// End subscription
linkQuery.unsubscribe(unsubscribeId);
```

#### Implementation of

[ILinkQuery](../interfaces/ILinkQuery.md).[subscribe](../interfaces/ILinkQuery.md#subscribe)

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:165](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L165)

___

### unsubscribe

▸ **unsubscribe**(`unsubscribeId`): `Promise`\<`void`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `unsubscribeId` | `string` |

#### Returns

`Promise`\<`void`\>

#### Implementation of

[ILinkQuery](../interfaces/ILinkQuery.md).[unsubscribe](../interfaces/ILinkQuery.md#unsubscribe)

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:264](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L264)

___

### unsubscribeAll

▸ **unsubscribeAll**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Implementation of

[ILinkQuery](../interfaces/ILinkQuery.md).[unsubscribeAll](../interfaces/ILinkQuery.md#unsubscribeall)

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:271](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L271)

___

### unsubscribeFromResource

▸ **unsubscribeFromResource**(`uri`): `Promise`\<`void`\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `uri` | `any` |

#### Returns

`Promise`\<`void`\>

#### Defined in

[packages/connected/src/linkTraversal/ResourceLinkQuery.ts:245](https://github.com/o-development/ldo/blob/2085e12f9f1a1b9db0429a041343e0568e3bede9/packages/connected/src/linkTraversal/ResourceLinkQuery.ts#L245)
