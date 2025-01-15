# `useMatchSubject`

A hook that lets you get a list of Linked Data Objects for a subject matching the provided parameters.

```typescript
import { useMatchSubject } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  // Gets all subjects in the database that have a type "Person"
  const profiles = useMatchSubject(
    ProfileShapeType,
    "http://www.w3.org/1999/02/22-rdf-syntax-ns#type",
    "http://xmlns.com/foaf/0.1/Person",
    null,
  );

  return <div>
    {profiles.map((profile) => <p>Name: {profile?.name}</p>}
  </div>
}
```

### Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object
 - `predicate: string | PredicateNode | null` - The predicate to match
 - `object: string | ObjectNode | null` - The object to match
 - `graph: string | GraphNode | null` - The graph to match

### Returns

A list of linked data objects corresponding to the given matched items.