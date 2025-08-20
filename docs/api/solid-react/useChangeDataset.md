# `useChangeDataset`

A hook that starts a transaction with the global dataset, then provides you with tools for modifying and committing that transaction.

Use this hook for forms and bulk operations.

```typescript
import { useChangeDataset } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { namedNode, literal } from "@ldo/rdf-utils";

const Component: FunctionComponent = () => {
  const [transactionDataset, setData, commitData] = useChangeDataset();

  const handleAddData = () => {
    setData((dataset) => {
      dataset.add(
        namedNode("https://example.com/subject"),
        namedNode("http://xmlns.com/foaf/0.1/name"),
        literal("John Doe")
      );
      dataset.add(
        namedNode("https://example.com/subject"),
        namedNode("http://xmlns.com/foaf/0.1/mbox"),
        literal("john@example.com")
      );
    });
  };

  const handlePreviewChanges = () => {
    console.log("Current transaction dataset:", transactionDataset.toString());
  };

  const handleCommitChanges = async () => {
    const result = await commitData();
    if (result.isError) {
      console.error("Failed to commit changes:", result.error);
    } else {
      console.log("Changes committed successfully!");
    }
  };

  return (
    <div>
      <button onClick={handleAddData}>
        Add Data
      </button>
      <button onClick={handlePreviewChanges}>
        Preview Changes
      </button>
      <button onClick={handleCommitChanges}>
        Commit Changes
      </button>
    </div>
  );
};
```

## Parameters

This hook takes no parameters.

## Returns

Returns a tuple containing three elements:

1. **`transactionDataset`** - A transaction dataset derived from the parent dataset. This dataset can be modified without triggering update events in the global dataset.

2. **`setData`** - A function for modifying the transaction dataset. It takes a callback function that receives the transaction dataset as a parameter. All changes made within the callback are batched together and will be committed when `commitData` is called.

   ```typescript
   setData((dataset) => {
     // Modify the dataset here
     dataset.add(subject, predicate, object);
     dataset.delete(subject, predicate, object);
   });
   ```

3. **`commitData`** - An async function that commits all changes from the transaction dataset to the global dataset and remote dataset (if connected). Returns a Promise that resolves when the commit is successful or rejects if there's an error.