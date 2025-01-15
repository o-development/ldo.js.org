# `useMatchSubject`

A hook that lets you get a list of Linked Data Objects for a subject matching the provided parameters.

```typescript
import { useMatchObject } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  // Gets all objects in the database that know Kevin Bacon 
  const profiles = useMatchObject(
    ProfileShapeType,
    "https://example.com/Kevin_Bacon",
    "http://xmlns.com/foaf/0.1/knows",
    null,
  );

  return <div>
    {profiles.map((profile) => <p>Name: {profile?.name}</p>}
  </div>
}
```

### Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object
 - `subject: string | SubjectNode | null` - The subject to match
 - `predicate: string | PredicateNode | null` - The predicate to match
 - `graph: string | GraphNode | null` - The graph to match

### Returns

A list of linked data objects corresponding to the given matched items.