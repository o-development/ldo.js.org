# Interface: WaitingProcess\<Args, Return\>

A data structure that represents a possible process and how to handle it.

## Type parameters

| Name | Type |
| :------ | :------ |
| `Args` | extends `any`[] |
| `Return` | `Return` |

## Properties

### after

• `Optional` **after**: (`result`: `Return`) => `void`

#### Type declaration

▸ (`result`): `void`

##### Parameters

| Name | Type |
| :------ | :------ |
| `result` | `Return` |

##### Returns

`void`

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:13](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L13)

___

### args

• **args**: `Args`

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:9](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L9)

___

### awaitingRejections

• **awaitingRejections**: (`err`: `any`) => `void`[]

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:12](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L12)

___

### awaitingResolutions

• **awaitingResolutions**: (`returnValue`: `Return`) => `void`[]

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:11](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L11)

___

### name

• **name**: `string`

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:8](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L8)

___

### perform

• **perform**: (...`args`: `Args`) => `Promise`\<`Return`\>

#### Type declaration

▸ (`...args`): `Promise`\<`Return`\>

##### Parameters

| Name | Type |
| :------ | :------ |
| `...args` | `Args` |

##### Returns

`Promise`\<`Return`\>

#### Defined in

[packages/connected-solid/src/util/RequestBatcher.ts:10](https://github.com/o-development/ldo/blob/db87958cb6f858f6cf7340ba5d9536a3a794d587/packages/connected-solid/src/util/RequestBatcher.ts#L10)
