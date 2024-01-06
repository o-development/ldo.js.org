# `useLdo`

A hook that returns the following helpers:

---

## `dataset`

The global dataset for the application. 

```typescript
import { useLdo } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { dataset } = useLdo();

  useEffect(() => {
    // Logs the global dataset as n-tiples
    console.log(dataset.toString());
  }, []);
}
```

---

## `getResource`

A function that lets you retrieve a resource. This functionally serves the same purpose as `useResource`, but in a non-hook form.

```typescript
import { useLdo } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";

const Component: FunctionComponent = () => {
  const { getResource } = useLdo();

  useEffect(() => {
    const resource = getResource("https://example.com/");
  }, []);
}
```

### Parameters
 - `uri: string`: the URI or the resource
 - `options`: object with the following fields:
   - `autoLoad: boolean` - true if the resource should autoload

### Returns

A Leaf or Container depending on the URI

---

## `getSubject`

A function that lets you get a Linked Data Object for a specific subject. This functionally serves the same purpose as `useSubject`, but in a non-hook form.

```typescript
import { useLdo } from "@ld/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const { getSubject } = useLdo();

  useEffect(() => {
    const profile = getSubject(
      ProfileShapeType,
      "https://example.com/profile#me"
    );
    console.log(profile?.name);
  }, []);
}
```

### Parameters

 - `ShapeType: ShapeType` - The ShapeType dictating the shape of the Linked Data Object
 - `subject: string | SubjectNode` - the subject URI

### Returns

A linked data object corresponding to the given subject

---

## createData<Type extends LdoBase>(

Creates modifiable data that can be edited and committed.

```typescript
import { useLdo, useResource, commitData } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { PostShapeType } from "./.ldo/Post.shapeType";

const Component: FunctionComponent = () => {
  const { createData } = useLdo();

  const resource = useResource("https://example.com/post1.ttl");

  const onCreatePost = useCallback(async () => {
    const cPost = createData(
      PostShapeType,
      "https://example.com/post1",
      resource
    );
    cPost.message = "This is a post";
    await commitData(cPost);
  }, []);

  return <button onClick={onCreatePost}>Create Post</button>
}
```

### Parameters

 - `shapeType: ShapeType<Type>` - The ShapeType dictating the shape of the Linked Data Object
 - `subject: string | SubjectNode` - the subject URI
 - `...resources: Resource[]` - Any number of resources that any update should be applied to

### Returns

A Linked Data Object associated with the provided subject

---

## `changeData`

Takes a Linked Data Object and turns it into a modifiable Linked Data Object that can be edited and committed.

```typescript
import { useLdo, useResource, useSubject, commitData } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { ProfileShapeType } from "./.ldo/Profile.shapeType";

const Component: FunctionComponent = () => {
  const { changeData } = useLdo();

  const resource = useResource("https://example.com/profile");
  const profile = useSubject("https://example.com/subject")

  const onModifyProfile = useCallback(async () => {
    if (!resource || !profile) return;
    const cProfile = changeData(
      profile
      resource
    );
    cProfile.name = "Mr. Cool Dude";
    await commitData(cProfile);
  }, []);

  return <button onClick={onModifyProfile}>Modify Profile</button>
}
```

### Parameters

 - `input: Type` - The Linked Data Object that should now be modifiable
 - `...resources: Resource[]` - Any resources that all updates should be applied to

### Returns

A Linked Data Object associated with the provided subject

---

## `commitData`

Commits changes made on Linked Data Objects to the Pod.

```typescript
import { useLdo, useResource, commitData } from "@ldo/solid-react";
import React, { FunctionComponent } from "react";
import { PostShapeType } from "./.ldo/Post.shapeType";

const Component: FunctionComponent = () => {
  const { createData } = useLdo();

  const resource = useResource("https://example.com/post1.ttl");

  const onCreatePost = useCallback(async () => {
    const cPost = createData(
      PostShapeType,
      "https://example.com/post1",
      resource
    );
    cPost.message = "This is a post";
    const result = await commitData(cPost);
    if (result.isError) {
      alert(result.message);
    }
  }, []);

  return <button onClick={onCreatePost}>Create Post</button>
}
```

### Parameters

 - `input: LdoBase` - A changed Linked Data Object

### Returns

An update result
