# `SolidLdoProvider`

A Provider for the LDO-related part of the library.

Note: This does not provide auth functionality. It is suggested that you use the BrowserSolidLdoProvider to initialize the app.

## Usage

```typescript
import type { FunctionComponent } from "react";
import React from "react";
import { SolidLdoProvider } from "@ldo/solid-react";

// The base component for the app
const App: FunctionComponent = () => {
  return (
    <SolidLdoProvider>
      <RestOfTheApp />
    </SolidLdoProvider>
  );
};
```

## Props

 - `children: ReactNode` - The application that should be wrapped