# `useRootContainer`

Gets the Root container of the given URI

```typescript
import { useLdo, useResource, useSubject, commitData } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const rootContainer = useRootContainer("https://example.com/profile");

  return <p>RootContainer {rootContainer?.uri}</p>
}
```

### Parameters

 - `uri: string` - the URI of the resource

### Returns

A root container or undefined if it hasn't been fetched yet
