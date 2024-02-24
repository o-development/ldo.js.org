# Interface: GetWacUriSuccess

Returned when the URI for a resources ACL document was successfully retried

## Hierarchy

- `ResourceSuccess`

  ↳ **`GetWacUriSuccess`**

## Properties

### isError

• **isError**: ``false``

#### Inherited from

ResourceSuccess.isError

#### Defined in

[packages/solid/src/requester/results/success/SuccessResult.ts:7](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/results/success/SuccessResult.ts#L7)

___

### type

• **type**: ``"getWacUriSuccess"``

#### Overrides

ResourceSuccess.type

#### Defined in

[packages/solid/src/resource/wac/results/GetWacUriSuccess.ts:8](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/wac/results/GetWacUriSuccess.ts#L8)

___

### uri

• **uri**: `string`

The URI of the resource

#### Inherited from

ResourceSuccess.uri

#### Defined in

[packages/solid/src/requester/results/success/SuccessResult.ts:17](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/requester/results/success/SuccessResult.ts#L17)

___

### wacUri

• **wacUri**: [`LeafUri`](../types/LeafUri.md)

The URI of the ACL document

#### Defined in

[packages/solid/src/resource/wac/results/GetWacUriSuccess.ts:12](https://github.com/o-development/ldo/blob/e8bb8b1/packages/solid/src/resource/wac/results/GetWacUriSuccess.ts#L12)
