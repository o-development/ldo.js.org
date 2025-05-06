# `useLinkQuery`

A hook that lets you define a query and will explore links in documents until
all documents encompassed by that query are fetched.

```typescript
import { useLinkQuery } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const linkQuery = {
  name: true,
  knows: {
    name: true,
  },
} as const;

const UseLinkQueryTest: FunctionComponent = () => {
  const profile = useLinkQuery(
    SolidProfileShapeShapeType,
    "https://example.com/profile/card",
    "https://example.com/profile/card#me",
    linkQuery,
  );
  if (!profile) return <p>Loading</p>;
  return (
    <div>
      <p role="profile-name">{profile.name}</p>
      <ul role="list">
        {profile.knows?.map((nestedProfile) => (
          <li key={nestedProfile["@id"]}>{nestedProfile.name}</li>
        ))}
      </ul>
    </div>
  );
};
```

### Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object. This will also inform what a link query can be.
 - `startingResource: string` - The URI of the resource at which to begin link exploration.
 - `startingSubject: string` - The URI of the subject (in RDF) at which to begin link exploration.
 - `linkQuery: LinkQuery<Type>` - A query defining the tree of data you'd like to fetch.

### Returns

A partial version of the requested data constrained by the given query.