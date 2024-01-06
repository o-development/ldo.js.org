# `BrowserSolidLdoProvider`

A BrowserSolidLdoProvider wraps the application and wires up all the base infrastructure to use @ldo/solid-react. Specifically, it works in a web browser environment. This combines SolidLdoProvider with the login functions of @inrupt/solid-client-authn-browser

## Usage

```typescript
import type { FunctionComponent } from "react";
import React from "react";
import {
  BrowserSolidLdoProvider,
} from "@ldo/solid-react";

// The base component for the app
const App: FunctionComponent = () => {
  return (
    /* The application should be surrounded with the BrowserSolidLdoProvider
    this will set up all the underlying infrastructure for the application */
    <BrowserSolidLdoProvider>
      <Login />
    </BrowserSolidLdoProvider>
  );
};
```

## Props

 - `children`: ReactNode - the application that should be wrapped