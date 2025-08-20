# `useResource`

Fetches a resource and rerenders the component as the state of the resource changes.

```typescript
import { useResource } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const resource = useResource("https://example.com/profile");

  if (resource?.isLoading()) {
    return <p>Loading...</p>;
  }

  return <p>{resource?.uri} loaded</p>;
};
```

## Parameters

 - `uri: string` - The URI of the resource
 - `options?: UseResourceOptions` - Optional configuration containing:
   - `suppressInitialRead?: boolean` - If true, this hook will not trigger a read event to fetch the document
   - `reloadOnMount?: boolean` - If true, this hook will trigger a read event whenever this component mounts
   - `subscribe?: boolean` - If true, this will subscribe to updates via WebSockets

## Returns

A resource object that provides access to the resource's data and status.
