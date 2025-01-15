# `useSubject`

A hook that lets you get a Linked Data Object for a specific subject.

```typescript
import { useSubject } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const profile = useSubject(ProfileShapeType, "https://example.com/profile#me");

  return <p>Name: {profile?.name}</p>
}
```

### Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object
 - `subject: string | SubjectNode` - the subject URI

### Returns

A linked data object corresponding to the given subject