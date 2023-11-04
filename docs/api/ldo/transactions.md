# transactions

Transactions let you modify data and commit all modifications at once. It's also useful for seeing the changes that were made.

## Usage

```typescript
import {
  startTransaction,
  transactionChanges,
  toSparqlUpdate,
  commitTransaction,
} from "@ldo/ldo"; 

// ... Get the profile linked data object

startTransaction(profile);
profile.name = "Kuzon"
const changes = transactionChanges(profile));
// Logs: <https://example.com/aang> <http://xmlns.com/foaf/0.1/name> "Kuzon"
console.log(changes.added?.toString())
// Logs: <https://example.com/aang> <http://xmlns.com/foaf/0.1/name> "Aang"
console.log(changes.removed?.toString())
commitTransaction(profile);
```

---

## `startTransaction`

Begins a transaction for a Linked Data Object. After this function is run, the Linked Data Object is considered to be "transactable" where all modifications are not written to the underlying dataset are stored separately as a delta.

Note: If a Linked Data Object is "transactable", it cannot be passed into `startTransaction` a second time.

```typescript
startTransaction(ldo: LdoBase): void
```

### Parameters
 - `ldo`: Any linked data object that is not currently "transactable"

---

## `commitTransaction`

Commits a transaction, writing all the stored changes to the underlying dataset. After this function is run, the Linked Data Object is considered to be NOT "transactable" all further modifications will be written directly to the underlying dataset.

```typescript
commitTransaction(ldo: LdoBase): void
```

### Parameters
 - `ldo`: Any linked data object that is currently "transactable"

---

## `transactionChanges`

Returns the changes that are made on a "transactable" Linked Data Object.

```typescript
transactionChanges(ldo: LdoBase): DatasetChanges<Quad>
```

### Parameters
 - `ldo`: Any linked data object that is currently "transactable"

### Return Value

DatasetChanges

 - `added` (Optional): `Dataset<Quad>`: All quads added during this transaction.
 - `removed` (Optional): `Dataset<Quad>`: All quads removed during this transaction
