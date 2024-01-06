# `useSolidAuth`

A hook that returns the following helpers for authentication:

---

## `login`

Logs the user in. Note that this will redirect the window, so any code after this function is called will not be called.

```typescript
import { useSolidAuth } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { login } = useSolidAuth();

  const onLogIn = useCallback(async () => {
    const issuer = prompt("What is your Solid Identity Provier?");
    if (issuer) login(issuer);
  }, []);

  return <button onClick={onLogIn}>Log In</button>
}
```

### Parameters

 - `issuer: string` - The identity provider for the user that is logging in
 - `loginOptions?: LoginOptions` - An object with the following fields
   - `redirectUrl?: string` - A custom redirect url. By default, LDO will redirect to the same page, but you can provide a different page here.
   - `clientId?: string` - A custom clientId. By default, LDO will dynamically register your client
   - `clientSecret?: string` - A custom cleint secret. By default, LDO will dynamically register your client
   - `clientName?: string` - A client name. By default, your client name will be "Solid Application"
   - `tokenType?: "DPoP" | "Bearer"` - Custom token type. By default it's DPoP.
   - `refreshToken?: string` - A refresh token. Providing a refresh token will ensure you don't need to go to a login screen.

---

## `logout`

Logs the current user out of the application.

```typescript
import { useSolidAuth } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { logout } = useSolidAuth();

  return <button onClick={logout}>Log Out</button>
}
```

---

## signUp: (issuer: string, loginOptions?: LoginOptions) => Promise<void>;

WARNING: This function only works on Solid servers that implement the 

Signup is an experiemental function that will direct users to a Sign-Up flow on a Solid Identity Provider rather than the login flow.

```typescript
import { useSolidAuth } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { signUp } = useSolidAuth();

  const onSignUp = useCallback(async () => {
    const issuer = prompt("What is your Solid Identity Provier?");
    if (issuer) signUp(issuer);
  }, []);

  return <button onClick={onSignUp}>Sign Up</button>
}
```

### Parameters

 - `issuer: string` - The identity provider for the user that is logging in
 - `loginOptions?: LoginOptions` - An object with the following fields
   - `redirectUrl?: string` - A custom redirect url. By default, LDO will redirect to the same page, but you can provide a different page here.
   - `clientId?: string` - A custom clientId. By default, LDO will dynamically register your client
   - `clientSecret?: string` - A custom cleint secret. By default, LDO will dynamically register your client
   - `clientName?: string` - A client name. By default, your client name will be "Solid Application"
   - `tokenType?: "DPoP" | "Bearer"` - Custom token type. By default it's DPoP.
   - `refreshToken?: string` - A refresh token. Providing a refresh token will ensure you don't need to go to a login screen.

---

## `fetch`

An authenticated fetch function to make HTTP requests. Most functions on Solid servers can be handled with the LDO API, but if you want to make a raw query to a Solid server, use the `fetch` function.

```typescript
import { useSolidAuth } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { fetch } = useSolidAuth();

  const onDoFetch = useCallback(async () => {
    const response = await fetch("https://example.com/");
  }, []);

  return <button onClick={onDoFetch}>Do Fetch</button>
}
```

## `session`

Info on the current session. This object will be updated with recent information on the logged in user.

```typescript
import { useSolidAuth } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { session } = useSolidAuth();

  if (!session.isLoggedIn) {
    return <p>You are not logged in.</p>
  }

  return <p>Logged in as {session.webId}</p>
}
```

### Fields

 - `isLoggedIn: boolean` - True if the current user is logged in
 - `webId?: string` - The WebId of the current user
 - `clientAppId?: string` - The app id for the client
 - `sessionId: string` - A unique id for this application's setting
 - `expirationDate?: number` - The time the auth token expires

---

## `ranInitialAuthCheck`

A boolean value to check if the auth check at load has been run or not

```typescript
import { useSolidAuth } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { session, ranInitialAuthCheck } = useSolidAuth();

  if (!ranInitialAuthCheck) {
    return <p>Loading</p>
  }

  if (!session.isLoggedIn) {
    return <p>You are not logged in.</p>
  }

  return <p>Logged in as {session.webId}</p>
}
```