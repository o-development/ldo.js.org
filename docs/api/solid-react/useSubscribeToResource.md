# `useSubscribeToResource`

A hook that lets you subscribe to a list of Resource URLs via webhooks.

When a resource is updated on a Pod, the updates will automatically be reflected in LDO.

```typescript
import { useSubscribeToResource } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  // Subscribes to updates on the Pod for the given resource. If the Pod is
  // updated, any component touching changed data will rerender.
  useSubscribeToResource(
    "https://example.com/Person1",
    "https://example.com/Person2"
  );
  
  const profile1 = useSubject(
    ProfileShapeType,
    "https://example.com/Person1#me"
  );
  const profile2 = useSubject(
    ProfileShapeType,
    "https://example.com/Person2#me"
  );

  return <div>
    <p>Profile1: {profile1.name}</p>
    <p>Profile2: {profile2.name}</p>
  </div>
}
```

### Parameters

 - `...ResrouceUri: string[]` - A list of resource URIs.

### Returns

Void.