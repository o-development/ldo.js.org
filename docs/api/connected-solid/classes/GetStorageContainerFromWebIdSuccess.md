# Class: GetStorageContainerFromWebIdSuccess

Indicates that the storage container has been successfully retireved from the
webId. Call `GetStorageContainerFromWebIdSuccess.storageContainers` for a
list of storage containers retrieved.

## Hierarchy

- `SuccessResult`

  ↳ **`GetStorageContainerFromWebIdSuccess`**

## Constructors

### constructor

• **new GetStorageContainerFromWebIdSuccess**(`storageContainers`): [`GetStorageContainerFromWebIdSuccess`](GetStorageContainerFromWebIdSuccess.md)

#### Parameters

| Name | Type |
| :------ | :------ |
| `storageContainers` | [`SolidContainer`](SolidContainer.md)[] |

#### Returns

[`GetStorageContainerFromWebIdSuccess`](GetStorageContainerFromWebIdSuccess.md)

#### Overrides

SuccessResult.constructor

#### Defined in

[packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts:34](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts#L34)

## Properties

### isError

• `Readonly` **isError**: ``false``

#### Inherited from

SuccessResult.isError

#### Defined in

packages/connected/dist/results/success/SuccessResult.d.ts:5

___

### storageContainers

• **storageContainers**: [`SolidContainer`](SolidContainer.md)[]

The storage containers retrieved

#### Defined in

[packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts:32](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts#L32)

___

### type

• **type**: ``"getStorageContainerFromWebIdSuccess"``

#### Overrides

SuccessResult.type

#### Defined in

[packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts:27](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/requester/results/success/CheckRootContainerSuccess.ts#L27)
