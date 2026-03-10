# `useLinkQuery`

A hook that lets you define a query and will explore links in documents until all documents encompassed by that query are fetched.

```typescript
import { useLinkQuery } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./_ldo/Profile.shapeType";

// Define a link query outside of the render function so it doesn't trigger
// unneeded updates.
const linkQuery = {
  name: true,
  knows: {
    name: true,
  },
} as const;

const Component: FunctionComponent = () => {
  const profile = useLinkQuery(
    ProfileShapeType,
    "https://example.com/profile/card",
    "https://example.com/profile/card#me",
    linkQuery,
  );

  if (!profile) return <p>Loading...</p>;

  return (
    <div>
      <p>Profile Name: {profile.name}</p>
      <ul>
        {profile.knows?.map((nestedProfile) => (
          <li key={nestedProfile["@id"]}>{nestedProfile.name}</li>
        ))}
      </ul>
    </div>
  );
};
```

## Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object. This will also inform what a link query can be.
 - `startingResource: string` - The URI of the resource at which to begin link exploration.
 - `startingSubject: string` - The URI of the subject (in RDF) at which to begin link exploration.
 - `linkQuery: LinkQuery<Type>` - A query defining the tree of data you'd like to fetch.

## Returns

A partial version of the requested data constrained by the given query.