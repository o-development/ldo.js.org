# `SolidLdoProvider`

A Provider for the LDO-related party of the library.

Note: This does not provide auth functionality. It is suggested that you use the BrowserSolidLdoProvider to initialize the app.

## Usage

```typescript
import type { FunctionComponent } from "react";
import React from "react";
import {
  SolidLdoProvider,
} from "@ldo/solid-react";

// The base component for the app
const App: FunctionComponent = () => {
  return (
    <SolidLdoProvider>
      <ReastOfTheApp />
    </SolidLdoProvider>
  );
};
```

## Props

 - `children`: ReactNode - the application that should be wrapped