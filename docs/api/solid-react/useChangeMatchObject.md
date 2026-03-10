# `useChangeMatchObject`

A hook that lets you get a list of Linked Data Objects for objects matching the provided parameters, and provides tools for modifying and committing changes to those objects within a transaction.

Use this hook for forms that need to modify multiple matching objects.

```typescript
import { useChangeMatchObject, useResource } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./_ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const resource = useResource("https://example.com/connections");
  
  // Gets all objects in the database that know Kevin Bacon
  const [profiles, setProfiles, commitProfiles] = useChangeMatchObject(
    ProfileShapeType,
    "https://example.com/Kevin_Bacon",
    "http://xmlns.com/foaf/0.1/knows",
    null,
  );

  const handleUpdateAllNames = () => {
    setProfiles(resource, (profileSet) => {
      profileSet.forEach((profile) => {
        if (profile) {
          profile.fn = "Updated Name";
        }
      });
    });
  };

  const handleAddEmailToAll = () => {
    setProfiles(resource, (profileSet) => {
      profileSet.forEach((profile) => {
        if (profile) {
          profile.mbox = "updated@example.com";
        }
      });
    });
  };

  const handleCommitChanges = async () => {
    try {
      await commitProfiles();
      console.log("All profile changes committed successfully!");
    } catch (error) {
      console.error("Failed to commit changes:", error);
    }
  };

  return (
    <div>
      <div>
        {profiles.map((profile, index) => (
          <div key={index}>
            <p>Name: {profile?.fn}</p>
            <p>Email: {profile?.mbox}</p>
          </div>
        ))}
      </div>
      <button onClick={handleUpdateAllNames}>
        Update All Names
      </button>
      <button onClick={handleAddEmailToAll}>
        Add Email to All
      </button>
      <button onClick={handleCommitChanges}>
        Commit All Changes
      </button>
    </div>
  );
};
```

## Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object
 - `subject: string | SubjectNode | null` - The subject to match
 - `predicate: string | PredicateNode | null` - The predicate to match
 - `graph: string | GraphNode | null` - The graph to match
 - `options?: UseMatchObjectOptions` - Optional configuration for the matching behavior

## Returns

Returns a tuple containing three elements:

1. **`objects`** - A list of linked data objects corresponding to the given matched items, derived from a transaction dataset.

2. **`setObjects`** - A function for modifying the matched objects. It takes two parameters:
   - `resource`: A resource object (typically from `useResource`) that contains the objects to modify
   - `changer`: A callback function that receives the set of objects and allows you to modify them

   ```typescript
   setObjects(resource, (objectSet) => {
     // Modify the objects here
     objectSet.forEach((object) => {
       if (object) {
         object.property = "new value";
       }
     });
   });
   ```

3. **`commitObjects`** - An async function that commits all changes from the transaction dataset to the global dataset and remote dataset (if connected). Returns a Promise that resolves when the commit is successful or rejects if there's an error.
