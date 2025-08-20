# `useSubject`

A hook that lets you get a Linked Data Object for a specific subject.

```typescript
import { useSubject, useResource } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const resource = useResource("https://example.com/profile");
  const profile = useSubject(ProfileShapeType, "https://example.com/profile#me");

  if (resource?.isLoading() || !profile) return <p>Loading...</p>;

  return <p>Name: {profile.name}</p>;
};
```

## Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object
 - `subject: string | SubjectNode` - The subject URI
 - `options?: UseSubjectOptions` - Optional configuration

## Returns

A linked data object corresponding to the given subject.