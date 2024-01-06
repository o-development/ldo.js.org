# `useResource`

Fetches a resource and rerenders the component as the state of the resource changes.

```typescript
import { useLdo, useResource, useSubject, commitData } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const resource = useResource("https://example.com/profile");

  if (resource.isLoading()) {
    return <p>Loading...</p>
  }
  return <p>{resource.uri} loaded</p>
}
```

### Parameters

 - `uri: string` - the URI of the resource
 - `options: {}` - Options containing the following fields
   - `suppressInitialRead?: boolean` - If true, this hook will not trigger a read event to fetch the document.
   - `reloadOnMount?: boolean` - If true, this hook will trigger a read event whenever this component mounts

### Returns

A resource
