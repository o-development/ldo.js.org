# `useRootContainer`

Gets the root container of the given URI.

```typescript
import { useRootContainer } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const rootContainer = useRootContainer("https://example.com/profile");

  return <p>Root Container: {rootContainer?.uri}</p>;
};
```

## Parameters

 - `uri: string` - The URI of the resource

## Returns

A root container or undefined if it hasn't been fetched yet.
