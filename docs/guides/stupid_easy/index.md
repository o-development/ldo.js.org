# Building with LDO is Stupid Easy

Let's build an LDO React app in a few very easy steps.

## 1. Initialize your React App

```bash
npx create-react-app stupid-easy-solid --template typescript
cd stupid-easy-solid
npm run start
```

## 2. Initialize LDO

```bash
npx @ldo/cli init
npm i @ldo/solid-react
```

## 3. Observe the generated files in the `/src/.ldo` folder

FoafProfile.typings.ts

```typescript
import { LdoJsonldContext, LdSet } from "@ldo/ldo";

export interface FoafProfile {
  "@id"?: string;
  "@context"?: LdoJsonldContext;
  /**
   * Defines the node as a Person (from foaf)
   */
  type: {
    "@id": "Person";
  };
  /**
   * Define a person's name.
   */
  name?: string;
  /**
   * Photo link but in string form
   */
  img?: string;
  /**
   * A list of WebIds for all the people this user knows.
   */
  knows?: LdSet<FoafProfile>;
}
```

FoafProfile.shapeTypes.ts

```typescript
import { ShapeType } from "@ldo/ldo";
import { foafProfileSchema } from "./foafProfile.schema";
import { foafProfileContext } from "./foafProfile.context";
import { FoafProfile } from "./foafProfile.typings";

export const FoafProfileShapeType: ShapeType<FoafProfile> = {
  schema: foafProfileSchema,
  shape: "https://example.com/FoafProfile",
  context: foafProfileContext,
};
```

## 4. Set up Component Structure

App.tsx

```typescript
import { Login } from './Login';

function App() {
  return (
    <Login />
  );
}

export default App;
```

Login.tsx

```typescript
import { FunctionComponent } from "react";
import { Profile } from "./Profile";

export const Login: FunctionComponent = () => {
  return <div>
    Login
    <Profile />
  </div>
}
```

Profile.tsx

```typescript
import { FunctionComponent } from "react";

export const Profile: FunctionComponent = () => {
  return <div>Profile</div>
}
```

## 5. Add a wrapper component

App.tsx

```typescript  hl_lines="1 6 8"
import { BrowserSolidLdoProvider } from '@ldo/solid-react';
import { Login } from './Login';

function App() {
  return (
    <BrowserSolidLdoProvider>
      <Login />
    </BrowserSolidLdoProvider>
  );
}

export default App;
```

## 6. Trigger Login

Login.tsx

```typescript  hl_lines="1 6 8 9 10 11 12 13 14 15 16 17 18 20 21 22 23 24 25 26"
import { useSolidAuth } from "@ldo/solid-react";
import { FunctionComponent } from "react";
import { Profile } from "./Profile";

export const Login: FunctionComponent = () => {
  const { login, logout, session } = useSolidAuth();

  if (!session.isLoggedIn) {
    return (
      <div>
        <p>Currently Logged Out</p>
        <button onClick={() => {
          const issuer = prompt("What is your Solid Issuer?", "https://solidweb.me");
          if (issuer) login(issuer);
        }}>Log In</button>
      </div>
    )
  }

  return (
    <div>
      <p>Logged in as {session.webId}</p>
      <button onClick={logout}>Log Out</button>
      <Profile />
    </div>
  )
}
```

## 7. Fetch and Display Data

Profile.tsx

```typescript  hl_lines="1 3 6 7 8 10 11 12 14 15 16"
import { useResource, useSolidAuth, useSubject } from "@ldo/solid-react";
import { FunctionComponent } from "react";
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes"

export const Profile: FunctionComponent = () => {
  const { session } = useSolidAuth();
  const webIdResource = useResource(session.webId);
  const profile = useSubject(FoafProfileShapeType, session.webId);

  if (webIdResource?.isLoading()) {
    return <p>Loading...</p>
  }

  return <div>
    <p>Hello! Welcome {profile?.name}.</p>
  </div>
}
```

## 8. Modify Data

```typescript hl_lines="1 9 17 18 19 20 21 22"
import { useLdo, useResource, useSolidAuth, useSubject } from "@ldo/solid-react";
import { FunctionComponent } from "react";
import { FoafProfileShapeType } from "./.ldo/foafProfile.shapeTypes"

export const Profile: FunctionComponent = () => {
  const { session } = useSolidAuth();
  const webIdResource = useResource(session.webId);
  const profile = useSubject(FoafProfileShapeType, session.webId);
  const { changeData, commitData } = useLdo();  

  if (webIdResource?.isLoading()) {
    return <p>Loading...</p>
  }

  return <div>
    <p>Hello! Welcome {profile?.name}.</p>
    <input value={profile?.name} onChange={async (e) => {
      if (!profile || !webIdResource) return;
      const cProfile = changeData(profile, webIdResource);
      cProfile.name = e.target.value;
      await commitData(cProfile);
    }} />
  </div>
}
```

